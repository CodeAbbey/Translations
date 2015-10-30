_Thanks to my colleague [Zhanna Khaymedinova](https://www.facebook.com/sleepydisaster) for the idea of this exercise!_

Nowadays there are tons of information on the internet. And no wonder that such information even if targeted to humans,
is often collected and processed by robots.

In this task you are to write a small program which collects data over the social network. Start from here:

[John Doe at Fake Social Network](http://codeabbey.github.io/social-network/)

You see that each page represents a person with different name, date of birth and `net worth`. Also each page provides
links to few other people somehow related to given one, so that from **John Doe** you can navigate to **Dan Wagner**
(via "Friends") and from here to **Dave Johnson** (via messages on the "Wall").

###The Task

The goal is to sum up `net worth` figures for all persons with specific last name (e.g. **Johnson**) who are reachable
(via any number of links) from **John Doe**.

View source of the page (by pressing `Ctrl-U` or using **Inspect element** feature in Google Chrome or Firebug plugin
for FireFox) to see how elements of text could be distinguished (with regexps or some other method).

Typical approach is like following:

- create a function to download page by `url` into string (for example
	[here are hints](http://stackoverflow.com/questions/16025368/download-file-as-string-in-python) for Python);
- write function to extract references to other pages from the string (hint - they are in form
	`<a href="./monika-s-smith.html">` - easy to fetch with regexp!);
- also add functions to extract the last name and net worth;
- now make a loop which traverses the social graph - avoid visiting the same pages for several times or you may stuck,
	(you may want to use [Breadth First Search](./breadth-first-search) here);
- the only thing remaining is to sum up all **Johnsons** for example.

There are also some things to note:

- if your script have processed more than `1500` persons and still goes on - you obviously are in a loop of some kind,
	since there aren't that many pages;
- note that site does not return pages very fast, so you may use separate script to fetch and save all reachable pages
	into temporary directory and then perform processing on saved files in case if you will try to process them more
	than once (due to some mistakes for example);
- probably adding small delays (`200-300` milliseconds) after fetching each page may surprisingly reduce delays
	introduced by site itself and speed up the process.

**Input data** will contain last name (lowercased) which we are interested in.  
**Answer** should contain total `net worth` for all people with such last name who are reachable from the initial page.

Example:

    input data:
	doe
	
	answer:
	130000
