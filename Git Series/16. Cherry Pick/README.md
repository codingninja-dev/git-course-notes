<h1 align='center'>~ Cherry Pick ~</h1>

<p>When you are working with a team of developers on a medium to large sized project, managing the changes between a number of git branches can become a complex task. Sometimes you don't want to merge a whole branch into another, and only need to pick one or two specific commits. This process is called 'cherry picking'.</p>

<h3>How do I cherry pick a commit in Git?</h3>

<p>In Git, the cherry pick command takes changes from a target commit and places them on the HEAD of the currently checked out branch.</p>

<h3>When should I use the Git cherry pick command?</h3>

<p>The cherry pick command can be helpful if you accidentally make a commit to the wrong branch. Cherry picking allows you to get those changes onto the correct branch without redoing any work.</p>

<h3>What’s the difference between cherry picking and merging in Git?</h3>

<p>Cherry picking is one method of moving a commit from one branch to another in Git. But be warned! Use the cherry pick command sparingly as overusing it can lead to duplicate commits and a messy repo history. Another method for moving a commit to another branch in Git—which may be preferred to cherry pick in order to preserve commit history—is a merge.</p>

```
git cherry-pick d467740         // Cherry pick one commit
git cherry-pick d467740 de906d4 // Cherry pick more than one commit
git cherry-pick --continue      // If it gets halted because of conflicts, resolve them and continue
git cherry-pick --abort         // If you want to abort the cherry pick process
```
