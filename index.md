## TLDR

If you want to **read something** in connection with the talks, I would recommend [Intro to Web Prolog for Erlangers](https://gup.ub.gu.se/file/207827) for the second talk, and the [chapter on SCXML and Web Prolog](https://github.com/Web-Prolog/swi-web-prolog/blob/master/book/web-prolog-and-scxml.pdf) for the fourth talk. Also, the draft [Web Prolog manual](documents/manual-draft.pdf) might be handy.

If you want to **delve deeper**, reading my manuscript [Web Prolog and the programmable Prolog Web](https://github.com/Web-Prolog/swi-web-prolog/raw/master/book/web-prolog.pdf) might also be useful. It's very much a draft lacking some of the planned chapters, but should be readable enough for those who want to know more about the ideas behind Web Prolog. (I have a much later draft, which unfortuantely has become very messy and hard to read :-( . But if you insist, I might distribute that too.)

If you want to **play with the language** and perhaps **take the tutorial** (which I really recommend) you need to install the proof-of-concept implementation. See below.


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



## Links to videos

- [Video lectures on Prolog](https://www.metalevel.at/prolog/videos) by [Markus Triska](https://www.metalevel.at).
- [Panel discussion: Joe Armstrong, Carl Hewitt and Tony Hoare on concurrent and distributed programming](https://www.youtube.com/watch?v=37wFVVVZlVU)
- [Erlang Master classes](https://www.cs.kent.ac.uk/ErlangMasterClasses). A great way to learn Erlang, but you can probably skip Master class 1. 

 

