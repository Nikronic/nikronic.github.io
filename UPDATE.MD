- https://unix.stackexchange.com/questions/681282/can-i-clone-a-branch-of-an-unrelated-remote-repo-into-a-branch-of-my-git-repo-a
- https://stackoverflow.com/questions/1709177/pull-a-certain-branch-from-the-remote-server

Practically you should:
1. create a local branch
2. create a new remote pointing to the desired remote repo (al-folio)
3. fetch the desired remote repo 
4. pull the desired branch of the remote repo into the local branch
5. This results in merge conflicts. Fix them manually.
6. Now since there are no conflicts, just do a pull request to the main branch of the local repo. After this, update should be completed.
