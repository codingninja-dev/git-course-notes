<h1 align='center'>~ Inspecting Repository ~</h1>

<p>Inspecting a repository is a great way to see file tracking information and history information. There are two commands below that are used.</p>

<ul>
  <li>git status</li>
  <li>git log</li>
</ul>

<h3>Git Status</h3>

<p>You can inspect a Git repository by using the git status command. This command allows you to see which changes have been staged, which haven’t, and which files aren’t being tracked by Git. The git status command is a pretty straightforward Git command. Basically, it shows what has been going on with git add and git commit.</p>

```
$ git status
```
<h4>No Changes</h4>

```
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

<h4>Untracked File</h4>

```
$ git status
On branch master
Untracked files:
(use “git add <file>…” to include in what will be committed)

app.js
```

<h4>File with Changes (Not Staged)</h4>

```
$ git status
On branch master
Changes not staged for commit:
(use “git add <file>…” to update what will be committed)
(use “git checkout — <file>…” to discard changes in working directory)

modified: app.js
```

<h4>File with Changes (Staged)</h4>

```
$ git status
On branch master
Changes to be committed:
(use “git reset HEAD <file>…” to unstage)

modified: app.js
```

<h3>Git Log</h3>

<p>You should try and remember that status output does not show you any information regarding the committed project history. For this, you need to use the git log command. The git log command displays committed snapshots. The command will allow you to list the project history, filter it, and search for specific changes.</p>

```
$ git log
```

<h4>Git log with Parameter</h4>

```
$ git log --oneline          // show in oneline
$ git log -2                 // limit commit output to two
$ git log --author="Adam"    // show commits changed by the person
$ git log --committer="Adam" // show commits made by the person
```
