# CS 162

CS 162 is Operating Systems and Systems Programming. I took this offering in Fall 2021 under Ion Stoica. This repo contains my development setup and notes.

There is no source code here and the submodules are made private. Please DO NOT contact me for source code.

## Installation

This course makes the use of virtual machines, which can get messy real quick. But I have found a way to make it work for my own setups.

### Apple Silicon Installation

First, you need to install Vagrant. We can do that via any package manager:

```sh
brew install vagrant
```

Then you will need to install VirtualBox, which you can download [here](https://www.virtualbox.org/wiki/Downloads). As of now, VirtualBox should support Apple Silicon.

The CS 162 course staff will retire the Vagrant repos as the semesters progress. To keep up to date, I usually go find Project 0 in their [website](https://cs162.org). Otherwise, their most recent setups are located [here](https://cs162.org/static/hw/hw-intro/docs/setup/virtualbox-setup/).

Run these series of commands to setup and login to the virtual machine:

```sh
mkdir cs162-vm
cd cs162-vm
vagrant init cs162/fall2022
vagrant up
vagrant ssh
```

### Linux Installation

Once inside a virtual machine, you will need to run the following commands to get things running:

```sh
sudo apt install build-essential gcc-9 g++-9 fzf -y
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 9
sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 9

git clone --recurse git@github.com:briancpark/cs162.git
export PATH=$HOME/cs162/proj/src/utils:$PATH
```

We need to compile with `gcc-9`, as any higher version will result in compilation errors. Note that this will work and get you running on any Ubuntu machine as well.
