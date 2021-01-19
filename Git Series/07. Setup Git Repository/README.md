<h1 align='center'>~ Setup Git Repository ~</h1>

<p>When starting a new project, one of the first things you'll find yourself needing to do is creating a new Git repository.</p>

<p>There are two ways to get a repository up and running below:</p>

<ul>
  <li>Creating a Repository for Scratch or Existing Project</li>
  <li>Cloning an Existing Project</li>
</ul>

<h3>Creating a Repository for Scratch or Existing Project</h3>
<p>Creating a repository for a new project is virtually the same process as creating a repository for an existing project.</p>

```
$ git init
Initialized empty Git repository in /Users/Adam/Desktop/projects/my-new-project/.git/
```

<h3>Cloning an Existing Project</h3>
<p>Although you aren't technically creating a new repo, in this use-case you can clone an existing one, preventing you from needing to git init one yourself. This is very common for when you're needing to make updates to an existing project, or maybe if you want to clone a skeleton project to help get you started.</p>

```
$ git clone git@github.com:Adam/test-project.git
Cloning into 'my-new-project'...
remote: Enumerating objects: 48, done.
remote: Total 48 (delta 0), reused 0 (delta 0), pack-reused 48
Receiving objects: 100% (48/48), 9.35 KiB | 0 bytes/s, done.
Resolving deltas: 100% (22/22), done.
```
