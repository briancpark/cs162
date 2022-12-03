# CS 162



## Installation
This course makes the use of virtual machines, which can get messy real quick. But I have found a way for my own setups.

### M1 Mac Installation

```sh
brew install vagrant
```

The CS 162 course staff will retire the Vagrant repos as the semester progresses. To keep update, usually find project 0 in their [website](https://cs162.org). Otherwise, their most recent setups are located [here](https://cs162.org/static/hw/hw-intro/docs/setup/virtualbox-setup/).

```sh
mkdir cs162-vm
cd cs162-vm
vagrant init cs162/fall2022
vagrant up
vagrant ssh
```

### Linux Installation
Once inside a virtual machine, you will need to run the following commdands to get things running:

```sh
sudo apt install build-essential gcc-9 g++-9 fzf -y
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 9
sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 9

git clone --recurse git@github.com:briancpark/cs162.git
export PATH=$HOME/cs162/proj/src/utils:$PATH
```

We need to compile with gcc-9, as any higher version results in some compiler errors. Note that we can do this natively on Linux machine as well.