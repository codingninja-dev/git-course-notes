<h1 align='center'>~ Undoing Changes ~</h1>

<p>One of the most useful features of any version control system is the ability to "undo" your mistakes. In Git, "undo" can mean many slightly different things.</p>

<p>There are several ways we can go about undoing changes in Git.</p>

<ul>
  <li>git checkout</li>
  <li>git clean</li>
  <li>git revert</li>
  <li>git reset</li>
  <li>git remove</li>
</ul>

<h3>Git Checkout</h3>

<p>The "checkout" command can switch the currently active branch. However, it can also be used to restore files. The most common use case for "checkout" is when you want to switch to a different branch, making it the new HEAD branch. Another use case for "checkout" is when you want to restore a historic version of a specific file. Thereby, you can reset single files to earlier revisions - while keeping the rest of the project untouched.</p>

```
$ git checkout -- app.js
```

<p>Basically git is taking the app.js file that is on your current branch and replaces the app.js file you have made changes to. If you want to replace your file with the same file from a different branch you can use the format below.</p>

```
// git checkout <tree-ish> -- <pathspec>
$ git checkout featurebranch -- app.js
```

<h3>Git Revert</h3>

<p>The "revert" command helps you undo an existing commit. It's important to understand that it does not delete any data in this process: instead, Git will create new changes with the opposite effect and thereby undo the specified old commit. This is used more often over the git reset due to the fact that it keeps your git history intact by creating a new commit. This is best for commits already made public to others.</p>

```
$ git revert <commit id>
```

<p>After running git revert it will create a new commit that’s the opposite (or inverse) of the given commit id. Anything removed in the old commit will be added in the new commit and anything added in the old commit will be removed in the new commit.</p>

<h3>Git Reset</h3>

<p>The git reset command allows you to RESET your current head to a specified state. You can reset the state of specific files as well as an entire branch. This is useful if you haven't pushed your commit up to GitHub or another remote repository yet.</p>

<p>To reset the first commit you can use "reset HEAD~1" to remove the first commit. HEAD~1 is shorthand case for "the commit right before HEAD"</p>

```
$ git reset HEAD~1
```

<p>There are three parameters you can pass to reset.</p>

<ul>
  <li>soft</li>
  <li>mixed</li>
  <li>hard</li>
</ul>

<h4>Reset with Soft mode</h4>

<p>The --soft parameter tells Git to reset HEAD to another commit, but that’s it. If you specify --soft Git will stop there and nothing else will change. What this means is that the staging area and working directory don’t get touched, so all of the files that changed between the original HEAD and the commit you reset to appear to be staged.</p>

```
$ git reset --soft HEAD~1
```

<h4>Reset with Mixed mode</h4>

<p>The --mixed parameter (which is the default if you don’t specify anything) will reset HEAD to another commit, and will reset the staging area to match it, but will stop there. The working directory will not be touched. So, all of the changes between the original HEAD and the commit you reset to are still in the working directory and appear as modified, but not staged.</p>

```
$ git reset HEAD~1
$ git reset --mixed HEAD~1
```

<h4>Reset with Hard mode</h4>

<p>The --hard parameter will blow out everything – it resets HEAD back to another commit, resets the staging area to match it, and resets the working directory to match it as well. This is the more dangerous of the commands and is where you can cause damage. </p>

```
$ git reset --hard HEAD~1
```

<h3>Git Clean</h3>

<p>The clean command is one of Git's many "undo" tools. Compared to reset or revert, which are also classic undo commands, git clean is different: it targets untracked files that haven't been added to version control, yet.</p>

```
$ git status
On branch master

Changes not staged for commit:
  (use "git add ..." to update what will be committed)
  (use "git restore ..." to discard changes in working directory)
      modified:   html.html

Untracked files:
  (use "git add ..." to include in what will be committed)
      app.js
```

<p>Whatever options and parameters you provide: using git clean will only affect untracked files - in our example app.js - and leave anything else untouched.</p>

<p>Before you use git clean to delete untracked files, you should remember an important detail: untracked files, by definition, aren't included in version control - and this means that when you delete them, you will not be able to restore them! This is why the first step when approaching git clean is to make use of its "dry run" functionality using the "-n" flag:</p>

```
$ git clean -n
Would remove app.js
```

<p>"Dry run" means that Git will not actually perform any deletions, but it only tells you which files would be deleted. If this looks correct, you can proceed without the safety catch.</p>

<p>To actually allow git clean to delete files in your working copy, you'll have to use the "force" option:</p>

```
$ git clean -f
```

<p>By default, folders themselves will no be deleted. If you want to include them, you can use the "-d" flag:</p>

```
git clean -fd
```

<h3>Git Remove</h3>

<p>The "rm" command helps you to remove files from a Git repository. It allows you to not only delete a file from the repository, but also from the filesystem. Deleting a file from the filesystem can of course easily be done in many other applications, e.g. a text editor, IDE or file browser. But deleting the file from the actual Git repository is a separate task, for which git rm was made.</p>

<p>To remove a file both from the Git repository and the filesystem, you can use git rm without any parameters:</p>

```
git rm app.js
```

<p>If you only want to remove the file from the repository, but keep it on the filesystem, you can add the --cached flag:</p>

```
$ git rm app.js --cached
```

<p>When trying to delete multiple files in a directory, you might want to perform a "dry-run" first and see which files would be removed:</p>

```
$ git rm app.js index.html --dry-run
rm 'app.js'
rm 'index.html'
```
