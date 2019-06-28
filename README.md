# my Git Commands
My most used git commands for the operations that are not available through github desktop software
## Change text editor
For squashing commits you need this. Replace your text editor at least with notepad)
##### For notepad
```
git config core.editor notepad
```

##### For sublime or notepad++
```
git config --global core.editor \
"'C:/Program Files/Sublime Text 3/sublime_text.exe' -multiInst -notabbar -nosession -noPlugin"
```
or
```
git config --global core.editor \
"'C:/Program Files/Sublime Text 3/sublime_text.exe' -multiInst"
```

## Delete a branch
```
git checkout master
git push --delete origin branch_Name
git branch -D branch_Name
```
## Copy current branch to a new branch 
git checkout -b new_Branch_Name

## Squash commits (merge)
use the commit ID of one commit before your first commit, 
```
git rebase --interactive 5c63ce3029fd372fb63d07d77c74cfae1c377ab1
```
When editor is opened, 
replace pick which squash, 
make the first squash pick again. (All other commits will be merged to this one)
Save and close the first editor, 
the second editor will be opened for editing comments. 
Use the first line and some enters after that as the title. 
Write your comments below that (things after # are ignored)
In the end:
```
git push --force

```
Alternative method with number (not much useful)
```
git rebase --interactive HEAD~[53]
```
## Reword last commit's comment
```
git commit --amend -m "title" -m "

Your comment here
use enter for different lines

		"
```
```
git push --force
```
## Merge branch to master
```
git checkout master
git merge other_Branch
git push --force
```
## Remove last commit
```
use the id one before that
git reset --hard e78df3ad58a71eca510a76b716404841d6d4fe20
git push --force
```
or
```
git reset --hard HEAD^
git push origin -f
```

## Rename branch:
```
git checkout old_name
git branch -m new_name
git push origin --delete old_name
git push origin -u new_name
```