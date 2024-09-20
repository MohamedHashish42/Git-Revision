
 <H2 dir="rtl" align="center">
بسم الله الرحمن الرحيم
</h2>

# Git Revision

This revision is designed to provide a concise overview of Git, including basic and some advanced concepts, and some of best practices for using Git in real-world scenarios. It is intended for developers, software engineers, and anyone interested in using Git to manage their code and collaborate with others. 

**Revision Content**  

1. [Getting Started](#GettingStarted)
2. [Git Basics](#Basics)
3. [Git Branching](#Branching)
4. [Git on the Server](#GitOnTheServer)
5. [GitHub](#GitHub)
6. [Git Tools](#GitTools)
7. [Customizing Git](#CustomizingGit)
8. [Some Git best practices](#GitBestPractices)
9. [Some git comparisons](#GitComparisons)
10. [Some useful git extensions in VS Code](#GitExtensionsInVSCode)
11. [References](#References)

---
## Section 1: Getting Started ?<a id="GettingStarted"></a>

### Important Definitions
- **Version control :** a system that records changes to a file or set of files over time, allowing you to recall specific versions later.  
- **Distributed version control :** a version control system where every user has a complete copy of the repository, instead of relying on a central server.  
- **Working directory :** the directory on your local machine where you are currently working on files in a Git repository.  
- **Repository :**  is a collection of files and directories that are tracked by Git.

### Important Points
- Git is a <b>distributed version control</b> system designed for speed, data integrity, and support for distributed, non-linear workflows.
- Git stores data as <b>snapshots</b> of the entire repository at particular points in time.
- Git has three main states for files: <b> committed, modified, and staged</b>.
- Git has a command-line interface as well as graphical user interface tools.
### Commands
| Command | Description |
| - | - |
| `git init`                      |initializes a new Git repository |
| `git clone [url]`               | clones a remote repository to your local machine |
| `git config --global user.name "Your Name"`              | sets your name for Git |
| `git config --global user.email "youremail@example.com" ` | sets your email for Git |

<br><br>

---

## Section 2: Git Basics <a id="Basics"></a>
### Important Definitions
- **Commit :** a snapshot of the repository at a particular point in time.
- **SHA-1 :** a cryptographic hash function used by Git to uniquely identify each commit and object in the repository.
- **Staging area :** a space where you can prepare changes before committing them to the repository.
- **Remote repository :** a copy of a repository that is located on a server or other remote location.

### Commands
| Command | Description |
| - | - |
| `git status`               | shows the status of the working directory |
| `git add [file]`           | adds changes to the staging area |
| `git reset [file]`         | unstages a file or resets the repository to a previous commit|
| `git checkout -- [file]`   | Discard changes in working directory. **This operation is unrecoverable**|
| `git commit -m "message"`  | commits changes to the repository with a message |
| `git commit --amend`       | amends the last commit with the staged changes |
| `git log`                  | shows the commit history |
| `git log -[limit]`         | limit number of commits by [limit] |
| `git log --oneline`        | condense each commit to a single line |
| `git diff [file]`          | shows the changes made to a file |


<br><br>

---

## Section 3: Git Branching <a id="Branching"></a>
### Important Definitions
- **Branch:** a separate line of development in a Git repository which have a pointer to a specific commit.
- **Merge:** the process of bringing changes from one branch into another.
- **HEAD:** a reference to the currently checked-out commit in the repository.
- **Conflict:** a situation where Git is unable to automatically merge changes from two branches.
### Important Points
- Branching allows for non-linear development and can be used to work on multiple features simultaneously.

### Commands
| Command | Description |
| - | - |
| `git branch`                  |lists all branches in the local repository|
| `git branch -r`               |list the remote branches for a Git repository|
| `git branch -a`               |list all branches, both local and remote|
| `git branch [name]`           |creates a new branch with the given name|
| `git checkout [name]`         |switches to the branch with the given name |
| `git checkout -b [name]`      |creates a new branch with the given name and switches to it|
| `git merge [name]`            |merges changes from the specified branch into the current branch|
| `git merge --no-ff [name]`    |forces a merge commit even if it's a fast-forward merge|
| `git branch --merged`         |list the branches that have been merged into the current branch|
| `git branch -d [name]`        |deletes the branch with the given name|
| `git branch -D [name]`        |forces a branch deletion even if it contains unmerged changes|
| `git tag`                     |list all tags|
| `git tag -a [name] [commit]`  |create an annotated tag|
| `git tag [name] [commit]`     |create a tag|
| `git tag -d [name]`           |remove a tag from local repository|


<br><br>

---

## Section 4: Git on the Server <a id="GitOnTheServer"></a>
### Important Definitions
- **SSH :** a secure network protocol used for remote access to servers and repositories.
- **Git protocol :** a lightweight network protocol used by Git for efficient communication between repositories.

### Important Points
- Git can be used with a central server or in a distributed model where each user has their own copy of the repository.
- To host a Git repository on a server, you can use a variety of protocols, including HTTP, SSH, and Git.
- Git provides hooks that can be used to trigger actions on the server based on certain events.
- Git provides the `git clone` command to copy a repository from a server to your local machine.
### Commands
| Command | Description |
| - | - |
|`git remote add [name] [url]`  |adds a remote repository with the given name and URL|
|`git remote -v`                |lists all remote repositories|
|`git push [remote] [branch]`   |pushes changes to a remote repository|
|`git push --tags`              |pushes all tags to a remote repository|
|`git fetch [remote]`           |fetches changes from a remote repository|
|`git pull [remote] [branch]`   |pulls changes from a remote repository|


<br><br>

---


## Section 5: GitHub <a id="GitHub"></a>
### Important Points
- **Fork :** a copy of a repository on GitHub that allows you to make changes without affecting the original repository.
- **Pull request :** a way to propose changes to a repository on GitHub.
### Important Points
- GitHub is a web-based hosting service for Git repositories.
- GitHub provides a variety of features to support collaboration, including pull requests, issues, and code reviews.
- GitHub provides integrations with a variety of third-party tools, including continuous integration and deployment services.
### Commands
| Command | Description |
| - | - |
|`git remote add [RemoteName] [url]`  |adds the remote repository as the [RemoteName]|
|`git push -u [RemoteName] [branch]`  |pushes changes to the [RemoteName] and sets the upstream branch|
|`git pull [RemoteName] [branch]`     |pulls changes from the [RemoteName] and merges them|
|`git push [RemoteName] [branch]`     |deletes a branch from the [RemoteName]|


<br><br>

---

##  Section 6: Git Tools <a id="GitTools"></a>
### Important Points
- Git provides a variety of tools to help with common tasks, including merging, rebasing, and cherry-picking.
- Git provides a way to view the changes made to a file over time using the `git blame` command.
- Git provides a way to search for changes across the repository using the `git grep` command.
- Git provides the `git stash` command to temporarily store changes.
### Commands
| Command | Description |
| - | - |
|`git stash`                   |stashes changes to the working directory|
|`git stash list`              |lists all stashes|
|`git stash apply`             |applies the most recent stash|
|`git stash apply stash@{n}`   |applies the nth stash|
|`git blame [file]`            |shows who made each change to a file and when|
|`git reflog`                  |shows a log of all Git references|
|`git reset [file]`            |unstages a file or resets the repository to a previous commit|
|`git revert [commit]`         |creates a new commit that undoes the changes of a specific commit|
|`git cherry-pick [commit]`    |applies the changes of a specific commit onto the current branch <br>(useful if you want to apply changes from one branch onto another without merging the entire branch)|
|`git cherry-pick --abort`     |aborts the cherry-pick process and restores the branch to its original state|
|`git cherry-pick --continue`  |continues the cherry-pick process after resolving conflicts|
|`git cherry-pick --skip`      |Skips the current commit if it has already been cherry-picked <br>(Using git cherry-pick --skip can save time and avoid unnecessary conflicts when cherry-picking a range of commits <br>that may include duplicates. However, it's important to keep track of which commits have been cherry-picked to avoid <br>skipping important changes unintentionally)|
|`git clean`                   |deletes untracked files from the working directory|


<br><br>

---

##  Section 7: Customizing Git  <a id="CustomizingGit"></a>
### Important Points
- Git can be customized using configuration files and aliases.
- Git provides a way to create custom Git commands using shell scripts.
- Git provides a way to create custom Git hooks to trigger actions based on certain events.
- Customizing Git can help improve your workflow and increase productivity.
### Commands
| Command | Description |
| - | - |
|`git config --global core.editor "nano"`  |sets the default editor for Git|
|`git config --global color.ui true`       |enables color output for Git|
|`git config --global alias.ci commit`     |creates an alias for a Git command|
|`git config --global --unset alias.ci`    |removes an alias for a Git command|


<br><br>

---

## Some Git best practices <a id="GitBestPractices"></a>

- **Use descriptive commit messages :** Write clear and concise commit messages that describe the changes you have made.

- **Commit early and often :** Committing changes frequently helps you keep track of your progress and makes it easier to undo changes if necessary.

- **Use branches :** Create a new branch for each feature or bug fix you work on. This makes it easier to isolate changes, collaborate with others, and revert changes if necessary.

- **Keep your repository clean :** Remove unnecessary files and directories from your repository. This reduces the size of your repository and makes it easier to work with.

- **Use tags :** Use tags to mark important milestones in your project, such as releases or major changes.

- **Use pull requests :** Use pull requests to review and merge changes contributed by others. This helps ensure that changes are reviewed and tested before they are merged into the main branch.

- **Use Git hooks :** Git hooks are scripts that run automatically when certain Git events occur, such as committing changes or pushing changes to a remote repository. Use Git hooks to automate tasks such as running tests, checking code style, and generating documentation.

- **Use Git aliases :** Git aliases are shortcuts for Git commands. Use Git aliases to save time and make it easier to remember complex commands.


<br><br>

---

## Some git comparisons <a id="GitComparisons"></a>

### Git VS GitHub
<table>
  <tr>
    <th></th>
    <th>Git</th>
    <th>GitHub</th>

  </tr>
  <tr>
    <td>Definition</td>    
    <td>Distributed version control system </td>
    <td>Web-based hosting service for Git repositories</td>
  </tr>

   <tr>
    <td>Pull Requests</td>
    <td>Not supported by Git alone</td>
    <td>Supported through the GitHub web interface</td>
  </tr>

  <tr>
    <td>Issue Tracking</td>
    <td>Not supported by Git alone</td>
    <td>Supported through the GitHub web interface</td>
  </tr>

  <tr>
    <td>User Management</td>
    <td>It lacks a user management feature</td>
    <td>It has a built-in user management feature</td>
  </tr>

  <tr>
    <td>Project Management</td>
    <td>Not supported by Git alone</td>
    <td>Supports project management through GitHub Projects and Boards</td>
  </tr>

  <tr>
    <td>Cost</td>
    <td>Free and open-source</td>
    <td>Free for public repositories, paid plans for private repositories with additional features</td>
  </tr>

  <tr>
    <td>Popularity</td>
    <td>Widely used in the software development industry</td>
    <td>One of the most popular web-based hosting services for Git repositories</td>
  </tr>

  <tr>
    <td>Desktop Interface</td>
    <td>Its desktop interface is named Git Gui</td>
    <td>Its desktop interface is named GitHub Desktop</td>
  </tr>
  
</table>

<br>

### git push -u [remote] [branch] VS git push  [remote] [branch] 

<table>

 <tr>
    <th>git push -u [remote] [branch] </th>
    <th>git push [remote] [branch] </th>
  </tr>

   <tr>
    <td>Used to push changes to a remote branch and set up a tracking relationship between the local and remote branches.</td>
    <td>Used to push changes to a remote branch without setting up a tracking relationship.</td>
  </tr>

   <tr>
    <td>The <b>(-u or --set-upstream)</b> option is required the first time you push changes to a remote branch to set up the tracking relationship.</td>
    <td>The -u option is not required.</td>
  </tr>

  <tr>
    <td>By setting up tracking relationships, you can streamline your workflow and avoid having to specify the remote and branch names each time you push or pull changes</td>
    <td>You will need to specify the remote and branch names each time using the <b>git push [remote] [branch]</b> command because Git will not know which remote branch corresponds to the local branch</td>
  </tr>
</table>

<br>

### git merge [name] VS git merge --no-ff [name] 

<table>
  <tr>
    <th></th>
    <th>git merge [name]</th>
    <th>git merge --no-ff [name]</th>
  </tr>
  <tr>
    <td>Merge Type</td>
    <td>Fast-forward merge if possible, otherwise creates a merge commit</td>
    <td>Always creates a merge commit</td>
  </tr>

  <tr>
    <td>Commit History</td>
    <td>Simple commit history, less detailed</td>
    <td>Detailed commit history, shows when a branch was merged and which commits were included in the merge</td>
  </tr>

  <tr>
    <td>Use Cases</td>
    <td>Best for simple merges or when a fast-forward merge is desired</td>
    <td>Useful for tracking changes and understanding how the codebase has evolved over time</td>
  </tr>
</table>

<br>



### Annotated Tags VS Lightweight Tags

<table>
  <tr>
    <th></th>
    <th>Annotated Tags</th>
    <th>Lightweight Tags</th>

  </tr>
  <tr>
    <td>Object Type</td>
    <td>Full object in Git's object database</td>
    <td>Reference to a commit</td>
  </tr>

  <tr>
    <td>Metadata</td>
    <td>Contains additional metadata such as tagging message, tagger name, email, and GPG signature</td>
    <td>No additional metadata</td>
  </tr>

  <tr>
    <td>Size</td>
    <td>Larger size due to additional metadata</td>
    <td>Smaller size due to lack of metadata</td>
  </tr>

  <tr>
    <td>Recommended Use</td>
    <td>Recommended for most use cases</td>
    <td>Use when only a simple reference to a commit is needed</td>
  </tr>

  <tr>
    <td>Creation Command</td>
    <td>git tag -a [name] [commit]</td>
    <td>git tag [name] [commit]</td>
  </tr>
</table>

<br>

### git log VS git ref 
<table>
  <tr>
    <th>git log</th>
    <th>git ref log</th>
  </tr>
  <tr>
    <td>Shows the commit history of the current branch or a specified branch</td>
    <td>Shows the history of all the local references, including deleted branches and commits that are no longer reachable</td>
  </tr>
  <tr>
    <td>Displays a list of commits in reverse chronological order</td>
    <td>Displays a list of all the changes made to the repository's references, including branches and tags</td>
  </tr>
  <tr>
    <td>Shows the commit message, author, date, and hash for each commit</td>
    <td>Shows the reference name, hash, and commit message for each change to a reference</td>
  </tr>
  <tr>
    <td>Can be filtered by various options, such as author, date range, and file path</td>
    <td>Does not support filtering options</td>
  </tr>
  <tr>
    <td>Can be used to generate a patch or diff for a specific commit</td>
    <td>Does not support generating patches or diffs</td>
  </tr>
  <tr>
    <td>Useful for reviewing the history of a branch and understanding the changes made over time</td>
    <td>Useful for recovering lost commits or branches and understanding the history of the repository's references</td>
  </tr>
  <tr>
    <td>Can be used with various options and flags, such as --graph and --oneline, to customize the output</td>
    <td>Does not support customization options or flags</td>
  </tr>
  <tr>
    <td>Can be used with various commands, such as git blame and git cherry-pick, to perform different operations on the commits</td>
    <td>Does not support performing operations on the references</td>
  </tr>
</table>

<br><br>

---

## Some useful git extensions in VS Code  <a id="GitExtensionsInVSCode"></a>
- [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Git Blame](https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame)

<br><br>

---

## References <a id="References"></a>

- [Git Pro](https://git-scm.com/book/en/v2)
- [Chat GPT](https://chat.openai.com/auth/login)
- [Git cheat sheet (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf)
- [Git cheat sheet (Atlassian)](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
- [Git cheat sheet (GitLab)](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)
