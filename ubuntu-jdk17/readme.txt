# ubuntu-bionic



## build image
docker build -t wenhsiaoyi/ubuntu-base:jdk17 .
docker login
docker push wenhsiaoyi/ubuntu-base:jdk17



rename image
docker tag ttt:sss  XXX:333


remove image/container
docker rmi ttt:sss



docker run --rm -it wenhsiaoyi/ubuntu-base:jdk17


## git log 查詢 commit 的檢查碼

###加入該次commit的檢查碼
$ git tag -a openjdk17 bf28576298b7c37a6bd30c06b4d12756ae2fc7f4

$ git tag




$ git push origin openjdk17
$ git push origin --tags


git revert HEAD --no-edit

git reset HEAD

git add filename

git commit  -m ""


