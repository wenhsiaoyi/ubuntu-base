# ubuntu-bionic



## build image
docker build -t wenhsiaoyi/ubuntu:bionic .
docker login
docker push wenhsialyi/ubuntu:bionic



rename image
docker tag ttt:sss  XXX:333


remove image/container
docker rmi ttt:sss


docker build -t wenhsiaoyi/ubuntu:bionic .


docker run -it <image> /bin/bash


## git log 查詢 commit 的檢查碼

###加入該次commit的檢查碼
$ git tag -a bionic 9fceb02

$ git tag




$ git push origin bionic
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""


