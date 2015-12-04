So we learned how to [Use HTML](./basics-of-html) to create web-page and how to
[generate page on-the-fly](./dynamic-web-page) - but all this is about how server sends data to user.

And how can user send some data to server so that interaction is more like a "dialogue" of two people, rather than
"monologue" of a server?

One of the oldest approaches is to append user's data to URL in form of [Query String](http://en.wikipedia.org/wiki/Query_string).
For example, regard the following link:

[http://www.bing.com/search?q=Donald+Knuth](http://www.bing.com/search?q=Donald+Knuth)

Here `www.bing.com` is obviously an address of the popular search server, while `/search` is an "endpoint" or resource
on this server - just like our dynamic web-page. But what follows next?

- there is a question mark `'?'` which separates query string parameters from the address itself;
- then parameters follow in the form `name=value` (here `q` is a name of parameter and `Donald Knuth` is a value);
- you may notice that spaces in parameter values are substituted with plus sign `'+'`;
- if we need to pass several parameters, we concatenate them with ampersand `'&'`.

You may note that even some pages on CodeAbbey site have similar urls, for example ones with problem solutions:

	http://www.codeabbey.com/index/task_solution?task=sum-of-two&user=testuser&lang=Python

You see there the user-id, task-id and language are passed as parameters.

Now we are going to study how such parameters are processed, and how such URL-s are conveniently generated (you could
not force user to type such things manually, could you?)

<div class="attention">An important advice was given by our colleague
<a href="/index/user_profile/hogarth45">Jesse Clark</a>: you never (in real applications) should use strings provided by users
(via parameters or forms) without some precautions, like filtering unwanted characters. For example
regard my link with such a parameter:<br/>
<a href="http://rodiongork.atwebpages.com/test.py?name=Dear+Pants+%3Cscript%3Ealert%281%29%3C/script%3E">
http://rodiongork.atwebpages.com/test.py?name=Dear+Pants+%3Cscript%3Ealert%281%29%3C/script%3E</a><br/>
it has a piece of javascript attached to name which leads to execution of some code in user's browser
(showing harmless message in our case) - though this may be prevented if browser is incognito mode or
have some other special features turned on.</div>

---

###Processing Query Parameters

Technically web-server separates parameters and feeds them to your script, for example, via environment variables.
However most web-related languages already have built-in functionality to deal with these parameters so you need not
care how exactly they came to your script.

For example if you use `Python` via simple `CGI` interface, your code will utilize `cgi.FieldStorage` object:

	#!/usr/bin/env python
	
	import cgi, cgitb 
	
	params = cgi.FieldStorage() 
	name = params.getvalue('name') if 'name' in params else 'Stranger'
	
	print "Content-type: text/html"
	print
	
	print "Hello, " + name

<p>You may see slightly improved version of such script by
	<a href="http://rodiongork.atwebpages.com/test.py?name=Dear+CodeAbbey+User" target="_blank">this link</a> -
try to play with it a bit, for example removing query parameter or substituting with your name. (make sure to hit
enter in address line after you change it, so the page is reloaded)</p>

In `PHP` this is bit easier - parameters are stored in the associative array named `$_GET`:

    <?php
	
	$name = $_GET['name'];
	
	if (empty($name)) {
		$name = 'Stranger';
	}
	
	echo "Hello, " . $name;

###Sending Query Parameters

We use HTML "form" to provide user input and allow building and using URL-s with query strings. For example:

    <form action="http://www.bing.com/search">
		<input type="text" name="q"/>
		<input type="submit" value="Search"/>
	</form>

Here `form` tag has an attribute `action` which tells the base address to where parameters would be sent. Inside the
form there are one or more `input` elements. You see the last of them have a type `submit` and is rendered as a
button. It does not affect query string produced by the form, instead it makes browser to generate the url with this
string and open it when the button is clicked.

Other `input`-s usually have `name` attribute which means they should get some value from user and attach it to query
string with such a parameter name. The input with type `text` is rendered as small text field.

You may look at [this example](http://jsfiddle.net/ovo9gntq/2/) showing such form in action. You see the html code
in the upper left window and the form produced by it in the lower right. Type in some words here (e.g. `Alan Turing`)
and click the `Search` button. You should see that form forwards you to the bing search results page (link similar
to one discussed at the beginning).

---

###Problem Statement

You will create a Personal Horoscope site now. It will ask user for name and birth date, then calculate the following
value:

    lucky = (length(name) * A + month * B + day * C + year) % 31 + 1

and output it as a "Your lucky day". Here `A`, `B` and `C` would be small integers given to you in input data.

So you have to create two pages:

1. Static web-page with the form providing `4` inputs for `name`, `year`, `month` and `day` - [see an example
	here](http://rodiongork.atwebpages.com/horoscope.html) - this form should have exactly such parameter names
	and should give as its `action` attribute the **full** url of the second page (usually you may also put relative
	urls there, but for this problem checker is not very clever to understand relative paths).
2. Dynamic web-page which, if supplied with the `4` mentioned parameters in query string, produces prophecy in form
	"Your lucky day is 25" according to formula above. Play with the form referenced above to see how it should work.

**Input data** will give you values for `A`, `B` and `C`.  
**Answer** should be an URL of your horoscope form (first page). You need not tell url of the second page since
the checker will fetch it from the first page.

Example:

	input data:
	14 30 11
	
	answer:
	http://rodiongork.atwebpages.com/horoscope.html

_After this exercise is done you are ready to proceed and make [real stateful web-app](./employees-web-app),
though small of course._