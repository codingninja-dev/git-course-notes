<h1 align='center'>~ Gitignore File ~</h1>

<p>The .gitignore file is a text file that tells Git which files or folders to ignore in a project. A local .gitignore file is usually placed in the root directory of a project.</p>

<p>To create a local .gitignore file, create a text file and name it .gitignore (remember to include the . at the beginning). Then edit this file as needed. Each new line should list an additional file or folder that you want Git to ignore.</p>

<h3>Matching Pattern for Gitignore File</h3>

<ul>
  <li>* is used as a wildcard match</li>
  <li>/ is used to ignore pathnames relative to the .gitignore file</li>
  <li># is used to add comments to a .gitignore file</li>
</ul>

```
# Ignore Mac system files
.DS_store

# Ignore node_modules folder
node_modules

# Ignore all text files
*.txt

# Ignore files related to API keys
.env

# Ignore SASS config files
.sass-cache
```

<h3>Global Gitignore File</h3>

```
git config --global core.excludesfile ~/.gitignore_global
```
<p>This will create the file ~/.gitignore_global in your computer's home directory. Now you can edit that file the same way as a local .gitignore file. All of your Git repositories will ignore the files and folders listed in the global .gitignore file.</p>
