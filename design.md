## design

The design software allows you to rapidly test designs and discard bad ones before spending time and supplies to build them.
However, if you already have a design in mind and the kit in hand, 
you skip the simulation and go ahead and [build](/build) it now!
<br>

<!-- <a class="github-button" href="https://github.com/voxcraft" data-size="large" data-show-count="true" aria-label="Follow @voxcraft on GitHub">Follow @voxcraft</a>
<br><br>
The software has three parts:
<br> -->

### **Start here:**

If recommend starting with the [Science Buddies](https://www.sciencebuddies.org/science-fair-projects/project-ideas/robotics_p016/robotics/squishy-robot-simulator#procedure) tutorial for CPU VoxCAD.
The first step links to a Windows installation of VoxCAD.
If you do not have Windows, you can instead download a GUI for [Mac](https://voxcraft.github.io/design#mac) and [Linux](https://voxcraft.github.io/design#linux), and then continue with step 2 of the procedure.

### **Step-by-step tutorials:**

<iframe width="100%" height="400" src="https://www.youtube.com/embed/JAm1vqny8Z0" frameborder="0" allowfullscreen></iframe>
<br>

[Python](https://github.com/caitlingrasso/Voxcraft-python) <br>

[Julia](https://www.youtube.com/watch?v=LRWhnXDBs6M&list=PL3hGTlJn4wpMvm_XV3T6Pk9jeyRjvVjrz) <br>


### **A new GPU simulator:**

Our new GPU software, which was forked from CPU VoxCAD, has two parts:
<br>

<a href="#viz"><i class="fas fa-desktop icon" title="viz"></i></a>
&nbsp;&nbsp;&nbsp;&nbsp; 
<a href="#viz">**viz**</a>: _draw and **vi**suali**z**e voxelbots in action._

&nbsp;
<a href="#sim"><i class="fas fa-running icon" title="sim"></i></a>
&nbsp;&nbsp;&nbsp;&nbsp; 
<a href="#sim">**sim**</a>: _gpu-accelerated **sim**ulation._

<!-- <a href="#ray"><i class="fas fa-pastafarianism icon" title="ray"></i></a>
&nbsp;&nbsp;&nbsp;
<a href="#ray">**ray**</a>: _automatic design powered by [**Ray.io**](https://ray.io/)._
<br><br> -->


<a name="viz"></a>
# **viz**
You can manually design voxelbots by drawing them in our graphical user interface 
[voxcraft-viz](https://github.com/voxcraft/voxcraft-viz), 
which was originally forked from [voxcad](https://github.com/jonhiller/VoxCAD).
<br>

<a class="github-button" href="https://github.com/voxcraft/voxcraft-viz" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star voxcraft/voxcraft-viz on GitHub">Star</a>
<a class="github-button" href="https://github.com/voxcraft/voxcraft-viz/fork" data-icon="octicon-repo-forked" data-size="large" data-show-count="true" aria-label="Fork voxcraft/voxcraft-viz on GitHub">Fork</a>
<a class="github-button" href="https://github.com/voxcraft/voxcraft-viz/archive/master.zip" data-icon="octicon-download" data-size="large" aria-label="Download voxcraft/voxcraft-viz on GitHub">Download</a>
<br>


<a name="windows"></a>
### **install on Windows**
On Win10, you can download the software 
[here](https://github.com/voxcraft/voxcraft-viz/raw/master/bin/voxcraft-viz-win10-x64.7z).
<br><br>


<a name="linux"></a>
### **install on linux**

On linux you can install with snap
```bash
sudo snap install voxcraft-viz
```

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-white.svg)](https://snapcraft.io/voxcraft-viz)
<br><br>


<a name="mac"></a>
### **install on macOS**

On macOS follow these steps to install viz (you'll need [Homebrew](https://brew.sh)):
```bash
brew install cmake
brew install boost
brew install qt5
brew install glfw3
brew install xquartz
brew install freeglut
brew install mesa
```
This will take a while...
```bash
git clone https://github.com/voxcraft/voxcraft-viz.git

cd voxcraft-viz/
mkdir build
cd build/
  
cmake -DQt5_DIR=$(brew --prefix qt5)/lib/cmake/Qt5 -DCMAKE_BUILD_TYPE=Release ..
  
make -j 10
```
Copy the executable ```voxcraft-viz``` somewhere in your $PATH, for example /usr/local/bin.

```
cp voxcraft-viz /usr/local/bin
```
Done!

Type ```voxcraft-viz``` into your terminal to launch the viz.
<!-- Check for [mac updates](https://github.com/voxcraft/voxcraft-viz/blob/master/InstallOnMac.md).-->
<br><br>


## **drawing a robot in viz**

You can draw a custom robot in voxcraft-viz using your mouse and then press play to watch its behavior.
<iframe width="100%" height="400" src="https://www.youtube.com/embed/jvxQjlrLgQo" frameborder="0" allowfullscreen></iframe>
<br><br>


## **playing a history file in viz**

voxcraft-viz can also be used to replay the behavior of robots that have already been simulated elsewhere: 
their **history**.

You can download one of these prerecorded history files 

[**`m190.history`**](https://github.com/voxcraft/voxcraft-viz/raw/master/demos/m190.history)
&nbsp;&nbsp;
[**`m805.history`**](https://github.com/voxcraft/voxcraft-viz/raw/master/demos/m805.history)

and replay it in voxcraft-viz:

<iframe width="100%" height="400" src="https://www.youtube.com/embed/ytQ7dj3yE8M" frameborder="0" allowfullscreen></iframe>
<br>


<a name="sim"></a> 
# **sim**
[voxcraft-sim](https://github.com/voxcraft/voxcraft-sim) simulates voxels in parallel on a gpu. 
The simulations are headless (without graphics)
but a _history file_ can be recorded that traces the behavior of each voxel within a simulation. 
This history can then be replayed in either voxcraft-viz or Unity.
<br>

<a class="github-button" href="https://github.com/voxcraft/voxcraft-sim" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star voxcraft/voxcraft-sim on GitHub">Star</a>
<a class="github-button" href="https://github.com/voxcraft/voxcraft-sim/fork" data-icon="octicon-repo-forked" data-size="large" data-show-count="true" aria-label="Fork voxcraft/voxcraft-sim on GitHub">Fork</a>
<a class="github-button" href="https://github.com/voxcraft/voxcraft-sim/archive/master.zip" data-icon="octicon-download" data-size="large" aria-label="Download voxcraft/voxcraft-sim on GitHub">Download</a>
<br>

<a name="colab"></a>
## **run sim in Google Colab** 
Create a new notebook and go to Menu->Runtime->Change runtime type, select GPU.
<br>

Then, copy and run the script from this (readonly) example 
[notebook](https://colab.research.google.com/drive/1yiqw7Uq3W3CgYCinXq4t808M2l7uuLv1).
<br>

It will produce `a.history` which can be played in voxcraft-viz to visualize the simulated behavior.
<br><br>


<a name="unity"></a>
## **render a history file in Unity** 
History files can also be rendered in the Unity game engine.
<iframe width="100%" height="400" src="https://www.youtube.com/embed/z0f-I2rZGDU" frameborder="0" allowfullscreen></iframe>

You can download this Unity demo project [here](https://github.com/voxcraft/voxcraft.github.io/blob/master/demos/UnityHistoryFileDemo.zip).
<br><br>


<a name="install"></a>
## **install sim from scratch**
If you have access to Nvidia graphic cards you can compile voxcraft-sim from scratch.
The most difficult part is installing
[CUDA 10.1](https://developer.nvidia.com/cuda-10.1-download-archive-base).
<br>

Once you have CUDA **10.1**, the rest is easy:
```bash
sudo apt-get update
sudo apt-get install -y git cmake libboost-all-dev

git clone https://github.com/voxcraft/voxcraft-sim.git
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

<a name="cite"></a>
## **cite voxcraft-sim**
If you use this code for academic purposes, please cite:
```
@MISC{liu_voxcraft_2020,
	title = {Voxcraft-sim, a GPU-accelerated voxel-based physics engine},
	howpublished = {\url{https://github.com/voxcraft/voxcraft-sim}},
	author = {Sida Liu and David Matthews and Sam Kriegman and Josh Bongard},
	year = {2020},
	doi = {10.5281/zenodo.3835152},
}
```
[![DOI](https://zenodo.org/badge/265434971.svg)](https://zenodo.org/badge/latestdoi/265434971)
<br>

Thanks!
<br><br>

<!-- 
<a name="ray"></a>
# **ray**
With voxcraft-sim you can evaluate designs on GPUs with blazing fast speed, but which designs should you sim?
<br>
<a class="github-button" href="https://github.com/voxcraft/voxcraft-ray" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star voxcraft/voxcraft-ray on GitHub">Star</a>
<a class="github-button" href="https://github.com/voxcraft/voxcraft-ray/fork" data-icon="octicon-repo-forked" data-size="large" data-show-count="true" aria-label="Fork voxcraft/voxcraft-ray on GitHub">Fork</a>
<a class="github-button" href="https://github.com/voxcraft/voxcraft-ray/archive/master.zip" data-icon="octicon-download" data-size="large" aria-label="Download voxcraft/voxcraft-ray on GitHub">Download</a>
<br>
**voxcraft-ray** connects voxcraft-sim to [Ray](https://ray.io/), which provides dozens of machine learning algorithms and a nice interface for distributed computing. 
<br>
Starting with randomly generated designs, machine learning methods can incrementally improve their performance according to a desired behavioral goal: locomotion, grasping, jumping, etc.
### **install with Docker**
....
### **install with Singularity**
....
### demo
...
-->
