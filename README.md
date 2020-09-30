# measim2.0
*Simulation of two-dimensional cultured neuronal network with an astrocytic component*

This code implements a neuronal, electrophysiological model by [Volman et al](http://dx.doi.org/10.1088/1478-3975/4/2/003), which consists of [Morris--Lecar](https://dx.doi.org/10.1016%2FS0006-3495(81)84782-0) neurons and extended [Tsodyks--Markram](http://www.pnas.org/content/94/2/719) synapses as TUMA tripartite synapses, on a 2D network to simulate a system of dissociated cultured neurons with astrocytes on a multi-electrode array. Please see the manuscript [Kumar et al](https://doi.org/10.1093/texcom/tgaa053) for details of the model and the corresonding experiments. Earlier studies employing the code include: [Huang et al](https://link.springer.com/article/10.1007/s10827-016-0634-4) 
[arXiv:1402.1959](https://arxiv.org/abs/1402.1959)

## Prerequite libraries (Debian packages, recommanded verion)
Building from source package: HDF5 (libhdf5-dev, >=1.8.16)  
With GUI: glut/freeglut3 (freeglut3-dev, >=2.8.1)  

Building from git checkout: autoconf (>=2.69), autoconf-archive (20160916), automake (>=1.15), libtool (>=2.4.6), pkgconf (>=0.9.12)

## Build from git
The build system of measim is based on GNU autotools. First check out the source tree and submodules from github:

    $ git clone https://github.com/salvira/measim2.0
    $ cd measim2.0
    $ git submodule init
    $ git submodule update

then build from source with

    $ ./bootstrap
    $ mkdir build
    $ cd build
    $ ../configure
    $ make

## Build from release source package
Download release source package `measim-<version>.tar.xz` from git and build:

    $ tar xf measim-<version>.tar.xz
    $ cd measim-<version>
    $ mkdir build
    $ cd build
    $ ../configure
    $ make

## Executables
After the build process completes successfully, there will be following executables for the simulation:
* `rvol`: command-line simulation engine use `./rvol --help` to see options
* `vdmp`: dumps mean values of system states as it runs
* `vvol`: GUI programs for visualized simulation run
* `vvlt`: Threaded version of `vvol` to seperate GUI and running codes (unstable, changing parameter while running may lead to crash of the program)
