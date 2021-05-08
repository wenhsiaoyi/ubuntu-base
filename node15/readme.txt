# ubuntu-bionic



## build image
docker build -t wenhsiaoyi/ubuntu-base:node15 .
docker login
docker push wenhsiaoyi/ubuntu-base:node15



rename image
docker tag ttt:sss  XXX:333


remove image/container
docker rmi ttt:sss



docker run --rm -it wenhsiaoyi/ubuntu-base:node15


## git log 查詢 commit 的檢查碼

###加入該次commit的檢查碼
$ git tag -a node15 cd85c06

$ git tag




$ git push origin node15
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""


