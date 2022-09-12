# ubuntu-jammy



## build image
docker build -t wenhsiaoyi/ubuntu-base:jammy .
docker login
docker push wenhsiaoyi/ubuntu-base:jammy



rename image
docker tag ttt:sss  XXX:333


remove image/container
docker rmi ttt:sss


docker run --rm -it wenhsiaoyi/ubuntu-base:jammy /bin/bash


## git log 查詢 commit 的檢查碼

###加入該次commit的檢查碼
$ git tag -a jammy 9a5ebe071985e7646f8929f8db62493ce1f814b1

$ git tag




$ git push origin jammy
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""

