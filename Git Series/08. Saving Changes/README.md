<h1 align='center'>~ Saving Changes ~</h1>

<p>There are two way of saving your changes in Git.</p>

<ul>
  <li>git commit</li>
  <li>git stash</li>
</ul>

<h3>Git Commit</h3>

<p>Git commit allows you to record your changes to the repository. This means that any updates such as file changes or new files gets recorded in the repository history.</p>

<p>Note that you have to explicitly tell Git which changes you want to include in a commit before running the "git commit" command. This means that a file won't be automatically included in the next commit just because it was changed. Instead, you need to use the "git add" command to mark the desired changes for inclusion.</p>

<ul>
  <li><b>git add</b>: takes a modified file in your working directory and places the modified version in a staging area.</li>
  <li><b>git commit</b>: takes everything from the staging area and makes a permanent snapshot of the current state of your repository that is associated with a unique identifier.</li>
</ul>

<img src="https://www.earthdatascience.org/images/earth-analytics/git-version-control/git-add-commit.png">

```
$ git add index.html            // add one file
$ git add index.html styles.css // add multiple file
$ git add .                     // add all files
```

```
$ git commit                          // will open a editor to add message and commit
$ git commit -m "change html file"    // '-m' for adding message
$ git commit -a -m "change html file" // '-a' for adding all file and '-m' for adding message
```

<p>Did you forget to include something in your last commit message? Did you make a typo? Did you add something into your commit message that is not relevant? To update a commit message or add new changes to your commit you can use the command below.</p>

```
// can be used to add any new changes to your commit

$ git commit --amend              // change the commit message with editor
$ git commit --amend -m 'changes' // change the commit message in line
$ git commit --amend --no-edit    // without changing commit message
```

<p>The git commit –amend command modifies your latest commit. This command lets you change files in your last commit or your commit message. Your old commit is replaced with a new commit that has its own ID. This command is useful because it allows you to undo changes without having to create a new commit. Creating a new commit to undo changes would make the history of a repository less clear. You’d only be reverting a mistake and that does not usually need a commit of its own. Amending a commit does not just change a commit. It replaces it with a new commit which will have its own ID. You can only modify the last commit in your repository, which is referred to as a Git HEAD.</p>

<h3>Git Stash</h3>

<p>Git stashing is used to clean and save a copy of your working directory so that you can have a clean state to work with. Everything that is stashed can be placed back in the repository. It gives you the ability to quickly save or stash away your changes and then apply them back to the repository later.</p>

```
$ git stash                 // stash your current changes
$ git stash list            // get a list of all your stashes
$ git stash pop             // retrieve most recent stash and remove from list
$ git stash pop stash@{1}   // retrieve stash@{1} and remove from list
$ git stash drop            // remove most recent from list
$ git stash drop stash@{1}  // remove stash@{1} from list
$ git stash apply           // retrieve most recent stash and keep in the list
$ git stash apply stash@{1} // retrieve stash@{1} and keep in the list
$ git stash clear           // remove all stashes
```
