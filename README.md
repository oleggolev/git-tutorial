# Basic shared repository workflow:
**__Always pull from remote repository before making any changes locally__**: ```git pull origin [branch-name]```
### Making a small change
***
Make your changes on the main branch and stage / commit them directly: 
```
git add [filename(s)]
git commit -m "description of what you changed"
git push origin main
```

### Working on a feature/functionality
_i.e. if you feel you'll need several commits/write multiple lines of code_
***
1. Check which branch you're currently on as a precaution: ```git branch```
This should list all local branches, along with an asterix besides the branch you are currently on.

2. Create a new working branch: ```git checkout -b my-branch```

_Note: This command will copy all contents of the branch you were on into `my-branch`. Re-run ```git branch``` to confirm you're on `my-branch`. Try to give a semantic branch name, such as `feature-logout` or `database-fixes`. Try to do the same for commit messages._

3. Make changes locally and stage them with ```git add [filename(s)]```

_Note: To quickly add all files (recursively) in and down your current directory. you can use `git add .`_

4. Commit your changes locally with ```git commit -m "description of what you changed"```

5. Repeat Steps (2) and (3) as you make more and more changes and add more commits to your new branch

6. Push your changes onto the remote Github repository using ```git push origin my-branch```

_Note: if you're doing this the first time, this command also adds your new local branch remotely. You can confirm this by going to the repo on Github. Keep pushing as and when necessary._

7. **Only when you have finished working on your feature/functionality and have ensured it is working**, you may send a pull request (PR) to have your `my-branch` changes proof-read by others and merged into `main`. To do this, first navigate to your repository on GitHub. Usually, if you pushed your branch changes recently, you will see a green button that says something like "Create pull request" with your branch name at the top of the page. If you do not see this, you can create a PR manually by first clicking on the “Pull Requests” tab, then “New pull request". From here, select `base: main` and `compare: my-branch` before clicking "Create pull request." With the PR created, you can easily view the changes you've made, resolve any conflicts, have your teammates proof-read your code, and finally merge your code into `main`.

_Note: If you have an open PR (not yet merged) for branch `my-branch` but continue working on `my-branch`, as you commit and push changes upstream, they will be reflected in the PR automatically!_

_Note: If changes have been made to `main` while you were working on `my-branch`, you might want to merge these changes into `my-branch` to keep `my-branch` up to date with `main`. This will also enable you to send a pull request later without any merge conflicts! You can do this by first confirming that you are on `my-branch` and then running ```git merge main```. You might have to resolve merge conflicts depending on what changes were made._

8. **Only when the feature is complete, `my-branch` is merged and will no longer be used**, you may delete it using one of two methods. The first method is to navigate to your repository on GitHub, click on "Branches", and click the trash icon near the branch you want to delete. The second method is to use the `git push -d origin <my-branch>` command.

_Note: Both of these methods delete your branch remotely. To also delete it locally (and stop it from showing up in the `git branch` list), run the following back in terminal:_
```shell
$ git checkout main {you are now on master}
$ git pull {pulls your newly merged changes locally if the PR was merged}
$ git branch -d my-branch (deletes the branch locally)
```

Repeat the process.

_Note: You can find more info on git usage and more detailed explanations [here](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)_
