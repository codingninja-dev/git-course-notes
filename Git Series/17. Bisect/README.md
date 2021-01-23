<h1 align='center'>~ Bisect ~</h1>

<p>Sometimes we work on projects for a long, long time. We might craft the perfect release, then we release it to the public and we start working on bug fixes, then we get feature requests and we work on improving the app.</p>

<p>At some point during this process you get a regression bug: an unexpected problem that is caused by an unrelated change in the code. Something is not working as expected, although you didn’t really change that part of code recently. Or maybe you touched a file or function so many times that you can’t remember what change might have caused the problem that was reported to you.</p>

<p>In any case, the first thing to do is to determine where the bug is. If you work using a versioning control system like Git, things are easier. You can go back in time and figure out the exact commit that introduced the change. When working in teams this is important because some other person might have worked on that, and if they caused the error you might not know what to do - except asking them to fix it, because Git gives you this information.</p>

<h3>Manual Process</h3>

```
$ git checkout <commit id> // it will checkout to that commit 
```

<p>If you still got the problem, you try doing the same with another commit from the day before, and so on, until you find a commit where the code works. Now you need to apply the divide and conquer principle, and pick a commit in the middle of the last one that you tried (and didn’t work) and the one that works. Repeat the process and cut in half every time the interval of commits, until you identify the commit that introduced the problem. This is such a common and useful thing that Git introduced the bisect command to automate this process.</p>

<h3>Using Git Bisect</h3>

```
$ git bisect start                   // tell git you want to start the bisect process
$ git bisect bad [HEAD or commit id] // tell git the bad commit
$ git bisect good [commit id]        // tell git the good commit
```

<p>After you run the three commands above Git will begin to find the commit that has issues. Below is something you will see.</p>

```
Bisecting: 3 revisions left to test after this (roughly 2 steps)
[d18ebf1c7db9a9b44e8facc5ddb3551e641a64e2] fixes #25
```

<p>Lets pretend you have six commits from bad to good. Git will tell you that you have 2 more steps until finding a problematic commit. Now you just have to test your code and see if the issue is present or not. Then you run the command in the bottom.</p>

```
$ git bisect bad  // run if bad
$ git bisect good // run if good
```
