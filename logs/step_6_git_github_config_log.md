**git config --global user.name**  
**  
  
**git config --global user.email**  
****os@gmail.com  
  
**git config --global init.defaultBranch**  
**git branch --show-current   # 현재 저장소 기준 브랜치명 확인**  
main  
  
**git config --list**  
credential.helper=osxkeychain  
user.name=**  
user.email=****os@gmail.com  
credential.helper=osxkeychain  
core.repositoryformatversion=0  
core.filemode=true  
core.bare=false  
core.logallrefupdates=true  
core.ignorecase=true  
core.precomposeunicode=true  
remote.origin.url=https://github.com/****os/E1_1.git  
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*  
branch.main.remote=origin  
branch.main.merge=refs/heads/main  
branch.main.vscode-merge-base=origin/main  
  
**cd ~/E1_1   # 또는 현재 작업 폴더**  
**git remote -v**  
origin	https://github.com/****os/E1_1.git (fetch)  
origin	https://github.com/****os/E1_1.git (push)  
  
**git remote set-url origin https://github.com/****os/E1_1.git**  
**git remote -v**  
origin	https://github.com/****os/E1_1.git (fetch)  
origin	https://github.com/****os/E1_1.git (push)  
  
**git push**  
Everything up-to-date  
  
**git config --list**  
credential.helper=osxkeychain  
user.name=**  
user.email=****os@gmail.com  
credential.helper=osxkeychain  
core.repositoryformatversion=0  
core.filemode=true  
core.bare=false  
core.logallrefupdates=true  
core.ignorecase=true  
core.precomposeunicode=true  
remote.origin.url=https://github.com/****os/E1_1.git  
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*  
branch.main.remote=origin  
branch.main.merge=refs/heads/main  
branch.main.vscode-merge-base=origin/main  
