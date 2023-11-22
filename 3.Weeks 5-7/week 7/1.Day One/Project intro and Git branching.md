- Project is a reddit clone
- The api will server user, comments, articles, analytics and stuffs
- All tests will run before you commit any changes
- The repo must be cloned not forked
- When ticket 2 is done, you should wait for it to be reviewed before carrying on
- git remote -v tells you what remote your local repo is pointing too


```bash
git checkout -b obi-news-1
#Here we create a new branch and switch to it
#..After doing some work to it and committing regularly
git add <FILES>
git commit -m "complete task 5"
git push origin <Current Branch name> #Push local branch to new remote branch obi-news-1
git checkout main #Return back to the main branch
git pull origin main #When the pr has been approved
```

- You can then do a "/nchelp pr" and send the pull request link
- !!!YOU SHOULD ONLY BRANCH FROM MAIN!!!
- Merge conflicts should be resolved before doing "/nchelp pr" 
- You can delete old branches with git branch -d \<branchname>


# tl;dl
- always checout to main and pull the altest changes before branching
- name branches after the ticket you are working on
- endpoints should be fully tested including errors
- there should be no .only, console.log or commented out code
- you should only include code on the branch that relates to that task
- once you are happy with your code let us know via /nchelp pr
- You can start a new task on a new branch, checkout back to main
- if you hav efeedback that requires changes, cheout back to the branch for that task to complete the work. push the changes up to that branch and send us a new nchelp
- do not mark a task as complete until it's been approved