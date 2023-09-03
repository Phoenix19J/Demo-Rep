GIT Basic Commands ------->

git clone [URL]
git init
git remote add [alias-origin/upstream] [URL-SSH/HTTPS]
git remote remove [alias-origin/upstream] [URL-SSH/HTTPS]
git remote -v


git  add .
git  add <file.txt>
git  add folder/


git commit -m "The message for your commit"
git commit -am "..."                                # commits all staged changes and give a message
git commit --amend
git commit --amend -m "New name to change for prev commit"


git reset <hashcode>                                # removes previous commit and unstages changes in workspace
git reset --hard <hashcode>                         # removes previous commit and deletes changes in workspace
git reset HEAD~1                                    # removes 1 previous commit in history without losing unstaged changes --hard to remove both


git log --oneline
git log --graph --oneline
git log --pretty=oneline
git status
git fetch --prune
git diff


git restore --staged <file.txt>                     # removes a file from staged
git restore <file.txt>                              # discard changes of a unstaged file in working directory
git clean -f -i -n                                  # removes any untracked files -n is --dry-run


git stash                                           # saves staged and unstaged changes locally for later use
git stash -u -all                                   # saves staged and unstaged changes -u UNTRACKED files -all IGNORED files
git stash pop                                       # applies changes on workspace and removes them from stash
git stash apply [1]                                 # applies changes on workspace but still have changes in stash for later use [1] ie.stash@{1}
git stash list                                      # shows all stash list
git stash save "message for your stash"             # saves a stash with a message
git stash drop [0]                                  # drops latest stash from the list or a specific one [0] ie.stash@{0}
git stash clear                                     # DELETES all stash 


git push [alias-origin] [branch-main...]            # pushes local branch commits to remote branch commits
git push [alias-origin] [branch-main...] -f         # pushes local branch commits to remote branch commits -f FORCEFULLY UPDATE REMOTE
git push [alias-origin] -all                        # pushes local branch commits to remote branch commits -all pushes all branches to remote
git pull [alias-origin/upstream] [branch-main...]   # fetch and merge commits from the remote branch


git branch [Branch_Name]                            # Creates a new branch
git checkout [Branch_Name]                          # Selects the specified branch
git branch -m [New_branch_Name]                     # Changes the name of the selected branch to a new name specified
git branch -m [Old_Branch_name] [New_branch_Name]   # Changes the name of a branch to new provided name 
git branch -d/D [Branch_Name]                       # Deletes a branch
git merge [Branch_Name]                             # Merges the branch into current selected one, same as a pull request
git push origin --delete [Branch]                   # Deletes a remote branch
git push origin [New_Branch]                        # Adds a new remote branch


---There are sub-branches in GIT ie. $git push origin Feature/Homepage/Login--- Here sub-branch is Login under Homepage which is also under Feature Branch


git tag                                             # Shows all git tags made before
git tag -l "filter options"                         # shows git tag with a specific filter
git tag <Version>                                   # creates a light weight git tag
git tag -a <Version>                                # creates a annotated git tag
git tag <Version> -m "The message for a tag"        # creates a git tag with a message
git tag <Version> [Commit-ID]                       # creates a git tag on a particular commit in history
git show <Version>                                  # show details of a particular version ie.tag
git tag --delete <Version>                          # delete a particular version ie.tag
git push [alias-origin] [branch-main...] -tags      # pushes local branch commits to remote branch commits -tags pushes all local tags to remote
