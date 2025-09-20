- `git init`: intialize current folder as a git repository
- `git clone <URL>`: brings the git repo from <URL> to current folder
- `git status`: tell us what we need to know about our repository

- `git add <FILE>` : add <FILE> to the staging area
- `git commit`: open a text editor to write commit message
    - `git commit -m "MESSAGE"`: writes MESSAGE as a commit without a text editor

- `git log`: shows the log (history) of our commits
    - `git log --oneline`: shows the shorter oneline commit

- `git diff`: compare current uncommited state with last know git state
    - `git diff --staged`: runs git diff between the staging area and the last know stated
- `git diff HEAD~<NUMBER>` : compares HEAD with commit <NUMBER> ago (relative)
- `git diff <HASH>` : compares HEAD with the commit in <HASH>
- `git restore --source <HASH OR HEAD~> <FILE>`: restore file to <HASH OR HEAD~> or <FILE>
    - git checkout <HASH OR HEAD~> <FILE>`: restores file to <HASH OR HEAD~>
    - `git checkout <HASH OR HEAD~>`>: if you forget the file, you end up in detachedHead State
    - `git checkout main`: go back to main
    - `git switch main`: go back to main
