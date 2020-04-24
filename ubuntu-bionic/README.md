# ubuntu-bionic



## build image
docker build -t wenhsiaoyi/ubuntu-base:bionic .
docker login
docker push wenhsiaoyi/ubuntu-base:bionic



rename image
docker tag ttt:sss  XXX:333


remove image/container
docker rmi ttt:sss


docker run --rm -it wenhsiaoyi/ubuntu-base:bionic /bin/bash


## git log 查詢 commit 的檢查碼

###加入該次commit的檢查碼
$ git tag -a bionic bd30eb69abec4c52b09333b153e2413d746278f1

$ git tag




$ git push origin bionic
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""

