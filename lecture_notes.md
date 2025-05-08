# **Nanoscale Material Modelling Lecture Notes**

[![hackmd-github-sync-badge](https://hackmd.io/bIxoXj7mSwS96s1I947ciA/badge)](https://hackmd.io/bIxoXj7mSwS96s1I947ciA)

We'll use this section to post real-time updates, links, and shared code. Keep an eye on this space during sessions!
### Tips for Posting

Just copy the template and modify it. Formatting doesn’t have to be perfect — this is a casual shared space.

## Announcements (in reverse chronological order)

:::success
Please download the reading material [here](https://filesender.surf.nl/?s=download&token=14e43dec-820b-402a-885b-bcfe2df180bf) until May 28th. (utku, 07/05/2025)
:::

## Week 4

- Run `git clone git@github.com:giuntoli-group/nmm-week4.git`

-

## Week 3


## Week 2

- Good morning! Can you access `/scratch/hb-nanoscale/nmm-week2`? If you can't please try to clone the repository to your home or scratch directory using `git clone git@github.com:giuntoli-group/nmm-week2.git` (utku)

- One thing you can try to get XCrySDen to work on mac machines, you try installing XQuartz software. Instructions can be seen here: https://docs.cse.lehigh.edu/xforwarding/xforwarding-mac/ 

- Please change the topology file name from `final.topo` to `final.data` in `nmm-week1/scripts/in.3dlj`. If you haven't run the simulation yet, this is updated on the github page (utku, 22/04/2025)


## Week 1
- Tip: add the following line to `~/.bashrc`
```bash
alias sq='squeue -u $USER'
```
to create the shortcut `sq` to check the status of your jobs. Then type `source ~/.bashrc`.


- Follow these steps to set up a passwordless login to Habrok https://wiki.hpc.rug.nl/habrok/connecting_to_the_system/ssh_key_login

- Use the following to donwload files from Habrok. Change `.` to `/your/path` to change the target location. Run it from the local machine
```bash
scp -r s12345@interactive1.hb.hpc.rug.nl:/scratch/hb-nanoscale/assignment_1/no_reacted.data .

scp -r <username>@interactive1.hb.hpc.rug.nl:<path_to_file> <path_to_destination>

pwd = get file path
. = current directory
```

- XCrySDen throws an error for some machines. Please use the browser version if that's the case https://tools.materialscloud.org/seekpath/

```bash
ssh -X s12345@interactive1.hb.hpc.rug.nl
```

---


## **Feedback Wall**

We'll occasionally ask you to leave feedback here — about the content, pace, vibe, or anything you'd like to share. You can add your thoughts anonymously or include your name if you like!

*What did you enjoy about the first session?*
*Is there anything that could be improved?*
*Anything else?*

- 
-
-
---

## Q&A
Type in our questions about anything. Feel free to respond to each other as well!

### Q: *What’s the difference between `scp` and `rsync`?*  
**A:** Both are used to copy files between systems over SSH, but they work differently:

- `scp` is simpler and just copies files from source to destination.
- `rsync` is more efficient for repeated transfers — it only copies the differences (deltas) between source and destination, supports resuming transfers, and has more options for syncing directories.

### Q: In week 1 assignment 4, you have asked to change the number of processors. It is unclear since there has to be distinction between task, node, cpu, gpu, and cores. In the documentation, we can specify the number of tasks (-n) and cores per task (-c), for example. I understand that we will get n*c cores (processors), but the provided script sets n=12 (and c=1 by default). Is my understanding correct? I would then set n=2 and n=64 as the assignment asks? If so, what is the difference between, for example, n=12 c=1 and n=2 c=6? 
**A:** 
The names can indeed be confusing, especially since Slurm uses a slightly different terminology compared to the colloquial one. In Habrok, each node has 128 processors (set by the ntasks option), and each processor (core) can be split into further logical partitions called threads (set by the cpus-per-task option). It is really hard to find the optimal choice of the number of threads/core (multithreading) for lammps simulations. This can vary wildly depending on the simulating system and the HPC architecture. So it is best we stick to 1 thread/core and use multiprocessing to increase performance instead. In short, keep the default c=1 and change ntasks.

### Q: <type here>
**A:** <type here>

### Q: <type here>
**A:** <type here>