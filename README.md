# Dockerfile_kunpeng
Build docker images on kunpeng. Make it easy to test on specific software.


usage:

```
git clone https://github.com/LyleLee/Dockerfile_kunpeng.gi
cd Dockerfile_kunpeng
cd Dockerfile_ubuntu_pocl ## could be another dir
docker build -t pocl .
docker run -it --rm --name pocl_container pocl
```
