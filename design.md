## design

The design software allows you to rapidly test designs and discard bad ones before spending time and supplies to build them. However, if you already have a design in mind and the kit in hand, you skip the simulation and go ahead and [build](/build) it now!
<br><br>

The software has three parts:&nbsp;
<a href="#viz">**viz**</a>,&nbsp; 
<a href="#sim">**sim**</a>,&nbsp;
<a href="#evo">**evo**</a>.
<br>

<a name="viz"></a>
# **viz**
You can manually design voxelbots by drawing them in our graphical user interface 
[voxcraft-viz](https://github.com/liusida/voxcraft-viz), 
which was originally forked from [voxcad](https://github.com/jonhiller/VoxCAD).
<br>

<a name="mac"></a>
### **install on macOS**

On macOS follow these steps to install viz:
```bash
brew install cmake
brew install boost
brew install qt5
brew install glfw3
brew cask install xquartz
brew install freeglut
brew install glm
brew install mesa
```
This will take a while...
```bash
git clone https://github.com/liusida/voxcraft-viz.git

cd voxcraft-viz/
mkdir build
cd build/
  
cmake -DQt5_DIR=$(brew --prefix qt5)/lib/cmake/Qt5 -DCMAKE_BUILD_TYPE=Release ..
  
make -j 10
```
Done!
  
Check for [mac updates](https://github.com/liusida/voxcraft-viz/blob/master/InstallOnMac.md).
<br><br>


<a name="linux"></a>
### **install on linux**

On linux you can install with snap
```bash
sudo snap install voxcraft-viz
```

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-white.svg)](https://snapcraft.io/voxcraft-viz)
<br>

It's that simple!<br>

But just in case, here's a video of the installation process:
<iframe width="100%" height="400" src="https://www.youtube.com/embed/lEzzASQn-_M" frameborder="0" allowfullscreen></iframe>
<br><br>


## **drawing a robot in viz**

You can draw a custom robot in voxcraft-viz using your mouse and then press play to watch its behavior.
<iframe width="100%" height="400" src="https://www.youtube.com/embed/jvxQjlrLgQo" frameborder="0" allowfullscreen></iframe>
<br><br>


## **playing a history file in viz**

voxcraft-viz can also be used to replay the behavior of robots that have already been simulated elsewhere: 
their **history**.

You can download one of these prerecorded history files 

[**`m190.history`**](https://github.com/liusida/voxcraft-viz/raw/master/demos/m190.history)
&nbsp;&nbsp;
[**`m805.history`**](https://github.com/liusida/voxcraft-viz/raw/master/demos/m805.history)

and replay it in voxcraft-viz:

<iframe width="100%" height="400" src="https://www.youtube.com/embed/ytQ7dj3yE8M" frameborder="0" allowfullscreen></iframe>
<br>


<a name="sim"></a> 
# **sim**

[voxcraft-sim](https://github.com/liusida/voxcraft-sim) simulates voxels in parallel on a gpu. 
The simulations are headless (without graphics) and linux-only,
but a history file can be recorded that traces the behavior of each voxel within a simulation. 
This history can then be replayed on a mac or linux machine without a gpu.
<br>

### **run in google colab** 
Create a new notebook and go to Menu->Runtime->Change runtime type, select GPU.
<br>

Then, copy and run the script from this (readonly) example 
[notebook](https://colab.research.google.com/drive/1yiqw7Uq3W3CgYCinXq4t808M2l7uuLv1).
<br>

It will produce `a.history` which can be played in voxcraft-viz to visualize the simulated behavior.
<br>


### **install from scratch**
If you have access to Nvidia graphic cards you can compile voxcraft-sim from scratch.
The most difficult part is installing
[CUDA 10.1](https://developer.nvidia.com/cuda-10.1-download-archive-base).
<br>

Once you have CUDA **10.1**, the rest is easy:
```bash
sudo apt-get update
sudo apt-get install -y git cmake libboost-all-dev

git clone https://github.com/liusida/voxcraft-sim.git
cd voxcraft-sim
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release -DCUDA_DEBUG=OFF ..
make -j 10
```

Now you will have two executables: `voxcraft-sim` and `vx3_node_worker`. 
<br>

Copy and paste them to a directory where you want to run the simulations.
<br>

Finally, try one of the demos:
```bash
./voxcraft-sim -i ../demos/basic/ > demo_basic.history
```

This will produce a `demo_basic.history` file that can be visualized in voxcraft-viz.
<br><br>


<a name="evo"></a>
# **evo**

With voxcraft-sim you can evaluate designs on GPUs with blazing fast speed, but which designs should you sim?
<br>

**voxcraft-evo** contains a simple but powerful evolutionary design package that 
"genetically" encodes each robot design as a 
[generative network](https://dl.acm.org/doi/pdf/10.1145/2463372.2463404),
and through a process of 
[trial and error](https://link.springer.com/chapter/10.1007/978-1-4419-7747-2_8), 
incrementally improves their performance according to a desired behavioral goal: locomotion, grasping, jumping, etc.
<br>

The software is modular: you can replace the encoding and optimization algorithm with whatever you'd like.
<br>

If you can beat the default settings,
that's impressive!
Please [publish](/research) your method,
contact 
[Sam](/team#sam), 
and we will link your code and paper here.
<br>


### **installing evo**

#### python



### **evolving robots**


#### for locomotion



