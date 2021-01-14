<h1 align='center'>~ Version Control System (VCS) ~</h1>

<h3>Drawback of not using VCS</h3>
<p>When you work alone on a document, the latest is usually the greatest: you successively open the document, make changes, and save the document. Each time you save, you overwrite the existing copy. The situation is different when you are working with a large, globally distributed team on a project consisting of hundreds, or even thousands, of files. In this case, it is important to track authorship and changes, and to resolve conflicts when users make conflicting changes to the same file. Version control systems allow you to do this. You can track and manage changes to any large collection of digital assets: documents, source code, web sites, audio files, and so on.</p>

<h3>Benefits of VCS</h3>

<p>One technique of version control systems is versioning. Rather than overwriting earlier versions of a file when it is saved, each saved copy of the file is versioned and assigned a number or letter that reflects the order in which it was saved.</p>
<p>In addition to identifying a file version within a sequence of versions, a version control system automatically associates certain information with each version: it records who made the change, when the change was made, and why the change was made. This information provides an audit trail that you can always consult to understand how a project developed and when specific changes were made. Because no version of a file is overwritten, when bugs arise, it is possible to identify the point at which the bug was introduced. This can be critical in fixing bugs that cannot be reproduced. In addition, looking at file history and understanding why certain decisions were made can help project participants stay on track or find appropriate options for future directions.</p>
<p>Sharing data under version control requires a certain amount of gatekeeping to determine who can access the data and how conflicts are resolved when two users make changes to the same file. To support this gatekeeping function, version control systems introduce the additional step of checking out a file and checking in or submitting a file.</p>

<h3>VCS General Workflow</h3>
<p>The basic version control workflow looks like this:</p>

<ul>
  <li>Assets under version control are placed in a specified repository</li>
  <li>Assets are associated with specific permissions that enable users to read or modify them</li>
  <li>A user checks out a working copy of an asset and makes changes</li>
  <li>Another user checks out a working copy of the same asset and makes changes</li>
  <li>The first user saves changes to the local working copy and checks in that copy</li>
  <li>The second user saves changes to the local working copy and attempts to check in that copy</li>
  <li>The version control system detects the fact that the same asset was changed in parallel, and it asks the second user to merge changes with those of the first user before the second user’s changes can be checked in. The work of comparing and merging changes is called resolving</li>
</ul>

<p>In this way, the version control system makes sure that changes are predictable, manageable, and auditable.</p>

<h3>Types of VCS</h3>
<p>Version control systems are traditionally either centralized or distributed:</p>

<ul>
  <li>Centralized version control systems use a single repository from which users check out one or more files to work on locally (SVN)</li>
  <li>Distributed version control systems allow users to host repositories locally, check out entire repositories with all history (Git)</li>
</ul>
