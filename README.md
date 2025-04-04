# Course Main Repository 

Welcome to Nanoscale Material Modelling! Access each week’s materials using the links below (the will be made available as the course progresses):

- [Week 1 Repository](https://github.com/giuntoli-group/nmm-week1)
- [Week 2 Repository](https://github.com/giuntoli-group/nmm-week2)
- [Week 3 Repository](https://github.com/giuntoli-group/nmm-week3)
- [Week 4 Repository](https://github.com/giuntoli-group/nmm-week4)
- [Week 5 Repository](https://github.com/giuntoli-group/nmm-week5)
- [Week 6 Repository](https://github.com/giuntoli-group/nmm-week6)
- [Week 7 Repository](https://github.com/giuntoli-group/nmm-week7)
- [Week 8 Repository](https://github.com/giuntoli-group/nmm-week8)


## Kickoff assignment

---


### Introduction to command line

The command line, or terminal, is a text-based interface to the system. You can navigate through files, run programs, and even connect to other computers. For many computational projects, especially those involving computer clusters, the command line is an essential tool.

Here are some fundamental commands you will use:

- `pwd` to print the directory you're currently in
- `ls` to list the files and directories in the current directory
- `cd` to change the directory
- `mkdir` to create a new directory
- `rm` to remove files or directories
- `cp` to copy files or directories

> **DANGER**: Never type `rm -rf *` in your home directory. This will delete everything in your system, and it's not reversible.


### Remote connection to Habrok

To connect to computer clusters, like Habrok, you'll use SSH (Secure Shell). SSH allows you to securely connect to another computer over the internet. Click [here](https://wiki.hpc.rug.nl/habrok/connecting_to_the_system/connecting) for more information on how to connect to Habrok.

For Mac and Linux users, open the terminal and type:

```bash!
ssh s123456@interactive1.hb.hpc.rug.nl
```

Replace `s123456` with your student number.

There are four possible ways of connecting to Habrok. If the above node is unresponsive, you can try the following:

```bash
ssh s123456@login1.hb.hpc.rug.nl
ssh s123456@login2.hb.hpc.rug.nl
ssh s123456@interactive2.hb.hpc.rug.nl
```


For Windows users, you'll need to download and install Putty, a free SSH client. Once installed, open Putty, enter the hostname (e.g., `s123456@interactive1.hb.hpc.rug.nl`), and click 'Open' to connect. More information for Windows users [here](https://wiki.hpc.rug.nl/habrok/connecting_to_the_system/windows)


#### Task 1: Complete [this tutorial](https://linuxsurvival.com/linux-tutorial-introduction/) on the command line

Optional task: Watch [this video](https://www.youtube.com/watch?v=s3ii48qYBxA) 

#### Task 2: Connect to Habrok and access the shared workspace

This is where you will store all your data. Keep in mind that you have a quota of 250GB. 
```bash
cd  \scratch\$USER\
```
You can copy scripts and data files from the shared data space to your workspace. Access the shared workspace from here
```bash
cd  \scratch\hb-nanoscale-ro
```

### Setting up environments and using software modules


We will show how to use existing software on Habrok when needed, and also how to install our own, i.e. Beadspring Analytics. We will use conda environments to install Python packages. This is normally not suggested on HPC systems because of performance issues, but we don't care because it's the easiest way to do it and our post-processing scripts are generally not be memory or CPU heavy. Once you login, you are automatically in the `/home/$USER` directory. This directory is backed up and has a storage quota of 50GB. It is meant to store your installed software and scripts, not the data. For data storage we will use `/scratch/$USER`. Let's first install an existing Anaconda distirbution from the software stack. Type

```bash!
module load Anaconda3/2023.09-0
```
Now you can use the `conda` executable. (Note that some systems come with an existing conda executable without needing to load Anaconda. Please check if this is true for Habrok). Now we are going to install [Beadspring Analytics](https://github.com/utkugurel/beadspring). Follow the link to the software repository. You will find more detailed installation instructions there. The package is not published on PyPI yet, so you have to install it within your environment from the source code. If any of the steps is not clear, please contact Utku. This is the only software you need to install from the source. Now, using the same command, load `LAMMPS` and test if it works


```bash=
module load LAMMPS/23Jun2022-foss-2021b-kokkos
lmp
```
in the given order. `lmp` is the name of the executable that launches the LAMMPS interface. You should see something like the following after typing this command.

```bash
LAMMPS (23 Jun 2022 - Update 1)
OMP_NUM_THREADS environment is not set. Defaulting to 1 thread. (src/comm.cpp:98)
using 1 OpenMP thread(s) per MPI task
```

Once you verify that you have access to `lmp` command, hit `ctrl+c` to exit. Now, we are ready to run our first simulation.
