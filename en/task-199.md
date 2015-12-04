After you learned how to create [Dynamic Web Page](./dynamic-web-page) and use
[Query String Parameters](./query-string-parameters) the last cornerstone thing for creating web-applications is to
find out how to preserve the state on the server.

Let us regard a simple example - the page which lists employees of a company and allows adding new ones. It should
work like following:

- if called without query parameters, it just lists employees already stored;
- when called with parameter `name` (e.g. `name=John+Doe`) - specified name should be added to the list;
- at last, if parameter `kill` is specified, list should be cleared and initialized with single name (the company founder).

[Here is an example](http://rodiongork.atwebpages.com/employees/index.php) - it also includes small form, so that you
can just enter names and click buttons instead of typing parameters manually (but you still can see parameters in the
address line). You should see that after adding a name the updated state of the list is preserved for future visitors.

**Where to store data on a server?**

Most hosting providers will allow you two general options:

- storing data in a file - i.e. your script simply opens a file as usually and reads array of names from it -
	and also it should update this file on addition / clearing operation;
- using database - for example `MySQL` or `MongoDb` are often provided for your applications - however you should
	research this on your own (I hope we'll add exercises on SQL later).

This exercise allows you to use any of these options. Just make your page accept query parameters `name` and `kill` -
and make it list employees as described above.

Please make your page list employees using [unordered list](http://www.w3schools.com/tags/tag_ul.asp) - i.e. tags `ul`
and `li`, for example:

    <ul>
		<li>Benjamin Franklin</li>
		<li>George Washington</li>
		<li>Abraham Lincoln</li>
		<li>Theodore Roosevelt</li>
	</ul>

We are going to test your list by presense of such list with such tags. Names should follow in the same order
they were added.

<div class="attention">Note that you are not required to add any form to your page. My example has it only for convenience. Adding any
caption, title, head etc. is also optional.</div>

**Input data** will contain the name of the founder (person who should appear in a list when it is cleared).  
**Answer** should provide url of your page (without parameters) so our service can test it. Make sure it starts
with `"http://"` prefix.

Example:

    input data:
	Mr Scrooge
	
	answer:
	http://rodiongork.atwebpages.com/employees/index.php

The checker will test that given page could respond properly to the following requests:

	http://rodiongork.atwebpages.com/employees/index.php?name=Random+Words
	
	http://rodiongork.atwebpages.com/employees/index.php?kill
	
	etc.