 - **Git config**: `git config --global user.name "Dominik Stuerzer"` to set the name, analogously the e-mail. Check status by `git config --list`.
 - Set up **credential cache**: `git config --global credential.helper cache` stores remote login data for a while.
 - **Initalize** Git on the local machine: `git init`.
 - **Clone** from other repo: `git clone` initializes and clones the repo. 
 - **Status**: `git status` shows status of files in repo. Short version with flag `-s`.
 - **Basics**: Fist time `git add` tracks files. At all times `git add` *stages* a file. `git commit` takes a snapshot of the *staging area*. Unstaged changes will not be committed (even if correspoding file is staged). `git commit -v` puts diff of change in the editor
 - **Diff (1)**: running simply `git diff` shows the diff between working directory and staging area (i.e. still unstaged changes). If nothing has been staged since last commit, `git diff` shows the diff between last commit and working directory. Adding the flag `--staged`, it shows the diff between last commit and staging area.
 - **Remote branches**: `git pull` is `git fetch`, followed by a `git merge` from the branch your local branch is *tracking*. Tracking    means that the remote branch and the local branch are 'connected'.
 - *Initializing tracking branch*: push local branch to tracking branch on the remote by `git push -u origin <local_branch>:<remote_branch_name>`
  - *Fetching* remote branch: If there is a remote branch <rbranch>, and I want to create a local branch tracking the remote, you do `git checkout --track origin/<rbranch>`, or more quickly, `git checkout <rbranch>`
 - **Remotes**: Show all remotes by `git remote -v`, and delete a remote by `git remote rm <origin>`

xxx
