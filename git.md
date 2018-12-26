---
layout: page
title: Git Notes (61B Fall 2016)
permalink: /notes/git.html
---

CONCEPTUAL OVERVIEW:

**What is Git?** 
It is a version control system; in other words, it’s a way for a programmer to keep track of all their old versions of code. An analogy is that Git keeps snapshots of your code throughout time. Why is this useful? What if you were working on a project and realized all the changes made during a late-night epiphany was actually completely incorrect? In order to get back the old version of your code (or snapshot), all you’d need to do is to tell Git to revert your code back to the state it was in during that snapshot. Directories in which Git is initialized are called repositories.

**How is Git relevant to the course?** Another great feature of Git is its ability to allow multiple people to work on one project or piece of code at once. There can be one central repository containing all the files, and users can pull from that repository as needed. The benefit here is that some person Bob can pull in files to his own computer, and make changes there. However, the central repository is still left unchanged, and other people can pull in fresh copies of the files from the central repository (of course, they can later push in their changes to the central repository, but that’s another story). This is useful. Here’s a simplified version of our own git scenario: the 61B course staff has, in the taa account, skeletons for labs/hw/projects. We want a way that all the students can easily pull these skeletons into their computers, make changes, and send their solutions for labs/hw/projects back in. Git works perfectly for this!

**What’s the local/remote?**

Let’s think back to the taa account that contains all the skeleton files; the taa account belongs to the cs6b instructional account group. As a student, you also have a cs61b account (for sake of example, let’s say 61b-abc from now on). The taa account maintains a repository for all students; in this case taa maintains a repository for abc. There are two ways for you to access the skeleton files available in the abc repository. 1. Through your instructional account; 2. Through your home computer.

1.  Through instructional account: This is where the word “remote” gets a little confusing. It really just refers to some repository that is not within your computer; so, it’s a very relative term. In this situation, your instructional account will clone your central repository (abc repo) from the taa account. This is one way you can access your skeleton files. How to use the indstructional accounts? Well, that’s the account you log in with on the Soda computers. You can also remotely log into your instructional account from another computer. That’s the ssh step, which we’ll get into further. If you prefer not making the trek up the hill to Soda or if editing code via your terminal is not your jam, then you’ll probably want to access the skeleton files in the comfort of your home computer…
2.  Through home computer: This is where you clone your central repository (abc repo) from the taa account. The only difference between (2) and (1) is that in (2) you are doing this on your home computer. This is what the Git Guide from Lab 1 tells you how to do.

Diagram:

![](/ching-photos/gitDiagram.jpg)

A brief interlude about ssh and scp:

ssh (**S**ecure **SH**ell): A secure way to connect to a remote computer from your own local computer. Here, the command will be “ssh <address>”, or “ssh cs61b-abc@ashby.cs.berkeley.edu”. Besides ashby, other servers you may use to access the instructional accounts are cory eecs, derby, hive, etc.

***Beware that cory eecs only has Java version 7, NOT 8. Don’t use it for java stuff.

scp (**S**ecure **C**opy **P**rotocol): Based off the protocol of ssh, scp is a secure way to copy file between a remote computer and your own local computer. Here, the command is “scp <source> <destination>”. 

Example: I want to copy over “multigrainbread.java” from my instructional account to a directory in my local computer called “breads”: “scp cs61b-abc@ashby.cs.berkeley.edu:~/multigrainbread.java ~/breads”

**Setting Up Your Local Repo**

So how to actually create a git repository on your local machine and link it up to your central repository? You’d follow the steps of the git guide from lab. If you’re still confused about what all the steps mean after following the guide, here’s a breakdown of what’s going on and why certain commands are run:
