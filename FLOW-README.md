# Installation
This is the installation guide to install FLOW on Ubuntu 16.04. The full FLOW environment requires `sumo`, `rllab-multiagent`, `flow`, and `ray`.

## Dependencies
```shell
sudo apt update && sudo apt upgrade
sudo apt install cmake swig libgtest-dev python-pygame python-scipy autoconf libtool pkg-config libgdal-dev libxerces-c-dev libproj-dev libfox-1.6-dev libxml2-dev libxslt1-dev build-essential curl unzip flex bison python python-dev python3-dev
sudo pip2 install cmake cython
```

## Anaconda
```shell
cd ~
wget https://repo.anaconda.com/archive/Anaconda2-5.1.0-Linux-x86_64.sh
sh ./Anaconda2-5.1.0-Linux-x86_64.sh
conda env create -f environment.yml # If failed, remove the flow env and retry.
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
echo 'export SUMO_HOME="$HOME/sumo"' >> ~/.bashrc
echo 'export PATH="$HOME/sumo/bin:$PATH"' >> ~/.bashrc
echo 'export PYTHONPATH="$HOME/sumo/tools:$PYTHONPATH"' >> ~/.bashrc
sumo/bin/sumo --version
```

## rllab-multiagent
```shell
cd ~
git clone https://github.com/cathywu/rllab-multiagent.git
cd rllab-multiagent
python setup.py develop
echo 'export PYTHONPATH="$HOME/rllab-multiagent:$PYTHONPATH"' >> ~/.bashrc 
```

## flow
```shell
cd ~/rllab-multiagent
git clone https://github.com/berkeleyflow/flow.git
cd flow
python setup.py develop
echo 'export PYTHONPATH="$HOME/rllab-multiagent/flow:$PYTHONPATH"' >> ~/.bashrc 
```

## ray
```shell
cd ~
git clone https://github.com/eugenevinitsky/ray.git
cd ray/python
sudo python setup.py develop
```
