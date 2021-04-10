# ubuntu-bionic



## build image
docker build -t wenhsiaoyi/ubuntu-base:ns801 --cache-from wenhsiaoyi/ubuntu-base:androidsdk30 .
docker login
docker push wenhsiaoyi/ubuntu-base:ns801



alias ns='docker run --env JAVA_OPTS="-Xms1024M -Xmx4096M" -it  -p 5037:5037  -v /opt/projects:/opt/projects -w /opt/projects --name ns8 wenhsiaoyi/ubuntu-base:ns801 bash'

alias ns='docker run --env JAVA_OPTS="-Xms1024M -Xmx4096M" -it  -p 5037:5037 --rm -v $PWD:`pwd` -w `pwd` --name ns8 wenhsiaoyi/ubuntu-base:ns801 bash'
alias ns='docker start -i ns8'


docker run --rm -it wenhsiaoyi/ubuntu-base:ns801


第一次 create container
docker run --env JAVA_OPTS="-Xms1024M -Xmx4096M" -it  -p 5037:5037  -v $PWD:`pwd` -w `pwd` --name ns8 wenhsiaoyi/ubuntu-base:ns801 ns

進入容器
docker start -i ns8

##
docker run -it --rm wenhsiaoyi/ubuntu-base:ns7 /opt/android-sdk/tools/bin/sdkmanager --sdk_root=/opt/android-sdk --update


docker run --env JAVA_OPTS="-Xms1024M -Xmx4G" -it  -p 5037:5037  --rm -v $PWD:`pwd` -w `pwd` --name ns8 wenhsiaoyi/ubuntu-base:ns801



docker run --env JAVA_OPTS="-Xms1024M -Xmx4G" -it  -p 5037:5037  -v $PWD:`pwd` -w `pwd` --name ns7 wenhsiaoyi/ubuntu-base:ns8

#



# clean unused images
docker image prune



## git log 查詢 commit 的檢查碼


# 忽略 在目錄下新增一個名為 .gitignore 的檔案
touch .gitignore
nano .gitignore

加入路徑與檔名

# 清除cache
git rm --cached

# 清除忽略的檔案
git clean -fX


透過 git checkout -- <file> 來還原檔案的內容

使用 git rm <file> 來告知 git，哪些是我們將要刪除的檔案

使用 git add -u 加入所有被更動的檔案（包含 modified 及 deleted）

使用 git mv <file> <new_name> 來重新命名檔案



###加入該次commit的檢查碼
$ git tag -a ns7 fc96528

$ git tag




$ git push origin bionic
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""


# 檔案異動
git add filename
git commit -m "up"
git push




Method 1. Use /etc/*-release file to display Linux distro version
To find out what version of Linux (distro) you are running, enter the following cat command at the shell prompt:
$ cat /etc/*-release

