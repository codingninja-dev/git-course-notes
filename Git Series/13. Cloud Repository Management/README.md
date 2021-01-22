<h1 align='center'>~ Cloud Repository Management ~</h1>

<p>There are a few commands that allows us to start working with a cloud repository such as Github and Bitbucket.</p>

<ul>
  <li>git remote</li>
  <li>git fetch</li>
  <li>git pull</li>
  <li>git push</li>
</ul>

<h3>Git Remote</h3>

<p>The "remote" command helps you to manage connections to remote repositories. It allows you to show which remotes are currently connected, but also to add new connections or remove existing ones.</p>

```
$ git remote -v                                  // list of all remote repositories
$ git remote add [remote name] [repository link] // add a new remote repository
$ git remote rm [name]                           // remove a remote repository
$ git remote rename [old name] [new name]        // rename remote repository
```

<h3>Git Fetch</h3>

<p>This command fetches the latest code commits from the remote and places them only in the local repository. The working directory and staging area remain unchanged. This option is for those who want to first check what is the latest code changes that are made by their fellow developers by checking the diff between their working copy and the local repository. Once they are satisfied with the changes, they will merge the local repository with the working copy using the merge command.</p>

```
$ git fetch
```

<h3>Git Pull</h3>

<p>This command fetches the latest code commits from the remote and merges it with your local branch.</p>

```
$ git pull          // pull all your changes
$ git pull --rebase // rebase all your changes on top of your pulled changes
```

<h3>Git Push</h3>

<p>This command takes all the commit history you have made that is not in your remote repository and pushes the changes to it.</p>

```
$ git push    // push all your commit history to the remote repository
$ git push -f // force push all your commit history to the remote repository overwriting it.
```
