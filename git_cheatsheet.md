 - **Git config**: `git config --global user.name "Dominik Stuerzer"` to set the name, analogously the e-mail. Check status by `git config --list`.
 - Set up **credential cache**: `git config --global credential.helper cache` stores remote login data for a while.
 - **Initalize** Git on the local machine: `git init`.
 - **Clone** from other repo: `git clone` initializes and clones the repo. Adds `origin` remote. 
 - **Status**: `git status` shows status of files in repo. Short version with flag `-s`.
 - **Basics**: Fist time `git add` tracks files. At all times `git add` *stages* a file. `git commit` takes a snapshot of the *staging area*. Unstaged changes will not be committed (even if correspoding file is staged). `git commit -v` puts diff of change in the editor. The flag `-a` stages all tracked files and commits them - it skips the `add`-part.
 - **Remove** a file: `git rm` stages the deletion of a file, the next commit deletes it. However, it can still be checked out in past commits.
 - **Rename**: A file can be renamed by `git mv <old_name> <new_name>`, the namechange is then staged.
 - **Untrack** a file by `git rm --cached <file>`: it is removed from staging area, and not tracked any more. If a previously committed file is untracked, checking out past commits will result in a conflict.
 - **Unstage**: To undo a `git add <file>` (i.e. remove it from the stagin area), use `git reset HEAD <file>`.
 - **Unmodify** a file: `git checkout -- <file>` overwrites file in working directory with last commited version. *Danger*: Any changes since last commit will be lost!
 - **Diff (1)**: running simply `git diff` shows the diff between working directory and staging area (i.e. still unstaged changes). If nothing has been staged since last commit, `git diff` shows the diff between last commit and working directory. Adding the flag `--staged`, it shows the diff between last commit and staging area.
 - **Log**: Possible flags: `-p` shows difference introduced in each commit. `-<n>` limits output to past `n` commits. `--stat` shows change stats. `--graph` visualizes branches. `--relative-date` show relative date. `--decorate` shows the positions of the branch pointers.
 - **Amend**: `git commit --amend` adds currently staged changes to your last commit, and you can edit the last commit message. You don't get a new commit. 
 - **Branches**: `git branch <new branch name>` creates a new branch (which is nothing but a pointer). To switch a branch, do `git checkout <branch>`. `git checkout -b <branch name>` creates and switches to new branch. A list of all branches is shown by `git branch`, and the current branch is marked with a `*`. The last commit per branch is shown by `git branch -v`. The flags `--merged` and `--no-merged` show the branches that have or haven't been merged into the current branch yet. 
 - **Merging**: Check out the branch you would like to merge into (often `master`), and then run `git merge <other branch>`. One of two scenarious will happen then:
  - *Fast Forward Merge*: If the branch to be merged is directly ahead of the branch to be merged into (e.g. `master`), then merging simply moves the `master`-pointer forward to the other branch's pointer. No conflicts happen here. The other branch can be deleted after that by `git branch -d <new branch>`.
  - *Three way merge*: New snapshot is created from the snapshots the two branch-pointers point to, and then commited. Here, conflicts can arise, which will interrupt the merge-process. `git status` shows which files contain conflicts. Conflicts are marked in the files, and can be removed manually. After that `git commit` finalizes the merge.
 - **Remotes**: Show all remotes by `git remote -v`, and delete a remote by `git remote rm <origin>`. To add a a new remote repo, run `git remote add <shortname> <url>`. Remote branches are accessible through `<remotename>/<branchname>`. If you have a local repo, and want to create a remote repo from the local one, first create a remote repo, but don't initialize it. Then `add origin`, then `git push -u origin master`. The `-u`-flag enables tracking of the remote branch.
 -- **Cloning**: Clones a (remote) repo and creates remote-tracking branches for each branch in the cloned repo. Then `git fetch` will update all remote-tracking branches, and `git pull` will additionally merge the remote master branch into the current master branch.
 - **Fetch**: The command `git fetch <remotename>` pulls all new data from remote, but it does not merge it or modify any current of your work. If a local branch *tracks* the remote branch, then `git pull` automatically fetches and merges the remote branch into your current local branch.
 - **Push**: The command `git push <remote-name> <branch-name>` pushes local changes of branch to remote. If `push` results in a conflict, then you have first to fetch and incorporate the remote changes, before pushing is allowed.
 - **Inspecting a Remote**: `git remote show <remote name>` shows more information about the remote.


 - **Remote branches**: `git pull` is `git fetch`, followed by a `git merge` from the branch your local branch is *tracking*. Tracking    means that the remote branch and the local branch are 'connected'.
 - *Initializing tracking branch*: push local branch to tracking branch on the remote by `git push -u origin <local_branch>:<remote_branch_name>`
  - *Fetching* remote branch: If there is a remote branch <rbranch>, and I want to create a local branch tracking the remote, you do `git checkout --track origin/<rbranch>`, or more quickly, `git checkout <rbranch>`


