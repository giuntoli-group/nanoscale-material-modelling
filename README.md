# Course Main Repository 

Welcome to Nanoscale Material Modelling! Access each week’s materials using the links below:

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


### Part 1: Introduction to command line

The command line, or terminal, is a text-based interface to the system. You can navigate through files, run programs, and even connect to other computers. For many computational projects, especially those involving computer clusters, the command line is an essential tool.

Here are some fundamental commands you will use:

- `pwd` to print the directory you're currently in
- `ls` to list the files and directories in the current directory
- `cd` to change the directory
- `mkdir` to create a new directory
- `rm` to remove files or directories
- `cp` to copy files or directories

> **DANGER**: Never type `rm -rf *` in your home directory. This will delete everything in your system, and it's not reversible.


#### Remote connection to Habrok

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


### Task 1: Complete [this tutorial](https://linuxsurvival.com/linux-tutorial-introduction/) on the command line

Optional task: Watch [this video](https://www.youtube.com/watch?v=s3ii48qYBxA) 

### Task 2: Connect to Habrok and access the shared workspace

This is where you will store all your data. Keep in mind that you have a quota of 250GB. 
```bash
cd  \scratch\$USER\
```
You can copy scripts and data files from the shared data space to your workspace. Access the shared workspace from here
```bash
cd  \scratch\hb-nanoscale-ro
```

## Part 2: Running your first simulation


After connecting to Habrok, navigate to a suitable directory to run your simulation. We will run this simple simulation on the interactive node, but please note that the purpose of the interactive node is to test your simulations. Never run an actual simulation on the login/interactive nodes once you start working on your project.

First, you can just navigate to the scratch partition on Habrok by typing the following.

```bash!
cd /scratch/$USER
```
### Task 3: Create a new directory named ```tutorial``` in this partition.

> **Hint**: Check the commands given in Part 1.


Before running our simulations, we need to load our simulation software LAMMPS. This is already installed on Habrok. Type the following: 

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

### Task 4: Navigate to ```tutorial``` and copy the scripts and the data files from your computer to here.

Assuming that you have a folder named `tutorial` on your computer, you can copy it to Habrok by the following command.
```bash
scp -r tutorial/ s123456@login1.hb.hpc.rug.nl:/scratch/s123456
```
