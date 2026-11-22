# Git

## Basic Commands
```
git init
git init --bare
git add
git add -u
git add -A
git commit
git commit -m "Commit Message"
git status
git diff
git diff <Commit Object Name>
git diff --cached
git diff main..origin/main
git log
git log -p
git restore --worktree .
git restore --staged .
git revert <Commit Object Name>
git branch
git branch <Branch Name>
git branch {-d|-D} <Branch Name>
git switch <Branch Name>
git merge <Branch Name>
git push <Destination Repo> <Source Branch>:<Destination Branch>
git push <Alias Name> --delete <Remote Branch Name>
git clone <Source Repo>
git remote add <Alias Name> {Local Repo Path | URL};
git remote -v
git fetch <Alias Name>
git fetch --prune
git merge <Alias Name>/<Repo Name>
git pull
```

## Branch Name Examples
| Branch Name | Use |
| --- | --- |
| main | Main |
| develop | Integration of the Development Version |
| feature/* | Add New Feature |
| bugfix/* | Bug Fix |
| docs/* | Document Revision |
| test/* | Test Codes |

## User config
```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global init.defaultBranch main
```

## Start SSH Agent
```
eval "$(ssh-agent -s)"
```

## Stop SSH Agent
### Method 1
```
ssh-agent -k
```
### Method 2
```
pkill ssh-agent
```

## Bare Repository
### Step 1: Register the client's SSH public key on the server
```
vim /home/git/.ssh/authorized_keys
```

### Step 2: Create a bare repository on the server
```
mkdir -p /home/git/<Repository Name>.git
cd /home/git/<Repository Name>.git
git init --bare --shared
```

### Step 3: First data upload from the client
> [!TIP] You need to specify the command path on the client side for the server to perform receive/upload operations.
```
git init
git add *
git commit -m "Initial commit"
git remote add origin ssh://git@<IP Address>:<Port Number>/home/git/<Repository Name>.git
git push --receive-pack </path/to/server's/git-receive-pack> -u origin main
git config remote.origin.receivepack </path/to/server's/git-receive-pack>
git config remote.origin.uploadpack </path/to/server's/git-upload-pack>
```

### Step 4: Clones by other clients
```
git clone --upload-pack </path/to/server's/git-upload-pack> ssh://git@<IP Address>:<Port Number>/home/git/<Repository Name>.git
```

### Daily workflow
```
git pull --upload-pack </path/to/server's/git-upload-pack>
git push --receive-pack </path/to/server's/git-receive-pack>
```

