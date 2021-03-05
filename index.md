## TLDR

If you want to **read something** in connection with the talks, I would recommend [Intro to Web Prolog for Erlangers](https://gup.ub.gu.se/file/207827) for the second talk, and the [chapter on SCXML and Web Prolog](https://github.com/Web-Prolog/swi-web-prolog/blob/master/book/web-prolog-and-scxml.pdf) for the fourth talk. Also, the draft [Web Prolog manual](documents/manual-draft.pdf) might be handy.

If you want to **delve deeper**, reading my manuscript [Web Prolog and the programmable Prolog Web](https://github.com/Web-Prolog/swi-web-prolog/raw/master/book/web-prolog.pdf) might also be useful. It's very much a draft lacking some of the planned chapters, but should be readable enough for those who want to know more about the ideas behind Web Prolog. (I have a much later draft, which unfortuantely has become very messy and hard to read :-( . But if you insist, I might distribute that too.)

If you want to **play with the language** and perhaps **take the tutorial** (which I really recommend) you need to install the proof-of-concept implementation. See below.


## Ecosystem: The "Holy Prolog Trinity"

![The Holy Prolog Trinity](documents/diagram.png "Optional Title")



## Marketing: Three "elevator pitches"

* Imagine a dialect of Prolog with actors and mailboxes and send and receive -- all the means necessary for powerful concurrent and distributed programming.  Alternatively, think of it as a dialect of Erlang with logic variables, backtracking search and a built-in database of facts and rules -- the means for logic programming, knowledge representation and reasoning. Also, think of it as a web logic programming language. This is what **Web Prolog** is all about.

* Imagine the Web wrapped in Prolog, running on top of a distributed architecture comprised of a network of nodes supporting HTTP and WebSocket APIs, as well as web formats such as JSON. Think of it as a high-level Web, capable of serving answers to queries -- answers that follow from what the Web "knows". Moreover, imagine it being programmable, allowing Web Prolog source code to flow in either direction, from the client to the node or from the node to the client. This is what **the Prolog Web** is all about.

* Imagine the Prolog Web populated by **Prolog Agents**. Imagine them being written in a thoroughly integrated combination of Web Prolog and StateChart XML -- two languages which come with a fair amount of formal semantics. Think of this as a way to ensure that four important aspects of web-based intelligent conversational agents -- natural language understanding, knowledge representation, reasoning and real-time interaction -- are accounted for. This is what programming languages for building such agents should be all about.


## Proof-of-concept implementation of Web Prolog

Note that this is a proof-of-concept demonstration/tutorial only. The system is _not_ yet ready for online deployment. But you can install it locally, work through the tutorial, and play with lots of code examples. Here's how to install it:

1. Install the latest [SWI-Prolog](https://www.swi-prolog.org/download/devel) for your platform. 
2. Clone or download the repo from [https://github.com/Web-Prolog/swi-web-prolog](https://github.com/Web-Prolog/swi-web-prolog)
3. From the `swi-web-prolog` directory, do `cd web-client` and then `swipl run.pl`. (There may be a few warnings, but they don't matter.)
4. Now direct your browser to [http://localhost:3060/apps/swish/index.html](http://localhost:3060/apps/swish/index.html) .



## Introductory material to traditional Prolog

To be able to follow the talks, some acquaintance with Prolog would likely help. If you're new to the language, you may want to have a look at an excellent new [online book](https://www.metalevel.at/prolog) and a series of [video lectures](https://www.metalevel.at/prolog/videos) by [Markus Triska](https://www.metalevel.at). 

You may also want to play with [SWISH](https://swish.swi-prolog.org), which is a stable online IDE for Prolog, running 24/7 and having lots of users, especially among students taking CS courses involving logic programming and Prolog. 

If you want to install SWI-Prolog locally, and check out the user forum, these are the links:

- [SWI-Prolog](https://www.swi-prolog.org)
- [SWI-Prolog user's forum](https://swi-prolog.discourse.group)



## Links to written material

- [Intro to Web Prolog for Erlangers](https://gup.ub.gu.se/file/207827)
- [Web Prolog and the programmable Prolog Web](https://github.com/Web-Prolog/swi-web-prolog/raw/master/book/web-prolog.pdf)
- [Chapter on SCXML and Web Prolog](https://github.com/Web-Prolog/swi-web-prolog/blob/master/book/web-prolog-and-scxml.pdf)
- [Web Prolog manual](documents/manual-draft.pdf)
- [ISO Prolog: A Summary of the Draft Proposed Standard](http://fsl.cs.illinois.edu/images/9/9c/PrologStandard.pdf)
- [ISO Prolog Threads](https://logtalk.org/plstd/threads.pdf)
- [Lots of useful Prolog references](https://swi-prolog.discourse.group/t/useful-prolog-references/1089)
- [David Harel's seminal paper on Statechart](http://www.wisdom.weizmann.ac.il/~harel/SCANNED.PAPERS/Statecharts.pdf)
- [The SCXML standard](https://www.w3.org/TR/scxml)
- [Make Prolog Great Again!](https://github.com/Web-Prolog/swi-web-prolog/blob/master/book/web-prolog-marketing.pdf)
- [Radomski, et al. - A Prolog Datamodel for State Chart XML](https://www.aclweb.org/anthology/W13-4019.pdf)
- [Junger, et al. - SCXML for Building Conversational Agents in the Dialog Web Lab](documents/sltc2010.pdf)


## Links to videos

- [Video lectures on Prolog](https://www.metalevel.at/prolog/videos) by [Markus Triska](https://www.metalevel.at).
- [Panel discussion: Joe Armstrong, Carl Hewitt and Tony Hoare on concurrent and distributed programming](https://www.youtube.com/watch?v=37wFVVVZlVU)
- [Erlang Master classes](https://www.cs.kent.ac.uk/ErlangMasterClasses). A great way to learn Erlang, but you can probably skip Master class 1. 

 

