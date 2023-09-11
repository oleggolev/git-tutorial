# Basic shared repository workflow:
**__Always pull from remote repository before making any changes locally__**: ```git pull origin {branch}```
### Making a small change
***
Make your changes on the master branch and stage+commit them directly: 
```
git add {filename(s)}
git commit -m "description of what you changed"
git push origin master
```

### Working on a feature/functionality
_i.e. if you feel you'll need several commits/write multiple lines of code_
***
0. Check which branch you're currently on as a precaution: ```git branch```
This should list all local branches, along with an asterix besides **master**

1. Create a new working branch: ```git checkout -b MyNewBranch```

Re-run ```git branch``` to confirm you're on MyNewBranch (there should be an asterix next to it)

Tip: Give a semantic branch name, such as _feature-logout_ or _database-fixes_. Try to do the same for commit messages

2. Make changes locally and stage them with ```git add {filename(s)}```

3. Commit your changes locally with ```git commit -m "description of your commit"```

4. Repeat Steps (2) and (3) as you make more and more changes and add more commits to your new branch

[More info on git branching](https://gist.github.com/digitaljhelms/4287848)

5. Push your changes onto the remote Github repository using ```git push origin MyNewBranch```

_Note: if you're doing this the first time, this command also adds your new local branch remotely. You can confirm this by going to the repo on Github. Keep pushing as and when necessary_

6. **Only when you have finished working on your feature/functionality and have ensured it it working**, click on your branch name on github --> click on “Pull Request” button (URC) --> click on “Send Pull Request" --> Compare and Merge Pull Request. Delete the branch when merged if you are done with that feature branch.

Imp: If changes have been made to the **master** branch while you were working on the **MyNewBranch** branch, you might want to merge these changes _into_ **MyNewBranch** as you continue working on your feature to keep **MyNewBranch** up-to-date with the changes to **master** or so you are able to send a pull request later without any merge conflicts. You can do this with ```git merge master``` (first, make sure to confirm you are on **MyNewBranch**). Note: you might have to resolve merge conflicts depending on what changes were made.

7. Back in terminal after the merge:
```shell
$ git checkout master {you are now on master}
$ git pull {pulls your newly merged changes locally if the pull request has been approved}
$ git branch -d MyNewBranch (this deletes the old branch locally)
```

Repeat the process.
