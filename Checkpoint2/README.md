# Checkpoint2 Submission

- **COURSE INFORMATION: CSN400NDD**
- **STUDENT’S NAME: Ashwin Dhingra**
- **STUDENT'S NUMBER: 124189218**
- **GITHUB USER ID: 124189218-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**


### Table of Contents
1. [Part A - Adding Files - Local Repo Workflow](#Part-A-Adding-Files-Local-Repo-Workflow)
2. [Part B - Inspecting Local Repo with `git status` and `git log`](#Part-B-Inspecting-Local-Repo-with-`git-status`-and-`git-log`)
3. [Part C - Creating & Merging Branches](#Part-C-Creating-&-Merging-Branches)
4. [Part D - Git Branching Strategy Review Question](#Part-D-Git-Branching-Strategy-Review-Question)


## Part A - Adding Files - Local Repo Workflow

We can use git add -all command to add and git commit command to add files to the local repository.

<img src="16412576933806_image30.png" alt="image" title="image">

## Part B - Inspecting Local Repo with `git status` and `git log`

git status- This command is useful in displaying the status of the directory the user is working on. It displays any changes that have been made to files since the last commit, including any alterations, additions, or deletions. Git status returns information about the branch you're on, untracked files, changes that need to be committed, and changes that aren't ready for commit.


git log - This command shows a list of commits in the repository in chronological order, beginning with the most recent commit and moving backward in time.

Example:

This picture show the output of git log and git status commands. Log commands show the commint history and the status command displaying directory info.


<img src="Screenshot (74).png" alt="image" title="image">

## Part C - Creating & Merging Branches

### Output of 'git log -n 5'
```bash
Ashwin dhingra@LAPTOP-75PU76M6 MINGW64 /c/CSN400-Git-project/CSN400-Capstone (main)
$ git log -n 5
commit 11170399f4846469ebeadb31ee87094b8a97638b (HEAD -> main, origin/main, origin/feat-emojis, origin/HEAD, feat-emojis)
Author: Ashwin Dhingra local <adhingra12@myseneca.ca>
Date:   Mon May 22 17:59:44 2023 -0400

    adds emojis to feat-emojis branch

commit cd1f99f98e495facbb8c48c83f9a662ea458e71d
Author: Ashwin Dhingra local <adhingra12@myseneca.ca>
Date:   Mon May 22 17:49:14 2023 -0400

    adds folder footnotes

commit 34b5f8ebe88fd4979e935d425b94474a3602951e
Author: Ashwin Dhingra local <adhingra12@myseneca.ca>
Date:   Mon May 22 17:26:32 2023 -0400

    modified headers

commit 85379b513ed186890647637469673c85b0badea0
Author: Ashwin Dhingra local <adhingra12@myseneca.ca>
Date:   Mon May 22 17:17:55 2023 -0400

    Adds checkpoint - Part 2

commit 65f4db025e041230db8cff4ca570bb8265c537e2
Author: Ashwin Dhingra local <adhingra12@myseneca.ca>
Date:   Mon May 22 16:52:12 2023 -0400

    Adds Part A

```

## Part D - Git Branching Strategy Review Questions

1. What are the differences between develop branch and main branch?

Answer-
Main branch: This is the primary branch in git which is also known master. It typically includes the most recent stable codebase version that is prepared for deployment.

Develop branch functions as an internal integration branch where different features, bug fixes, and other development modifications are put together and validated before merging into the primary code. Developers working on various features or tasks frequently split off branches  to work on their modifications and then merge those branches back into develop after completion.


2. What are the three supporting branches? Briefly describe the function of each of these supporting branches.

Answer - There are three types of branches in git called feature, release and hotfix.

Feature branches: New features and functionality are developed via feature branches. feature branches allow each feature to be developed independently on its own branch, developers can work on multiple features at once and it gets merged back into the develop branch after a feature is finished. When developing features, feature branches allow for productive collaboration while still providing isolation. 

Release branches: When the development team is getting ready to release a new version, release branches are generated from the develop branch. These branches make it possible to complete final testing, bug fixes, and other release-related work without interfering with active development. The release branch is merged into the develop and main branches after completion of the release. 

Hotfix branches: In the production environment, hotfix branches are implemented to address urgently needed serious problems or faults. They are built from the main branch to find and address the issue without interfering with ongoing development on the develop branch.

3. What are the best practices in working with release branches?

Answer: Some best practices for release branches are: 

For all new features and bug fixes, use feature branches.

Utilise pull requests to merge feature branches into the main branch.

Keep a high quality, up-to-date main branch.

Set up an effective versioning strategy for your releases. 

Test the release thoroughly to guarantee stability before merging the release branch into the main branch.
