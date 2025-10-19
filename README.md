# Git Notes

## Working with git locally 

- `git init`: intialize current folder as a git repository
- `git clone <URL>`: brings the git repo from <URL> to current folder
- `git status`: tell us what we need to know about our repository

- `git add <FILE>` : add <FILE> to the staging area
- `git commit`: open a text editor to write commit message
    - `git commit -m "MESSAGE"`: writes MESSAGE as a commit without a text editor

- `git log`: shows the log (history) of our commits
    - `git log --oneline`: shows the shorter oneline commit

- `git diff`: compare current uncommited state with last know git state
    - `git diff --staged`: runs git diff between the staging area and the last know state
- `git diff HEAD~<NUMBER>` : compares HEAD with commit <NUMBER> (relative)
- `git diff <HASH>` : compares HEAD with the commit in <HASH>
- `git restore --source <HASH OR HEAD~> <FILE>`: restore file to <HASH OR HEAD~> to <FILE>
    - `git checkout <HASH OR HEAD~> <FILE>`: restores file to <HASH OR HEAD~>
    - `git checkout <HASH OR HEAD~>`>: if you forget the file, you end up in detached head state
    - `git checkout main`: go back to main
    - `git switch main`: go back to main

## Working with remotes

- `git remote add <NAME> <URL>`: add the <URL> as a remote with the name <NAME>
- `git remote rm <NAME>` : removes the remote called <NAME>
- `git remote -v`: look at all the remotes you have
- `git push <WHERE> <WHAT>` : pushes the <WHAT> branch to <WHERE>
   - `git push origin main`
- `git pull <WHERE> <WHAT>`: pulls the <WHAT> branch in <WHERE> to local computer

## Branches 
- `git branch <NAME>`: create branch <NAME> where you are (HEAD)
- `git switch <NAME>`: move to the branch <NAME>
    - `git checkout <NAME>`: also move to the branch <NAME>
- `git switch -c <NAME>`: create and move to the branch <NAME> in 1 command
    - `git checkout -b <NAME>`: also create and move to branch <NAME> in 1 command
- `git merge <BRANCH>`: merge <BRANCH> into your current branch
- `git rebase`: command to change the history of a commit
    - Commits from `git merge` can be automatically combined
- `git rebase <BRANCH>` : incorporate changes from <BRANCH> into current branch
    - `git status`: is your friend 
    - `git add <FILE>` : to mark conflict resolution
    - `git rebase --continue`: move to next commit in rebase
    - `git rebase --abort`: undo git rebase step
- `git rebase -i <COMMIT>` `HEAD~ or <HASH> of commit to go into interactive reb    - you can make multiple commit changes here, e.g., `squash`/`s`
    - git rebase -i <HASH>^`: use ^ to include that commit in interactive rebase
    - `git stash` or `git commit`: to save work before moving branches 
        - `stash` is temporary 
        - `git stash list`: see your stashed commits
        - `git stash apply`: apply your last stashed commit 
        - `git stash clear`: clean up your stashes
- A `merge` on the remote is call a "pull request" or "merge request"
    - `git push <WHERE> <WHAT>`
    - To update a PR, we make the changes to the branch locally and re-`push`
