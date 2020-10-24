# Web Prolog

## Introductory material to Prolog

To be able to follow the talks, some acquaintance with Prolog is likely required. If you're new to Prolog, you may want to have a look at an excellent new [online book](https://www.metalevel.at/prolog) and a series of [video lectures](https://www.metalevel.at/prolog/videos) by [Markus Triska](https://www.metalevel.at). [SWISH](https://swish.swi-prolog.org) is an online IDE for Prolog that can be used for solving excercises. I'll be available for online consultation if needed.

You may also want to have a look at SWISH (https://swish.swi-prolog.org/) which is a stable online IDE for Prolog, running 24/7 and having lots of users, especially among students taking CS courses involving logic programming and Prolog. 

One of my long term goals is to replace the SWISH back-end with a Web Prolog node.


[ISO Prolog: A Summary of the Draft Proposed Standard](http://fsl.cs.illinois.edu/images/9/9c/PrologStandard.pdf)


## Proof-of-concept implementation of Web Prolog

This is a proof-of-concept demonstration/tutorial only. The system is _not_ yet ready for online deployment. But you can install it locally, work through the tutorial, and play with lots of code examples.

Design and implementation by Torbjörn Lager, with a _lot_ of help from Jan Wielemaker. 


### Installation

1. Install the latest [SWI-Prolog](https://www.swi-prolog.org/download/devel) for your platform. 

2. Clone or download the repo from [https://github.com/Web-Prolog/swi-web-prolog](https://github.com/Web-Prolog/swi-web-prolog)

3. From the `swi-web-prolog` directory, do `cd web-client` and then `swipl run.pl`. (There may be a few warnings, but they don't matter.)

4. Now direct your browser to [http://localhost:3060/apps/swish/index.html](http://localhost:3060/apps/swish/index.html) .

## Draft manuscripts and other documents

A book manuscript describing the approach is available [here](https://github.com/Web-Prolog/swi-web-prolog/raw/master/book/web-prolog.pdf).

It is very much a draft lacking some of the planned chapters, but should be readable enough for those who want to know more about the ideas behind Web Prolog.

[Draft Web Prolog manual](documents/manual-draft.pdf)


## Papers


[Intro to Web Prolog for Erlangers](https://gup.ub.gu.se/file/207827)


[Lots of useful Prolog references](https://swi-prolog.discourse.group/t/useful-prolog-references/1089)
