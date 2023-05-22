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