#### hangul setting
$ sudo apt install ibus-hangul
$ ibus-setup > install method > add > korean
- settings > region & Language > korean hangul


[Ubuntu20.04 tensorflow-gpu 사용](https://webnautes.tistory.com/1428)
1. gcc version 설정 python 버전도 아래 처럼 진행 할 수 있음
```
$ sudo apt update

$ sudo apt -y install build-essential
$ sudo apt -y install gcc-8 g++-8 gcc-9 g++-9

$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 8 --slave /usr/bin/g++ g++ /usr/bin/g++-8
$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 9 --slave /usr/bin/g++ g++ /usr/bin/g++-9

$ sudo update-alternatives --config gcc
```
> sudo update-alternatives --config gcc : gcc version 설정하기

2. python 
```
$ sudo apt install -y zlib1g-dev libbz2-dev libreadline-dev libssl-dev libsqlite3-dev libffi-dev curl file git python3-pip make build-essential
$ sudo pip3 install virtualenvwrapper
$ curl https://pyenv.run | bash
$ echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(pyenv init -)"' >> ~/.bashrc
$ echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
$ source ~/.bashrc
$ pyenv install 3.7.7 
//tensorflow는 3.7.7 지원함 
$ sudo apt install python-is-python3
$ pyenv virtualenv 3.7.7 tf2 >> python3.7.7 version으로  virtual 만드는 거
$ pyenv versions >> version 확인
$ pyenv global tf2(version 중에 가고 싶은 거)

```

```
pyenv 설정
export PATH="/home/ch/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

[pyenv 설명](http://taewan.kim/post/python_virtual_env/)


3. CUDA
```
cuda 다운
$ wget http://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda_10.1.243_418.87.00_linux.run
$ chmod +x cuda_10.1.243_418.87.00_linux.run 
$ sudo ./cuda_10.1.243_418.87.00_linux.run 
> continue
> accept
> driver 해제 후 install

cuda toolkit 환경변수 추가
$ echo 'export PATH=$PATH:/usr/local/cuda-10.1/bin' >> ~/.bash_profile
$ echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-10.1/lib64' >> ~/.bash_profile
$ echo 'export CUDADIR=/usr/local/cuda-10.1' >> ~/.bash_profile
$ source ~/.bash_profile
추가하면 이렇게 뜸
$ ls -l /usr/local/ 
lrwxrwxrwx  1 root root   21  7월 19 17:09 cuda -> /usr/local/cuda-10.1/
```

#### nvidia setting
```
$ sudo lshw -C display 
- see your driver version everything
$ nvidia-smi 
- driver version check
$ ubutntu-drivers devices
- recommended > drive install
$ sudo add-apt-repository ppa:graphics-drivers/ppa
- add repository함
$ sudo apt-get install nvidia-driver-<recommended>
successfully >> nvidia-smi check
```
>> software & update 가면 쉬움

#### CUDA 설치
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
sudo mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/11.2.0/local_installers/cuda-repo-ubuntu2004-11-2-local_11.2.0-460.27.04-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2004-11-2-local_11.2.0-460.27.04-1_amd64.deb
sudo apt-key add /var/cuda-repo-ubuntu2004-11-2-local/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda
```

