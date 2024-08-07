# DiffuserLite

Code for the paper "DiffuserLite: Towards Real-time Diffusion Planning".

## Installation
1. Create and activate conda environment
```bash
$ conda create -n diffuserlite python==3.9
$ conda activate diffuserlite
```
2. Install dependencies
```bash
$ conda install pytorch==2.2.2 torchvision==0.17.2 pytorch-cuda=12.1 -c pytorch -c nvidia
$ git clone https://github.com/diffuserlite/diffuserlite.github.io.git
$ cd diffuserlite.github.io
$ pip install -e .
```
3. Install D4RL
```bash
$ sudo apt-get install libosmesa6-dev libgl1-mesa-glx libglfw3 libglew-dev patchelf
$ cd <PATH_TO_D4RL_INSTALL_DIR>
$ git clone https://github.com/Farama-Foundation/D4RL.git
$ cd D4RL
$ pip install -e .
```

## Running the code
Train and evaluate DiffuserLite on D4RL-MuJoCo benchmark tasks
```bash
# DiffuserLite-R1
$ python pipelines/diffuserlite_d4rl_mujoco.py task=halfcheetah-medium-v2 mode=training
$ python pipelines/diffuserlite_d4rl_mujoco.py task=halfcheetah-medium-v2 mode=inference
# Reflow for DiffuserLite-R2
$ python pipelines/diffuserlite_d4rl_mujoco.py task=halfcheetah-medium-v2 mode=prepare_dataset
$ python pipelines/diffuserlite_d4rl_mujoco.py task=halfcheetah-medium-v2 mode=reflow
$ python pipelines/diffuserlite_d4rl_mujoco.py task=halfcheetah-medium-v2 mode=inference test_model=R2
```
Please see `configs/diffuserlite` for more configuration options and usage on other tasks.

