### The Prolog Trinity talk

If you want to **read something** in connection with my talk, I would recommend [Intro to Web Prolog for Erlangers](https://gup.ub.gu.se/file/207827) for the second talk, and the [chapter on SCXML and Web Prolog](https://github.com/Web-Prolog/swi-web-prolog/blob/master/book/web-prolog-and-scxml.pdf) for the fourth talk. Also, the draft [Web Prolog manual](documents/manual-draft.pdf) might be handy.

If you want to **delve deeper**, reading my manuscript [Web Prolog and the programmable Prolog Web](https://github.com/Web-Prolog/swi-web-prolog/raw/master/book/web-prolog.pdf) might also be useful. It's very much a draft lacking some of the planned chapters, but should be readable enough for those who want to know more about the ideas behind Web Prolog. (I have a much later draft, which unfortuantely has become very messy and hard to read :-( . But if you insist, I might distribute that too.)

If you want to **play with the language** and perhaps **take the tutorial** (which I really recommend) you need to install the proof-of-concept implementation. See below.


### Links to written material

- [Parts of two chapters from my draft manuscript](parts-of-chapter-2-and-3.pdf)
- [An appendix containing the draft Web Prolog manual](documents/manual-draft.pdf)
- [Another appendix with a thorough explanation of how the PoC is implemented](how-to-implement-a-node.pdf)


### Proof-of-concept implementation of Web Prolog written for clarity

Proof-of-concept implementations of Web Prolog have been written before (and I link to one of them below), but they have been complex in a way that has tended to hide its most essential features. This is the first PoC that has been written for optimal understandability in mind, which should make it easier to implement Web Prolog in Prolog systems other than SWI-Prolog. It does mean, however, that it is also less complete, and does not, for example, implement the `node` option or the `load_*` options.

Here's how to install the PoC, run the tests, play with the stateless HTTP API, and do some Erlang-style programming in Web Prolog:

1. Install the latest [SWI-Prolog](https://www.swi-prolog.org/download/devel) for your platform.
2. Source code for the PoC is [here](src/trinity-poc.zip), in a zip-file. 
3. Unzip and do
   ```
   $ cd trinity-poc
   ```
   and then 

   ```
   $ swipl trinity.pl
   ```

4. Tests are available in the same directory. Just do

   ```
   ?- [trinity_tests]. 
   ``` 
   and then run:

   ```
   ?- test.
   ``` 
   The tests should all pass.

5. To run a node with its stateless HTTP API, you need to do:

   ```text
   ?- node(3010).
   % Started server at http://localhost:3010/
   true.
   ?- 
   ``` 

   **Warning: Do not expose the node to the whole world at this point, as it is not secure!**

   You may want to take the node's stateless HTTP API for a trial run by selecting (or just entering) the following URI in a web browser:


   [http://localhost:3010/call?goal=member(X,[a,b])&format=prolog](http://localhost:3010/call?goal=member(X,[a,b])&format=prolog)

   In the browser's window, you should then see the following:

   ```
   success([member(a,[a,b]),member(b,[a,b])],false)
   ```

   Then try this:


   [http://localhost:3010/call?goal=member(X,[a,b])&template=X&offset=0&limit=1&format=prolog](http://localhost:3010/call?goal=member(X,[a,b])&template=X&offset=0&limit=1&format=prolog)



   and you should see

   ```
   success([a],true)
   ```

   Then this, where offset is set to `1`:


   [http://localhost:3010/call?goal=member(X,[a,b])&template=X&offset=1&limit=1&format=prolog](http://localhost:3010/call?goal=member(X,[a,b])&template=X&offset=1&limit=1&format=prolog)


    and you should see

   ```text
   success([b],false)
   ```

   From you Prolog prompt, you should also be able to test `rpc/2-3`, like so:

   ```text
   ?- rpc('http://localhost:3010', member(X,[a,b])).
   X = a ;
   X = b.
   ?-
   ```
   and so:

   ```text
   ?- rpc('http://localhost:3010', member(X,[a,b]),[limit(1)]).
   X = a ;
   % New HTTP request from offset 1
   X = b.
   ?-
   ```

   Here is a test that shows that the spurious recomputation is eliminated:  

   ```text
   ?- time(rpc('http://localhost:3010', (sleep(1), X=foo ; X=bar), [limit(1)])).
   % 2,040 inferences, 0.001 CPU in 1.006 seconds (0% CPU, 1485798 Lips)
   X = foo ;
   % New HTTP request from offset 1
   % 1,861 inferences, 0.001 CPU in 0.004 seconds (23% CPU, 1975584 Lips)
   X = bar.
   ?- 
   ```

   If you want to test the naive implementation of the HTTP API (the one you may be able to implement in Scryer Prolog at this point in time) you need to replace `compute_answer/5` with two lines (see ≈ line 590). If you do, note that computing the solution `X=bar` will take just as long as computing the solution `X=foo` since spurious recomputations are no longer eliminated.

6. Your Prolog top-level can be used as a shell. Try this for example:

   ```text
   ?- toplevel_spawn(Pid, [
          monitor(true)
      ]).
   Pid = '42103437'.
   
   ?- toplevel_call($Pid, between(1,5,I), [
          template(I),
          limit(2)
      ]).
   Pid = '42103437'.
   
   ?- flush.
   Shell got success('42103437',[1,2],true)
   true.
   
   ?- toplevel_next($Pid,[
          limit(10)
      ]).
   Pid = '42103437'.
   
   ?- flush.
   Shell got success('42103437',[3,4,5],false)
   Shell got down('42103437',true)
   true.
   
   ?- 
   ```
  
   You'll find a lot more examples in the draft chapters linked above, and most of the examples that work in the PoC is also included in the file `trinity_tests.pl`.
   
   Examples that do **not** work:
   
   1. Examples that use the `node` option,
   2. examples that use the `load_*` options,
   3. and probably a few others...




### Links to videos about Erlang, from which Erlang-style programming in Web Prolog can also be learned:

- [Panel discussion: Joe Armstrong, Carl Hewitt and Tony Hoare on concurrent and distributed programming](https://www.youtube.com/watch?v=37wFVVVZlVU)
- [Erlang Master classes](https://www.cs.kent.ac.uk/ErlangMasterClasses). A great way to learn Erlang-style concurrent programming. If you are at all familiar with functional programming, you can probably skip Master class 1.