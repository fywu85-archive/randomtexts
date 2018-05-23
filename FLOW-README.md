# Installation
This is the installation guide to install FLOW on Ubuntu 16.04. The full FLOW environment requires `flow`, `rllab-multiagent`, `sumo`, and `ray`.

## Dependencies
```shell
sudo apt update && sudo apt upgrade
sudo apt install cmake swig libgtest-dev python-pygame python-scipy autoconf libtool pkg-config libgdal-dev libxerces-c-dev libproj-dev libfox-1.6-dev libxml2-dev libxslt1-dev
```

## Anaconda
```shell
cd ~
wget https://repo.anaconda.com/archive/Anaconda2-5.1.0-Linux-x86_64.sh
sh ./Anaconda2-5.1.0-Linux-x86_64.sh
conda env create -f environment.yml
```

## sumo
```shell
cd ~
git clone --recursive https://github.com/eclipse/sumo
cd sumo
git fetch origin refs/replace/*:refs/replace/*
make -f Makefile.cvs
./configure
make
sumo/bin/sumo --version
```

## rllab-multiagent
```shell
cd ~
git clone https://github.com/cathywu/rllab-multiagent.git
cd rllab-multiagent
git clone https://github.com/berkeleyflow/flow.git
python setup.py develop
cd flow
python setup.py develop
```

## flow
```shell
cd ~/rllab-multiagent
git clone https://github.com/berkeleyflow/flow.git
cd flow
python setup.py develop
```

## ray
