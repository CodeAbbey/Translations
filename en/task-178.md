_Please read about [interactive problems](../wiki/interactive-problems) if you are not acquainted with them._

The Wumpus is a mysterious monster of yore. I can't tell you how it looks like - and no one can. No one of those who
saw it have ever returned to tell about it.

The game [Hunt the Wumpus](http://en.wikipedia.org/wiki/Hunt_the_Wumpus) is one of the oldest computer games and have
many variations. You can still play one of them if your machine runs `Ubuntu` (or other unix-like OS) - it exists in
the package `bsd-games`.

In this problem you are hired by **International Wildlife Conservation Organization** to help in study of the life of
the Wumpus. So you will not be allowed to kill it.

Nevertheless, you are deployed in a maze where this horrible creature lives and you have two goals:

- get out of the maze;
- locate the room where the Wumpus dwells (this info is required by your employers).

Besides the Wumpus our maze also have several pits. If you go into the room with a pit, you will also die instantly.

However you can sense both wumpus and pits from neighboring rooms, as described below.

###Technical details

Server url for the game is [http://codeabbey.sourceforge.net/wumpus.php](http://codeabbey.sourceforge.net/wumpus.php)

The maze consists of `53` rooms and have `5` pits.

At each move you are told the number of the room where you currently are (under the
title of `room`), and the numbers of adjacent rooms to which you can go (labeled as `ways`).
Every room have exactly `3` ways out and numbers of the rooms are `0`-based. Most of the passages between rooms are
bi-directional, but not all. Also there could be more than one passage between a pair of rooms.

The exit from the maze is represented by value `-1` instead.

You should tell the server a single value - the number of the room where you want to go next (use word `move` for this).

The server also tells you (in the line labeled `sense`) whether you feel any danger or not. If the room with a pit is
near, you feel `draft`. In you are close to the room with the Wumpus, you feel its `stench`.

When you are going to leave the maze, you should also send the number of room containing wumpus (use the word `wumpus`).

**Manual mode**

In normal mode you have only `5` seconds for each move. However you can initiate the game in manual or debug mode
if you start it adding property `manual` (with any value) to your request.

In manual mode the maze has only `37` rooms and `3` pits.

However you will not get the victory token in this mode after winning the game.

**Input data** will give you the authentication token - and you need to submit the victory token as an **Answer**.

Example of dialogue with server:

    You:						Server:
	
	token: <your-token>			room: 12
	manual: true				ways: 7 16 33
								sense: safe
	
	token: <your-token>			room: 7
	move: 7						ways: 1 25 13
								sense: draft
	
	token: <your-token>			room: 13
	move: 13					ways: 36 1 -1
								sense: draft stench
	
	token: <your-token>			end: game is lost
	move: -1					message: You crawled out of the maze, but in manual mode...
	wumpus: 36

_**Note** that due to stochastic nature of initial layout sometimes maze could be too hard or impossible to solve.
Feel free to restart in such case._