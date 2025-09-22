# [English Version](#en) | [النسخة العربية](#ar)

<h2 dir="ltr" align="center" id="en">
    بسم الله الرحمن الرحيم
</h2>

<h2 dir="ltr" align="center">
    Git Revision
</h2>

This revision is designed to provide a concise overview of Git, including basic and some advanced concepts, and some of best practices for using Git in real-world scenarios. It is intended for developers, software engineers, and anyone interested in using Git to manage their code and collaborate with others.

**Revision Content**

1.  [Getting Started](#GettingStarted)
2.  [Git Basics](#Basics)
3.  [Git Branching](#Branching)
4.  [Git on the Server](#GitOnTheServer)
5.  [Git Tools](#GitTools)
6.  [Git Best Practices](#GitBestPractices)
7.  [Git Comparisons](#GitComparisons)
8.  [GitLab vs Git](#GitVsGitLab)
9.  [Merge vs Rebase](#MergeVsRebase)
10. [Useful Git Extensions in VS Code](#GitExtensionsInVSCode)
11. [References](#References)

---

<h2 dir="ltr" align="center">
    Revision Content
</h2>

### 1. Getting Started <a id="GettingStarted"></a>

#### Important Definitions

-   **Version control:** A system that records changes to a file or set of files over time, allowing you to recall specific versions later.
-   **Distributed version control:** A version control system where every user has a complete copy of the repository, instead of relying on a central server.
-   **Working directory:** The directory on your local machine where you are currently working on files in a Git repository.
-   **Repository:** A collection of files and directories that are tracked by Git.

#### Important Points

-   **Git** is a **distributed version control** system designed for speed, data integrity, and support for distributed, non-linear workflows.
-   Git stores data as **snapshots** of the entire repository at particular points in time.
-   Files in Git have three main states: **committed, modified, and staged**.
-   Git has a command-line interface as well as graphical user interface tools.

#### Commands

| Command | Description |
| :--- | :--- |
| `git init` | Initializes a new Git repository |
| `git clone [url]` | Clones a remote repository to your local machine |
| `git config --global user.name "Your Name"` | Sets your name for Git |
| `git config --global user.email "youremail@example.com"` | Sets your email for Git |

---

### 2. Git Basics <a id="Basics"></a>

#### Important Definitions

-   **Commit:** A snapshot of the repository at a particular point in time.
-   **SHA-1:** A cryptographic hash function used by Git to uniquely identify each commit and object in the repository.
-   **Staging area:** A space where you can prepare changes before committing them to the repository.
-   **Remote repository:** A copy of a repository that is located on a server or other remote location.

#### Commands

| Command | Description |
| :--- | :--- |
| `git status` | Shows the status of the working directory |
| `git add [file]` | Adds changes to the staging area |
| `git reset [file]` | Unstages a file or resets the repository to a previous commit |
| `git checkout -- [file]` | Discards changes in the working directory. **This operation is unrecoverable** |
| `git commit -m "message"` | Commits changes to the repository with a message |
| `git commit --amend` | Amends the last commit with the staged changes |
| `git log` | Shows the commit history |
| `git log -[limit]` | Limits the number of commits shown by [limit] |
| `git log --oneline` | Condenses each commit to a single line |
| `git diff [file]` | Shows the changes made to a file |

---

### 3. Git Branching <a id="Branching"></a>

#### Important Definitions

-   **Branch:** A separate line of development in a Git repository that has a pointer to a specific commit.
-   **Merge:** The process of bringing changes from one branch into another.
-   **HEAD:** A reference to the currently checked-out commit in the repository.
-   **Conflict:** A situation where Git is unable to automatically merge changes from two branches.

#### Important Points

-   Branching allows for non-linear development and can be used to work on multiple features simultaneously.

#### Commands

| Command | Description |
| :--- | :--- |
| `git branch` | Lists all local branches in the repository |
| `git branch -r` | Lists the remote branches for a Git repository |
| `git branch -a` | Lists all branches, both local and remote |
| `git branch [name]` | Creates a new branch with the given name |
| `git checkout [name]` | Switches to the branch with the given name |
| `git checkout -b [name]` | Creates a new branch with the given name and switches to it |
| `git merge [name]` | Merges changes from the specified branch into the current branch |
| `git merge --no-ff [name]` | Forces a merge commit even if it's a fast-forward merge |
| `git branch --merged` | Lists the branches that have been merged into the current branch |
| `git branch -d [name]` | Deletes the branch with the given name |
| `git branch -D [name]` | Forces a branch deletion even if it contains unmerged changes |
| `git tag` | Lists all tags |
| `git tag -a [name] [commit]` | Creates an annotated tag |
| `git tag [name] [commit]` | Creates a lightweight tag |
| `git tag -d [name]` | Removes a tag from the local repository |

---

### 4. Git on the Server <a id="GitOnTheServer"></a>

#### Important Definitions

-   **SSH:** A secure network protocol used for remote access to servers and repositories.
-   **Git protocol:** A lightweight network protocol used by Git for efficient communication between repositories.

#### Important Points

-   Git can be used with a central server or in a distributed model where each user has their own copy of the repository.
-   To host a Git repository on a server, you can use a variety of protocols, including HTTP, SSH, and Git.
-   Git provides hooks that can be used to trigger actions on the server based on certain events.
-   Git provides the `git clone` command to copy a repository from a server to your local machine.

#### Commands

| Command | Description |
| :--- | :--- |
| `git remote add [name] [url]` | Adds a remote repository with the given name and URL |
| `git remote -v` | Lists all remote repositories |
| `git push [remote] [branch]` | Pushes changes to a remote repository |
| `git push --tags` | Pushes all tags to a remote repository |
| `git fetch [remote]` | Fetches changes from a remote repository |
| `git pull [remote] [branch]` | Pulls changes from a remote repository |

---

### 5. Git Tools <a id="GitTools"></a>

#### Important Points

-   Git provides a variety of tools to help with common tasks, including merging, rebasing, and cherry-picking.
-   Git provides a way to view the changes made to a file over time using the `git blame` command.
-   Git provides a way to search for changes across the repository using the `git grep` command.
-   Git provides the `git stash` command to temporarily store changes.

#### Commands

| Command | Description |
| :--- | :--- |
| `git stash` | Stashes changes to the working directory |
| `git stash list` | Lists all stashes |
| `git stash apply` | Applies the most recent stash |
| `git stash apply stash@{n}` | Applies the nth stash |
| `git blame [file]` | Shows who made each change to a file and when |
| `git reflog` | Shows a log of all Git references |
| `git reset [file]` | Unstages a file or resets the repository to a previous commit |
| `git revert [commit]` | Creates a new commit that undoes the changes of a specific commit |
| `git cherry-pick [commit]` | Applies the changes of a specific commit onto the current branch <br> (useful if you want to apply changes from one branch onto another without merging the entire branch) |
| `git cherry-pick --abort` | Aborts the cherry-pick process and restores the branch to its original state |
| `git cherry-pick --continue` | Continues the cherry-pick process after resolving conflicts |
| `git cherry-pick --skip` | Skips the current commit if it has already been applied <br> (Using git cherry-pick --skip can save time and avoid unnecessary conflicts when cherry-picking a range of commits that may include duplicates. However, it's important to keep track of which commits have been cherry-picked to avoid skipping important changes unintentionally) |
| `git clean` | Deletes untracked files from the working directory |

---

### 6. Git Best Practices <a id="GitBestPractices"></a>

-   **Use descriptive commit messages:** Write clear and concise commit messages that describe the changes you have made.
-   **Commit early and often:** Committing changes frequently helps you keep track of your progress and makes it easier to undo changes if necessary.
-   **Use branches:** Create a new branch for each feature or bug fix you work on. This makes it easier to isolate changes, collaborate with others, and revert changes if necessary.
-   **Keep your repository clean:** Remove unnecessary files and directories from your repository. This reduces the size of your repository and makes it easier to work with.
-   **Use tags:** Use tags to mark important milestones in your project, such as releases or major changes.
-   **Use pull requests:** Use pull requests to review and merge changes contributed by others. This helps ensure that changes are reviewed and tested before they are merged into the main branch.
-   **Use Git hooks:** Git hooks are scripts that run automatically when certain Git events occur, such as committing changes or pushing changes to a remote repository. Use Git hooks to automate tasks such as running tests, checking code style, and generating documentation.
-   **Use Git aliases:** Git aliases are shortcuts for Git commands. Use Git aliases to save time and make it easier to remember complex commands.

---

### 7. Git Comparisons <a id="GitComparisons"></a>

#### Git vs GitHub

| | **Git** | **GitHub** |
| :--- | :--- | :--- |
| **Definition** | A distributed version control system. | A web-based hosting service for Git repositories. |
| **Pull Requests** | Not supported by Git alone. | Supported through the GitHub web interface. |
| **Issue Tracking** | Not supported by Git alone. | Supported through the GitHub web interface. |
| **User Management** | It lacks a user management feature. | It has a built-in user management feature. |
| **Project Management** | Not supported by Git alone. | Supports project management through GitHub Projects and Boards. |
| **Cost** | Free and open-source. | Free for public repositories, paid plans for private repositories with additional features. |
| **Popularity** | Widely used in the software development industry. | One of the most popular web-based hosting services for Git repositories. |
| **Desktop Interface** | Its desktop interface is named Git Gui. | Its desktop interface is named GitHub Desktop. |

#### `git push -u [remote] [branch]` vs `git push [remote] [branch]`

| `git push -u [remote] [branch]` | `git push [remote] [branch]` |
| :--- | :--- |
| Used to push changes to a remote branch and set up a tracking relationship between the local and remote branches. | Used to push changes to a remote branch without setting up a tracking relationship. |
| The **(-u or --set-upstream)** option is required the first time you push changes to a remote branch to set up the tracking relationship. | The -u option is not required. |
| By setting up tracking relationships, you can streamline your workflow and avoid having to specify the remote and branch names each time you push or pull changes. | You will need to specify the remote and branch names each time using the `git push [remote] [branch]` command because Git will not know which remote branch corresponds to the local branch. |

#### `git merge [name]` vs `git merge --no-ff [name]`

| | **`git merge [name]`** | **`git merge --no-ff [name]`** |
| :--- | :--- | :--- |
| **Merge Type** | Fast-forward merge if possible, otherwise creates a merge commit. | Always creates a merge commit. |
| **Commit History** | Simple commit history, less detailed. | Detailed commit history, shows when a branch was merged and which commits were included in the merge. |
| **Use Cases** | Best for simple merges or when a fast-forward merge is desired. | Useful for tracking changes and understanding how the codebase has evolved over time. |

#### Annotated Tags vs Lightweight Tags

| | **Annotated Tags** | **Lightweight Tags** |
| :--- | :--- | :--- |
| **Object Type** | A full object in Git's object database. | A reference to a commit. |
| **Metadata** | Contains additional metadata such as a tagging message, tagger name, email, and GPG signature. | No additional metadata. |
| **Size** | Larger size due to additional metadata. | Smaller size due to lack of metadata. |
| **Recommended Use** | Recommended for most use cases. | Use when only a simple reference to a commit is needed. |
| **Creation Command** | `git tag -a [name] [commit]` | `git tag [name] [commit]` |

#### `git log` vs `git reflog`

| **`git log`** | **`git reflog`** |
| :--- | :--- |
| Shows the commit history of the current branch or a specified branch. | Shows the history of all the local references, including deleted branches and commits that are no longer reachable. |
| Displays a list of commits in reverse chronological order. | Displays a list of all the changes made to the repository's references, including branches and tags. |
| Shows the commit message, author, date, and hash for each commit. | Shows the reference name, hash, and commit message for each change to a reference. |
| Can be filtered by various options, such as author, date range, and file path. | Does not support filtering options. |
| Can be used to generate a patch or diff for a specific commit. | Does not support generating patches or diffs. |
| Useful for reviewing the history of a branch and understanding the changes made over time. | Useful for recovering lost commits or branches and understanding the history of the repository's references. |
| Can be used with various options and flags, such as `--graph` and `--oneline`, to customize the output. | Does not support customization options or flags. |
| Can be used with various commands, such as `git blame` and `git cherry-pick`, to perform different operations on the commits. | Does not support performing operations on the references. |

---

### 8. GitLab vs Git <a id="GitVsGitLab"></a>

| | **Git** | **GitLab** |
| :--- | :--- | :--- |
| **Definition** | A distributed version control system. | A web-based service and a complete DevOps lifecycle. |
| **Primary Use** | Managing local and remote code. | Hosting repositories, project management, CI/CD, and more. |
| **Environment** | Primarily a command-line interface. | A full web interface with integrated tools. |
| **CI/CD** | Does not support it directly. | Provides a powerful, built-in CI/CD system (GitLab CI/CD). |
| **Project Management** | Does not support it. | Provides boards for tracking issues and tasks. |
| **Installation** | Installed on the local machine. | Can be self-hosted or used as a cloud service. |

---

### 9. Merge vs Rebase <a id="MergeVsRebase"></a>

-   **Git Merge:** A non-destructive way to merge changes. It keeps a full historical record, including every merge commit, which clearly shows when branches were joined together.
-   **Git Rebase:** Rewrites the history. It moves a series of commits from one branch to another, creating a clean, linear history. This makes the commit history look more organized, but it can be dangerous on public branches because it changes the hashes of the commits.

---

### 10. Useful Git Extensions in VS Code <a id="GitExtensionsInVSCode"></a>

-   [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
-   [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
-   [Git Blame](https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame)

---

### 11. References <a id="References"></a>

-   [Git Pro](https://git-scm.com/book/en/v2)
-   [Git cheat sheet (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf)
-   [Git cheat sheet (Atlassian)](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
-   [Git cheat sheet (GitLab)](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)
-   [Git & GitHub شرح كورس عربي](https://www.youtube.com/watch?v=AkIpdnup6G4)

A comprehensive video course on Git and GitHub in Arabic.

<br>

<h2 dir="rtl" align="center" id="ar">
    بسم الله الرحمن الرحيم
</h2>

<h2 dir="rtl" align="center">
    مراجعة Git
</h2>

هذا المرجع يهدف لتقديم لمحة موجزة عن نظام Git، مع تغطية المفاهيم الأساسية وبعض المفاهيم المتقدمة، بالإضافة إلى أفضل الممارسات لاستخدام Git في سيناريوهات عملية. هذا الدليل موجه للمطورين، مهندسي البرمجيات، وأي شخص مهتم باستخدام Git لإدارة شفرة المصدر والتعاون مع الآخرين.

**محتوى المراجعة**

1.  [البدء](#GettingStarted)
2.  [أساسيات Git](#Basics)
3.  [الفروع في Git](#Branching)
4.  [Git على الخادم](#GitOnTheServer)
5.  [أدوات Git](#GitTools)
6.  [أفضل الممارسات](#GitBestPractices)
7.  [مقارنات Git](#GitComparisons)
8.  [مقارنة Git مع GitLab](#GitVsGitLab)
9.  [الدمج (Merge) مقابل إعادة الأساس (Rebase)](#MergeVsRebase)
10. [ملحقات Git المفيدة في VS Code](#GitExtensionsInVSCode)
11. [المراجع](#References)

---

<h2 dir="rtl" align="center">
    محتوى المراجعة

<h2 dir="rtl" id="GettingStarted">القسم 1: البدء</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>التحكم بالإصدارات (Version control):</strong> نظام يسجل التغييرات التي تحدث على ملف أو مجموعة من الملفات عبر الزمن، مما يتيح لك استعادة إصدارات سابقة محددة في وقت لاحق.</li>
    <li><strong>التحكم بالإصدارات الموزع (Distributed version control):</strong> نظام تحكم بالإصدارات يمتلك فيه كل مستخدم نسخة كاملة من المستودع، بدلاً من الاعتماد على خادم مركزي.</li>
    <li><strong>مجلد العمل (Working directory):</strong> المجلد على جهازك المحلي الذي تعمل فيه حاليًا على الملفات الموجودة في مستودع Git.</li>
    <li><strong>المستودع (Repository):</strong> مجموعة من الملفات والمجلدات التي يتم تتبعها بواسطة Git.</li>
</ul>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li><strong>Git</strong> هو نظام <strong>تحكم بالإصدارات موزع</strong> مصمم من أجل السرعة، سلامة البيانات، ودعم سير العمل الموزع وغير الخطي.</li>
    <li>يقوم <strong>Git</strong> بتخزين البيانات ك<strong>لقطات (snapshots)</strong> للمستودع بأكمله في نقاط زمنية معينة.</li>
    <li>الملفات في <strong>Git</strong> تمر بثلاث حالات رئيسية: <strong>committed (مؤكدة)، modified (معدلة)، وstaged (مرحلة)</strong>.</li>
    <li>لدى <strong>Git</strong> واجهة سطر أوامر، بالإضافة إلى أدوات واجهة رسومية.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git init</code></td>
            <td>يقوم بتهيئة مستودع Git جديد</td>
        </tr>
        <tr>
            <td><code>git clone [url]</code></td>
            <td>يستنسخ مستودعًا بعيدًا إلى جهازك المحلي</td>
        </tr>
        <tr>
            <td><code>git config --global user.name "Your Name"</code></td>
            <td>يقوم بضبط اسمك في Git</td>
        </tr>
        <tr>
            <td><code>git config --global user.email "youremail@example.com"</code></td>
            <td>يقوم بضبط بريدك الإلكتروني في Git</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="Basics">القسم 2: أساسيات Git</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>التأكيد (Commit):</strong> لقطة للمستودع في نقطة زمنية معينة.</li>
    <li><strong>SHA-1:</strong> دالة هاش تشفيرية تستخدمها Git لتحديد كل تأكيد وكائن في المستودع بشكل فريد.</li>
    <li><strong>منطقة التجهيز (Staging area):</strong> مساحة يمكنك فيها تحضير التغييرات قبل تأكيدها في المستودع.</li>
    <li><strong>المستودع البعيد (Remote repository):</strong> نسخة من المستودع موجودة على خادم أو أي موقع بعيد آخر.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git status</code></td>
            <td>يعرض حالة مجلد العمل</td>
        </tr>
        <tr>
            <td><code>git add [file]</code></td>
            <td>يضيف التغييرات إلى منطقة التجهيز</td>
        </tr>
        <tr>
            <td><code>git reset [file]</code></td>
            <td>يلغي تجهيز ملف أو يعيد المستودع إلى تأكيد سابق</td>
        </tr>
        <tr>
            <td><code>git checkout -- [file]</code></td>
            <td>يتجاهل التغييرات في مجلد العمل. <strong>هذه العملية غير قابلة للاستعادة</strong></td>
        </tr>
        <tr>
            <td><code>git commit -m "message"</code></td>
            <td>يؤكد التغييرات في المستودع مع رسالة</td>
        </tr>
        <tr>
            <td><code>git commit --amend</code></td>
            <td>يعدل آخر تأكيد بالتغييرات المجهزة</td>
        </tr>
        <tr>
            <td><code>git log</code></td>
            <td>يعرض سجل التأكيدات</td>
        </tr>
        <tr>
            <td><code>git log -[limit]</code></td>
            <td>يحد عدد التأكيدات المعروضة بـ [limit]</td>
        </tr>
        <tr>
            <td><code>git log --oneline</code></td>
            <td>يلخص كل تأكيد في سطر واحد</td>
        </tr>
        <tr>
            <td><code>git diff [file]</code></td>
            <td>يعرض التغييرات التي تمت على ملف</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="Branching">القسم 3: الفروع في Git</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>الفرع (Branch):</strong> خط تطوير منفصل في مستودع Git، يحتوي على مؤشر لتأكيد محدد.</li>
    <li><strong>الدمج (Merge):</strong> عملية جلب التغييرات من فرع إلى آخر.</li>
    <li><strong>HEAD:</strong> مرجع للتأكيد الحالي الذي تم سحبه في المستودع.</li>
    <li><strong>التعارض (Conflict):</strong> حالة لا يستطيع فيها Git دمج التغييرات تلقائيًا من فرعين.</li>
</ul>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li>يسمح التفريع بالتطوير غير الخطي ويمكن استخدامه للعمل على ميزات متعددة في وقت واحد.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git branch</code></td>
            <td>يسرد جميع الفروع المحلية في المستودع</td>
        </tr>
        <tr>
            <td><code>git branch -r</code></td>
            <td>يسرد الفروع البعيدة لمستودع Git</td>
        </tr>
        <tr>
            <td><code>git branch -a</code></td>
            <td>يسرد جميع الفروع، المحلية والبعيدة</td>
        </tr>
        <tr>
            <td><code>git branch [name]</code></td>
            <td>ينشئ فرعًا جديدًا بالاسم المحدد</td>
        </tr>
        <tr>
            <td><code>git checkout [name]</code></td>
            <td>ينتقل إلى الفرع بالاسم المحدد</td>
        </tr>
        <tr>
            <td><code>git checkout -b [name]</code></td>
            <td>ينشئ فرعًا جديدًا بالاسم المحدد وينتقل إليه</td>
        </tr>
        <tr>
            <td><code>git merge [name]</code></td>
            <td>يدمج التغييرات من الفرع المحدد في الفرع الحالي</td>
        </tr>
        <tr>
            <td><code>git merge --no-ff [name]</code></td>
            <td>يجبر على إنشاء تأكيد دمج حتى لو كان دمجًا سريعًا (fast-forward)</td>
        </tr>
        <tr>
            <td><code>git branch --merged</code></td>
            <td>يسرد الفروع التي تم دمجها في الفرع الحالي</td>
        </tr>
        <tr>
            <td><code>git branch -d [name]</code></td>
            <td>يحذف الفرع بالاسم المحدد</td>
        </tr>
        <tr>
            <td><code>git branch -D [name]</code></td>
            <td>يجبر على حذف الفرع حتى لو كان يحتوي على تغييرات غير مدمجة</td>
        </tr>
        <tr>
            <td><code>git tag</code></td>
            <td>يسرد جميع الوسوم</td>
        </tr>
        <tr>
            <td><code>git tag -a [name] [commit]</code></td>
            <td>ينشئ وسماً مشروحاً (annotated tag)</td>
        </tr>
        <tr>
            <td><code>git tag [name] [commit]</code></td>
            <td>ينشئ وسماً خفيفاً (lightweight tag)</td>
        </tr>
        <tr>
            <td><code>git tag -d [name]</code></td>
            <td>يزيل وسماً من المستودع المحلي</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitOnTheServer">القسم 4: Git على الخادم</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>بروتوكول SSH:</strong> بروتوكول شبكة آمن يستخدم للوصول عن بعد إلى الخوادم والمستودعات.</li>
    <li><strong>بروتوكول Git:</strong> بروتوكول شبكة خفيف الوزن يستخدمه Git للتواصل الفعال بين المستودعات.</li>
</ul>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li>يمكن استخدام Git مع خادم مركزي أو في نموذج موزع حيث يمتلك كل مستخدم نسخته الخاصة من المستودع.</li>
    <li>لاستضافة مستودع Git على خادم، يمكنك استخدام مجموعة متنوعة من البروتوكولات، بما في ذلك HTTP وSSH وGit.</li>
    <li>يوفر Git خطاطيف (hooks) يمكن استخدامها لتشغيل إجراءات على الخادم بناءً على أحداث معينة.</li>
    <li>يوفر Git أمر <code>git clone</code> لنسخ مستودع من خادم إلى جهازك المحلي.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git remote add [name] [url]</code></td>
            <td>يضيف مستودعًا بعيدًا بالاسم والمسار المحدد</td>
        </tr>
        <tr>
            <td><code>git remote -v</code></td>
            <td>يسرد جميع المستودعات البعيدة</td>
        </tr>
        <tr>
            <td><code>git push [remote] [branch]</code></td>
            <td>يدفع التغييرات إلى مستودع بعيد</td>
        </tr>
        <tr>
            <td><code>git push --tags</code></td>
            <td>يدفع جميع الوسوم إلى مستودع بعيد</td>
        </tr>
        <tr>
            <td><code>git fetch [remote]</code></td>
            <td>يجلب التغييرات من مستودع بعيد</td>
        </tr>
        <tr>
            <td><code>git pull [remote] [branch]</code></td>
            <td>يسحب التغييرات من مستودع بعيد</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitTools">القسم 5: أدوات Git</h2>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li>يوفر Git مجموعة متنوعة من الأدوات للمساعدة في المهام الشائعة، مثل الدمج (merging)، وإعادة الأساس (rebasing)، وانتقاء التأكيدات (cherry-picking).</li>
    <li>يوفر Git طريقة لعرض التغييرات التي تمت على ملف بمرور الوقت باستخدام الأمر <code>git blame</code>.</li>
    <li>يوفر Git طريقة للبحث عن التغييرات عبر المستودع باستخدام الأمر <code>git grep</code>.</li>
    <li>يوفر Git الأمر <code>git stash</code> لتخزين التغييرات مؤقتًا.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git stash</code></td>
            <td>يخزن التغييرات مؤقتًا في مجلد العمل</td>
        </tr>
        <tr>
            <td><code>git stash list</code></td>
            <td>يسرد جميع التخزينات المؤقتة</td>
        </tr>
        <tr>
            <td><code>git stash apply</code></td>
            <td>يطبق أحدث تخزين مؤقت</td>
        </tr>
        <tr>
            <td><code>git stash apply stash@{n}</code></td>
            <td>يطبق التخزين المؤقت رقم n</td>
        </tr>
        <tr>
            <td><code>git blame [file]</code></td>
            <td>يعرض من قام بكل تغيير على ملف ومتى</td>
        </tr>
        <tr>
            <td><code>git reflog</code></td>
            <td>يعرض سجلًا لجميع مراجع Git</td>
        </tr>
        <tr>
            <td><code>git reset [file]</code></td>
            <td>يلغي تجهيز ملف أو يعيد المستودع إلى تأكيد سابق</td>
        </tr>
        <tr>
            <td><code>git revert [commit]</code></td>
            <td>ينشئ تأكيدًا جديدًا يلغي التغييرات التي تمت في تأكيد محدد</td>
        </tr>
        <tr>
            <td><code>git cherry-pick [commit]</code></td>
            <td>يطبق التغييرات من تأكيد محدد على الفرع الحالي <br>(مفيد إذا كنت ترغب في تطبيق التغييرات من فرع على آخر دون دمج الفرع بأكمله)</td>
        </tr>
        <tr>
            <td><code>git cherry-pick --abort</code></td>
            <td>يلغي عملية cherry-pick ويعيد الفرع إلى حالته الأصلية</td>
        </tr>
        <tr>
            <td><code>git cherry-pick --continue</code></td>
            <td>يواصل عملية cherry-pick بعد حل التعارضات</td>
        </tr>
        <tr>
            <td><code>git cherry-pick --skip</code></td>
            <td>يتخطى التأكيد الحالي إذا كان قد تم تطبيقه بالفعل <br>(استخدام هذا الأمر يوفر الوقت ويتجنب التعارضات غير الضرورية عند تطبيق نطاق من التأكيدات التي قد تتضمن تكرارات)</td>
        </tr>
        <tr>
            <td><code>git clean</code></td>
            <td>يحذف الملفات غير المتتبعة من مجلد العمل</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitBestPractices">القسم 6: أفضل ممارسات Git</h2>

<ul dir="rtl">
    <li><strong>استخدم رسائل تأكيد وصفية:</strong> اكتب رسائل تأكيد واضحة وموجزة تصف التغييرات التي قمت بها.</li>
    <li><strong>التأكيد مبكرًا وبشكل متكرر:</strong> يؤدي تأكيد التغييرات بشكل متكرر إلى مساعدتك في تتبع تقدمك ويسهل عليك التراجع عن التغييرات إذا لزم الأمر.</li>
    <li><strong>استخدم الفروع:</strong> أنشئ فرعًا جديدًا لكل ميزة أو إصلاح خطأ تعمل عليه. هذا يسهل عزل التغييرات والتعاون مع الآخرين والتراجع عن التغييرات إذا لزم الأمر.</li>
    <li><strong>حافظ على نظافة المستودع:</strong> قم بإزالة الملفات والمجلدات غير الضرورية من المستودع. هذا يقلل من حجم المستودع ويسهل العمل معه.</li>
    <li><strong>استخدم الوسوم (tags):</strong> استخدم الوسوم لوضع علامة على المعالم الهامة في مشروعك، مثل الإصدارات أو التغييرات الرئيسية.</li>
    <li><strong>استخدم طلبات السحب (pull requests):</strong> استخدم طلبات السحب لمراجعة ودمج التغييرات التي يساهم بها الآخرون. هذا يساعد على ضمان مراجعة التغييرات واختبارها قبل دمجها في الفرع الرئيسي.</li>
    <li><strong>استخدم خطاطيف Git (Git hooks):</strong> خطاطيف Git هي نصوص برمجية تعمل تلقائيًا عند وقوع أحداث معينة في Git، مثل تأكيد التغييرات أو دفعها إلى مستودع بعيد. استخدم خطاطيف Git لأتمتة المهام مثل تشغيل الاختبارات وفحص تنسيق الشفرة وإنشاء التوثيق.</li>
    <li><strong>استخدم أسماء Git المستعارة (Git aliases):</strong> أسماء Git المستعارة هي اختصارات لأوامر Git. استخدمها لتوفير الوقت وتسهيل تذكر الأوامر المعقدة.</li>
</ul>

---

<h2 dir="rtl" id="GitComparisons">القسم 7: مقارنات Git</h2>

<h3 dir="rtl">Git مقابل GitHub</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th>Git</th>
            <th>GitHub</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>التعريف</strong></td>
            <td>نظام تحكم بالإصدارات موزع</td>
            <td>خدمة استضافة قائمة على الويب لمستودعات Git</td>
        </tr>
        <tr>
            <td><strong>طلبات السحب</strong></td>
            <td>لا يدعمها Git وحده</td>
            <td>مدعومة من خلال واجهة GitHub على الويب</td>
        </tr>
        <tr>
            <td><strong>تتبع المشاكل</strong></td>
            <td>لا يدعمه Git وحده</td>
            <td>مدعوم من خلال واجهة GitHub على الويب</td>
        </tr>
        <tr>
            <td><strong>إدارة المستخدمين</strong></td>
            <td>يفتقر إلى ميزة إدارة المستخدمين</td>
            <td>يحتوي على ميزة مدمجة لإدارة المستخدمين</td>
        </tr>
        <tr>
            <td><strong>إدارة المشاريع</strong></td>
            <td>لا يدعمها Git وحده</td>
            <td>يدعم إدارة المشاريع من خلال GitHub Projects and Boards</td>
        </tr>
        <tr>
            <td><strong>التكلفة</strong></td>
            <td>مجاني ومفتوح المصدر</td>
            <td>مجاني للمستودعات العامة، وخطط مدفوعة للمستودعات الخاصة مع ميزات إضافية</td>
        </tr>
        <tr>
            <td><strong>الانتشار</strong></td>
            <td>يستخدم على نطاق واسع في صناعة تطوير البرمجيات</td>
            <td>واحدة من أكثر خدمات الاستضافة شهرة لمستودعات Git</td>
        </tr>
        <tr>
            <td><strong>واجهة سطح المكتب</strong></td>
            <td>واجهة سطح المكتب الخاصة به تسمى Git Gui</td>
            <td>واجهة سطح المكتب الخاصة به تسمى GitHub Desktop</td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl"><code>git push -u [remote] [branch]</code> مقابل <code>git push [remote] [branch]</code></h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th><code>git push -u [remote] [branch]</code></th>
            <th><code>git push [remote] [branch]</code></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>يستخدم لدفع التغييرات إلى فرع بعيد وإعداد علاقة تتبع بين الفرع المحلي والفرع البعيد.</td>
            <td>يستخدم لدفع التغييرات إلى فرع بعيد دون إعداد علاقة تتبع.</td>
        </tr>
        <tr>
            <td>الخيار <strong>(-u أو --set-upstream)</strong> مطلوب في المرة الأولى التي تدفع فيها التغييرات إلى فرع بعيد لإعداد علاقة التتبع.</td>
            <td>الخيار -u ليس مطلوبًا.</td>
        </tr>
        <tr>
            <td>من خلال إعداد علاقات التتبع، يمكنك تبسيط سير عملك وتجنب الحاجة إلى تحديد اسم المستودع البعيد واسم الفرع في كل مرة تدفع فيها أو تسحب تغييرات.</td>
            <td>ستحتاج إلى تحديد اسم المستودع البعيد واسم الفرع في كل مرة باستخدام أمر <code>git push [remote] [branch]</code> لأن Git لن يعرف أي فرع بعيد يتوافق مع الفرع المحلي.</td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl"><code>git merge [name]</code> مقابل <code>git merge --no-ff [name]</code></h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th><code>git merge [name]</code></th>
            <th><code>git merge --no-ff [name]</code></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>نوع الدمج</strong></td>
            <td>دمج سريع (fast-forward merge) إذا كان ممكنًا، وإلا فإنه ينشئ تأكيد دمج.</td>
            <td>ينشئ دائمًا تأكيد دمج.</td>
        </tr>
        <tr>
            <td><strong>سجل التأكيدات</strong></td>
            <td>سجل تأكيدات بسيط، أقل تفصيلاً.</td>
            <td>سجل تأكيدات مفصل، يوضح متى تم دمج الفرع وأي تأكيدات تم تضمينها في الدمج.</td>
        </tr>
        <tr>
            <td><strong>حالات الاستخدام</strong></td>
            <td>الأفضل للدمج البسيط أو عندما يكون دمجًا سريعًا.</td>
            <td>مفيد لتتبع التغييرات وفهم كيفية تطور قاعدة الشفرة بمرور الوقت.</td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl">الوسوم المشروحة (Annotated Tags) مقابل الوسوم الخفيفة (Lightweight Tags)</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th>الوسوم المشروحة (Annotated Tags)</th>
            <th>الوسوم الخفيفة (Lightweight Tags)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>نوع الكائن</strong></td>
            <td>كائن كامل في قاعدة بيانات كائنات Git</td>
            <td>مرجع إلى تأكيد</td>
        </tr>
        <tr>
            <td><strong>البيانات الوصفية</strong></td>
            <td>تحتوي على بيانات وصفية إضافية مثل رسالة الوسم، واسم الواسم، والبريد الإلكتروني، وتوقيع GPG</td>
            <td>لا توجد بيانات وصفية إضافية</td>
        </tr>
        <tr>
            <td><strong>الحجم</strong></td>
            <td>حجم أكبر بسبب البيانات الوصفية الإضافية</td>
            <td>حجم أصغر بسبب عدم وجود بيانات وصفية</td>
        </tr>
        <tr>
            <td><strong>الاستخدام الموصى به</strong></td>
            <td>يوصى بها لمعظم حالات الاستخدام</td>
            <td>استخدمها عندما يكون المرجع البسيط إلى تأكيد هو كل ما تحتاجه</td>
        </tr>
        <tr>
            <td><strong>أمر الإنشاء</strong></td>
            <td><code>git tag -a [name] [commit]</code></td>
            <td><code>git tag [name] [commit]</code></td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl"><code>git log</code> مقابل <code>git reflog</code></h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th><code>git log</code></th>
            <th><code>git reflog</code></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>يعرض سجل التأكيدات للفرع الحالي أو فرع محدد.</td>
            <td>يعرض سجل جميع المراجع المحلية، بما في ذلك الفروع المحذوفة والتأكيدات التي لم يعد يمكن الوصول إليها.</td>
        </tr>
        <tr>
            <td>يعرض قائمة بالتأكيدات بترتيب زمني عكسي.</td>
            <td>يعرض قائمة بجميع التغييرات التي تمت على مراجع المستودع، بما في ذلك الفروع والوسوم.</td>
        </tr>
        <tr>
            <td>يعرض رسالة التأكيد، والمؤلف، والتاريخ، والهاش لكل تأكيد.</td>
            <td>يعرض اسم المرجع، والهاش، ورسالة التأكيد لكل تغيير في المرجع.</td>
        </tr>
        <tr>
            <td>يمكن تصفيته بخيارات متنوعة، مثل المؤلف، والنطاق الزمني، ومسار الملف.</td>
            <td>لا يدعم خيارات التصفية.</td>
        </tr>
        <tr>
            <td>يمكن استخدامه لإنشاء رقعة (patch) أو فرق (diff) لتأكيد معين.</td>
            <td>لا يدعم إنشاء الرقع أو الفروق.</td>
        </tr>
        <tr>
            <td>مفيد لمراجعة سجل فرع وفهم التغييرات التي تمت بمرور الوقت.</td>
            <td>مفيد لاستعادة التأكيدات أو الفروع المفقودة وفهم سجل مراجع المستودع.</td>
        </tr>
        <tr>
            <td>يمكن استخدامه مع خيارات وعلامات متنوعة، مثل <code>--graph</code> و <code>--oneline</code>، لتخصيص الإخراج.</td>
            <td>لا يدعم خيارات التخصيص أو العلامات.</td>
        </tr>
        <tr>
            <td>يمكن استخدامه مع أوامر متنوعة، مثل <code>git blame</code> و <code>git cherry-pick</code>، لأداء عمليات مختلفة على التأكيدات.</td>
            <td>لا يدعم أداء عمليات على المراجع.</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitVsGitLab">القسم 8: مقارنة Git مع GitLab</h2>

<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th>Git</th>
            <th>GitLab</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>التعريف</strong></td>
            <td>نظام تحكم بالإصدارات موزع.</td>
            <td>خدمة قائمة على الويب ودورة حياة DevOps كاملة.</td>
        </tr>
        <tr>
            <td><strong>الاستخدام الأساسي</strong></td>
            <td>إدارة الشفرة المحلية والبعيدة.</td>
            <td>استضافة المستودعات، إدارة المشاريع، CI/CD، والمزيد.</td>
        </tr>
        <tr>
            <td><strong>بيئة العمل</strong></td>
            <td>واجهة سطر أوامر بشكل أساسي.</td>
            <td>واجهة ويب كاملة مع أدوات مدمجة.</td>
        </tr>
        <tr>
            <td><strong>CI/CD</strong></td>
            <td>لا يدعمها بشكل مباشر.</td>
            <td>يوفر نظام CI/CD مدمج وقوي (GitLab CI/CD).</td>
        </tr>
        <tr>
            <td><strong>إدارة المشاريع</strong></td>
            <td>لا يدعمها.</td>
            <td>يوفر لوحات (boards) لتتبع المشاكل والمهام.</td>
        </tr>
        <tr>
            <td><strong>التثبيت</strong></td>
            <td>يتم تثبيته على الجهاز المحلي.</td>
            <td>يمكن استضافته على الخادم الخاص بك أو استخدامه كخدمة سحابية.</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="MergeVsRebase">القسم 9: الدمج (Merge) مقابل إعادة الأساس (Rebase)</h2>

<ul dir="rtl">
    <li><strong>Git Merge:</strong> طريقة غير مدمرة لدمج التغييرات. يحتفظ بسجل تاريخي كامل، بما في ذلك كل تأكيد دمج، مما يوضح بوضوح متى تم دمج الفروع معًا.</li>
    <li><strong>Git Rebase:</strong> يعيد كتابة سجل التاريخ. ينقل سلسلة من التأكيدات من فرع إلى فرع آخر، مما يخلق سجلًا خطيًا ونظيفًا. هذه الطريقة تجعل سجل التأكيدات يبدو أكثر تنظيمًا، ولكنها يمكن أن تكون خطيرة على الفروع العامة لأنها تغير الهاشات (hashes) الخاصة بالتأكيدات.</li>
</ul>

---

<h2 dir="rtl" id="GitExtensionsInVSCode">القسم 10: ملحقات Git المفيدة في VS Code</h2>

<ul dir="rtl">
    <li><a href="https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory">Git History</a></li>
    <li><a href="https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens">GitLens</a></li>
    <li><a href="https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame">Git Blame</a></li>
</ul>

---

<h2 dir="rtl" id="References">القسم 11: المراجع</h2>

<ul dir="rtl">
    <li><a href="https://git-scm.com/book/en/v2">Git Pro</a></li>
    <li><a href="https://education.github.com/git-cheat-sheet-education.pdf">Git cheat sheet (GitHub)</a></li>
    <li><a href="https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet">Git cheat sheet (Atlassian)</a></li>
    <li><a href="https://about.gitlab.com/images/press/git-cheat-sheet.pdf">Git cheat sheet (GitLab)</a></li>
    <li><a href="https://www.youtube.com/watch?v=AkIpdnup6G4">Git & GitHub شرح كورس عربي</a></li>
</ul>
<p dir="rtl">كورس فيديو شامل عن Git و GitHub باللغة العربية.</p>
