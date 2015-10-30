This is the simplest of [interactive problems](../wiki/interactive-problems) - please read explanations in this article
before trying. The purpose of this task is to learn exchanging `post` requests with server at all.

You are to play quite clever game against the server:

- after you send the first request (i.e. one with a lonely token), server choses random value between `1` and `99` and
	returns it to you (with the name of `secret`);
- you should then send another request with field `answer` which contains another value, so that their sum is exactly `100`.

Server url is [http://codeabbey.sourceforge.net/say-100.php](http://codeabbey.sourceforge.net/say-100.php)

**Input data** gives you a token to play and **answer** should contain victory token returned to you by server.

Example:

	YOU									SERVER
	------------------------			------------------------
	
	token: <your-token>					secret: 74								// request-response # 1
	
	token: <your-token>					end: <your-victory-token>				// request-response # 2
	answer: 26
