# Android SDK image
included sdk 30
included nodejs 15
included JDK 8



## build image
docker build -t wenhsiaoyi/ubuntu-base:androidsdk30.0.3 --cache-from wenhsiaoyi/ubuntu-base:node15 .
docker login
docker push wenhsiaoyi/ubuntu-base:androidsdk30.0.3



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
git tag -a androidsdk30.0.3 9b53f986

git tag




$ git push origin androidsdk
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""


# 檔案異動
git add filename
git commit -m "up"
git push


