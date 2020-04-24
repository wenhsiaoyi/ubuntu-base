# ubuntu-focal



## build image
docker build -t wenhsiaoyi/ubuntu-base:focal .
docker login
docker push wenhsiaoyi/ubuntu-base:focal



rename image
docker tag ttt:sss  XXX:333


remove image/container
docker rmi ttt:sss


docker run --rm -it wenhsiaoyi/ubuntu-base:focal /bin/bash


## git log 查詢 commit 的檢查碼

###加入該次commit的檢查碼
$ git tag -a focal 8e168bd1f2c2c138c01617e80f49164f557451c3

$ git tag




$ git push origin focal
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""

