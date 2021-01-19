### Ubutu shell 

> $ touch ~/Templates/Document
> $ gedit /home/{user name}/.bash_history
> $ gedit /root/.bash_history

--------------------------------------------------------------
### git first
```
git init
git add .
git status
git config --global user.email " "
git config --global user.name " "
git commit -m " "
git remote add origin {url}
git push -u origin master
```
---------------------------------------------------------------

### ROS2 version 

- ros2 run < > < >
- 


### Ubuntu20.04
- change build options
```
$ sudo update-alternatives --config {compile}
- ex) sudo update-alternatives --config gcc
- and next you choose a number
```
> if you change first time, you have to 
```
$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 8 --slave /usr/bin/g++ g++ /usr/bin/g++-8
$ sudo update-alternatives --install {$which gcc} gcc {$which gcc-8} 8 --slave {$which g++} g++ {$which g++-8}
```

### VSCODE
- Ctrl + Shift + ` : open terminal

- Ctrl + Shift + B : [Terminal] - [Configure Default Build Task] :: choose build active option
- F5 : debug and make excute file
- $ g++ {file name}.cpp >> make >> a.out
- $ ./a.out >> excute your file

#### c++ compile
- #include <pthread.h> 포함 파일일 경우 : g++ -pthread




[reference]
- https://goodgodgd.github.io/ian-flow/archivers/vscode-tutorial

정리하기!
