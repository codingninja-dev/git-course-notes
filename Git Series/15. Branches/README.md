<h1 align='center'>~ Branches ~</h1>

<img src="http://cr103.com/collections/Trees/wideangle_tree.jpg">

<p>Picture this tree as a Git repository. It has a lot of branches, long and short, stemming from the trunk and stemming from other branches. Let's say the tree's trunk represents a master branch of our repo. I will use master in this article as an alias for "master branch"—i.e., the central or first branch of a repo. To simplify things, let's assume that the master is a tree trunk and the other branches start from it.</p>

<h3>Why we need branches in a Git repo</h3>

<ul>
  <li>If you are creating a new feature for your project, there's a reasonable chance that adding it could break your working code. This would be very bad for active users of your project. It's better to start with a prototype, which you would want to design roughly in a different branch and see how it works, before you decide whether to add the feature to the repo's master for others to use.</li>
  <li>Another, probably more important, reason is Git was made for collaboration. If everyone starts programming on top of your repo's master branch, it will cause a lot of confusion. Everyone has different knowledge and experience (in the programming language and/or the project); some people may write faulty/buggy code or simply the kind of code/feature you may not want in your project. Using branches allows you to verify contributions and select which to add to the project. (This assumes you are the only owner of the repo and want full control of what code is added to it. In real-life projects, there are multiple owners with the rights to merge code in a repo.)</li>
</ul>

<img src="https://www.nobledesktop.com/image/gitresources/git-branches-merge.png">

<h3>Viewing, Creating, and Deleting Branches</h3>

```
$ git branch                          // show all branches
$ git branch my-project               // create new branch called my-project
$ git branch -d my-project            // safe delete branch my-project
$ git branch -D my-project            // force delete branch my-project
$ git branch -a                       // show all remote branch
$ git push origin --delete my-project // delete remote branch
```

<h3>Checking Out Branches</h3>

<p>The git checkout command lets you navigate between the branches created by git branch. Checking out a branch updates the files in the working directory to match the version stored in that branch, and it tells Git to record all new commits on that branch.</p>

```
$ git checkout my-project    // move to that branch
$ git checkout -b my-project // create a branch and move to that branch
```
<p>The two commands below does the same thing.</p>

```
$ git branch my-project 
$ git checkout my-project
```

<p>same as</p>

```
$ git checkout -b my-project
```

<h3>Merging changes from one branch to another branch</h3>

<p>Separating different topics into different branches is a crucial practice for any serious developer. By not mixing up code from a feature, bugfix, or experiment code with another, you avoid a lot of problems - and don't have to worry about breaking things in your development branches. But at some point your code will (hopefully) reach a state where you'll want to integrate it with the rest of the project. This is where the "git merge" command comes in.</p>

<img src="https://i.stack.imgur.com/83JeN.png">

<p>Let say say you are working on my project branch and you have completed your feature and want to move it back into the master branch you can run the below command to get your changes merged in.</p>

```
$ git checkout master  // We checkout to the master branch
$ git pull             // Make sure to get all the changes from remote repository master branch
$ git merge my-project // We merge the my-project changes into your master branch
```

<h3>Dealing with Merge Conflicts</h3>

<p>Git will do what it can to make merging as easy as in our example. And in many cases, a merge will indeed be a walk in the park. In some cases, however, the integration will not go as smoothly: if the branches contain incompatible changes, you will have to face (and solve) a "merge conflict".</p>

```
Auto-merging [filename1]
CONFLICT (content): Merge conflict in [filename1]
Automatic merge failed; fix conflicts and then commit the result.
```

```
$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add ..." to mark resolution)
  both modified: [filename]
no changes added to commit (use "git add" and/or "git commit -a")
```

<p>If you go to the file that was stated above you should see something similar to the below.</p>

```
<<<<<<< HEAD
This is an edit on the master branch
=======
This is an edit on the my-project branch
>>>>>>> my-project
```

<p>If you and another contributer make the same changes on the same file and line of code you will face merge conflicts.</p>

<p>As you can see, Git added some syntax including seven "less than" characters, <<<<<<< and seven "greater than" characters, >>>>>>>, separated by seven equal signs, =======. These can be searched using your editor to quickly find where edits need to be made.</p>

<ul>
  <li>The "less than" characters denote the current branch's edits (in this case, "HEAD," which is another word for your current branch), and the equal signs denote the end of the first section.</li>
  <li>The second section is where the edits are from the attempted merge; it starts with the equal signs and ends with the "greater than" signs.</li>
</ul>

<p>As a developer, you decide what stays and what goes. Make your edits as necessary, then close the file:</p>

```
This is an edit on the my-project branch
```

```
$ git status
On branch master
All conflicts fixed but you are still merging.
(use "git commit" to conclude merge)

Changes to be committed:
modified: [filename]
```

<p>After you have completed and saved. You can run the below command.</p>

```
$ git commit
[master 9937ca4] Merge branch 'branch name'
```
