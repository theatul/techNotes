---
title: "Part 2 - How to Run VMware View Planner"
date: 2020-07-19T00:55:23+05:30
draft: false

tags: [
    "viewplanner",
    "View Planner",
    "VMware View Planner",
    "Horizon capacity planning",
    "VDI capacity planning",
    "VDI Benchmark",
]
---

Here are the steps to prepare desktop and client virtual machines for test.
<!--more-->

## Prepare Windows desktop Virtual Machines for Test.

1. Create a windows VM.

2. Shut down the VM and set following value in .vmx file of the VM. This enables access to host timer that is more accurate then VM timer.

```
        monitor_control.pseudo_perfctr = “1”
```

3. Install all required applications for test, for standard profile you need to install:

```
        Microsoft Office 
        Google chrome
        Adobe reader
        windows media player.

```

4. Configure any license required for OS and applications.

5. Install Horizon agent for in the VM.

6. Install View Planner Agent, Provide harness IP during installation.

7. Enable auto login in the VM.

8. Shut down the VM and create a snapshot.

9. Create horizon desktop pool, the VM count should be same as the number of VM's to test Although it is better to start with one VM and increase VM count when everything works well.


## Prepare Windows client Virtual Machines for Test.

10. Create a windows VM.

11. Shut down the VM and set following value in .vmx file of the VM. This enables access to host timer that is more accurate then VM timer.

```
        monitor_control.pseudo_perfctr = “1”
```

12. Install Horizon client.

13. Configure any license required.

14. Install View Planner Agent, Provide harness IP during installation.

15. Enable auto login in the VM.

16. Shut down the VM and create a snapshot.

17. Now you can create clones using Horizon or Virtual Machines tab in View planner UI.