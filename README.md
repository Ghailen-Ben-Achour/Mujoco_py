# Mujoco_py
This work is based on the original [repository](https://github.com/openai/mujoco-py).

```Mujoco_py``` is a tool to use DeepMind's Mujoco simulation using Python. This tool is now open source for everyone.

In the following tutorial we use Mujoco 2.0.0 and Python3. We also use Linux as OS. 

# Installation on Linux

1. Download the binary files ```mujoco200``` for linux [here](https://www.roboti.us/download/mujoco200_linux.zip)
2. Download the activation key ```mjkey``` (available until October 18, 2031) from this [link](https://www.roboti.us/file/mjkey.txt)
3. Unzip the downloaded ```mujoco200``` directory into ```~/.mujoco/mujoco200```, and place your license key (mjkey.txt) at ```~/.mujoco/mjkey.txt```.
The folder should be organized as the following
```plain
└── ~/.mujoco
       ├── mujoco200
       |   ├── bin
       |   ├── doc
       |   └── include
       |   ├── model
       |   └── sample
       └── mjkey.txt
```

If you want to specify a nonstandard location for the key and package, use the env variables MUJOCO_PY_MJKEY_PATH and MUJOCO_PY_MUJOCO_PATH.

4. run the following command to install mujoco-py
```bash
pip3 install -U 'mujoco-py<2.1,>=2.0'
```
Note that this only works with Python3 (Python2 is not supported).

5. Open .bashrc file using the following command
```bash
vim ~/.bashrc
```
6. Add following line to .bashrc
```plain
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:~/.mujoco/mujoco200/bin
```
7. Save changes and restart your terminal
# Simple tests
To make sure that the installation was done successfully, you can run the following scripts.
```bash
python3 script.py
```

You can also run your simulations by running ```FetchReach.py``` or ```ant.py```.
```bash
python3 FetchReach.py 
```

![Project Image](images/fetch.png)

# Issues
One issue the you may encounter when  running ```FetchReach.py``` or ```ant.py```.
```plain
ERROR: GLEW initalization error: Missing GL version
```
To resolve this error you should:
1. Open .bashrc file using the following command
```bash
vim ~/.bashrc
```
2. Add following line to .bashrc
```plain
export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so
```
3. Save changes and restart your terminal
4. Run ```FetchReach.py``` or ```ant.py```:
```bash
python3 FetchReach.py [or ant.py]
```
