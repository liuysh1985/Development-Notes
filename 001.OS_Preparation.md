# How to prepare a proper operation and development environment

## Choose the OS

RHEL/CentOS is the better OS for production usage. But for development, maybe the GUI is more important than OS. So Ubuntu 18.04 is the best choice for my scenario.

## Set the faster 3rd-party repositories of Ubuntu 18.04

+ Edit the file /etc/apt/sources.list, and paste lines into it.

```command
# sudo mv/etc/apt/sources.list /etc/apt/sources.list.bak
# sudo vi /etc/apt/sources.list
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable
deb-src [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable
# sudo apt update
# sudo apt -y upgrade
```

+ Then install packages if necessary.

```command
# sudo apt install gcc make vim openjdk-8-jdk python-pip
```

## Set the faster 3rd-party repositories of PIP

+ Edit the file /etc/pip.conf.

```config
[global]
index-url =  https://mirrors.aliyun.com/pypi/simple/
```

+ Upgrade pip and install python packages

```command
# sudo pip install pip --upgrade
# sudo pip install ansible virtualenv
# sudo pip install -U "pylint<2.0.0" pytest-runner
```

## Abount IDE

1. **Download "*Visual Studio Code*" from offical site**

   [VSC Download](https://code.visualstudio.com/Download)

2. **Recommend Extensions**

   1. Python
   2. Ansible
   3. Terraform
   4. Markdown Preview Github Styling
   5. markdownlint
   6. Kubernetes

---

### Waiting for more notes