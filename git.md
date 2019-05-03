
# Config

## Get

```bash
git config --get remote.origin.url
```
## Set 

```bash
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```

###Caching your GitHub password in Git
```git
git config --global credential.helper cache
```

#Remove
###Remove Directory
```bash
git rm --cached mylogfile.log
```
###Remove file
```bash
git rm --cached -r mydirectory
```
###Remove branch
```bash
git branch -d branch_name
git branch -D branch_name
```

####Delete a remote GIT branch
```bash
git push <remote_name> --delete <branch_name>
```
	