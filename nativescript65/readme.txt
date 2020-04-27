# ubuntu-bionic



## build image
docker build -t wenhsiaoyi/ubuntu-base:ns65 .
docker login
docker push wenhsiaoyi/ubuntu-base:ns65



rename image
docker tag ttt:sss  XXX:333


remove image/container
docker rmi ttt:sss



docker run --rm -it wenhsiaoyi/ubuntu-base:ns65


##
docker run -it --rm wenhsiaoyi/ubuntu-base:ns65 /opt/android-sdk/tools/bin/sdkmanager --sdk_root=/opt/android-sdk --update


docker run --env JAVA_OPTS="-Xms1024M -Xmx2048M" -it  -p 5037:5037  --rm -v $PWD:`pwd` -w `pwd` --name ns65 wenhsiaoyi/ubuntu-base:ns65 tns



docker run --env JAVA_OPTS="-Xms1024M -Xmx2048M" -it  -p 5037:5037  -v $PWD:`pwd` -w `pwd` --name ns65 wenhsiaoyi/ubuntu-base:ns65

docker start -i ns65



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


# 檔案異動
git add filename
git commit -m "up"
git push
