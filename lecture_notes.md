# **Nanoscale Material Modelling Lecture Notes**

[![hackmd-github-sync-badge](https://hackmd.io/bIxoXj7mSwS96s1I947ciA/badge)](https://hackmd.io/bIxoXj7mSwS96s1I947ciA)

We'll use this section to post real-time updates, links, and shared code. Keep an eye on this space during sessions!
### Tips for Posting

Just copy the template and modify it. Formatting doesn’t have to be perfect — this is a casual shared space.

## Announcements (in reverse chronological order)

-
-
-

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

### Q: <type here> 
**A:** <type here>


### Q: <type here>
**A:** <type here>

### Q: <type here>
**A:** <type here>