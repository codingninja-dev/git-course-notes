<h1 align='center'>~ Rewrite History ~</h1>

<p>There are two ways to rewrite history in Git.</p>

<ul>
  <li>git commit amend</li>
  <li>git rebase</li>
</ul>

<h3>Git Commit Amend</h3>

<p>One of the simplest history rewrites we can do with git is changing the last commit message. Let’s say right after making a commit you find a typo in its description, or you find a better way of describing the changeset.</p>

```
$ git commit --amend
```

<p>It will open an editor with the last commit message, so you can modify it. After saving, a new commit will be created with the same changes and the new message, replacing the commit with the previous message. This can be useful to include files you forgot to track, or include modifications to the files you just commited.</p>

```
$ git add app.js
$ git commit --amend --no-edit 
```

<h3>Git Rebase</h3>

<p>Rebasing a branch in Git is a way to move the entirety of a branch to another point in the tree. The simplest example is moving a branch further up in the tree.</p>

<img src="https://cdn-images-1.medium.com/max/2404/1*FNaZp740nmp8wz851BqcAg.png">

<p>To rebase, make sure you have all the commits you want in the rebase in your master branch. Check out the branch you want to rebase and type git rebase master (where master is the branch you want to rebase on).</p>

```
$ git rebase master
```

<h4>Interactive Rebasing</h4>

<p>Interactive rebasing can be used for changing commits in many ways such as editing, deleting, and squashing. To tell Git where to start the interactive rebase, use the commit id or index of the commit that immediately precedes the commit you want to modify. Interactive rebasing will create new commit from old commit therefore it is best to use interactive rebasing on commits you have not pushed to a remote branch.</p>

```
$ git rebase -i HEAD~6
```

<img src="https://blog.verslu.is/wp-content/uploads/2020/01/InteractiveRebase-1536x852.png">
