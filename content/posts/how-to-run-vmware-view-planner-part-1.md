---
title: "Part 1 - How to Run VMware View Planner"
date: 2020-07-13T20:49:29+05:30
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
Here are the steps to prepare View Planner Harness...
<!--more-->

## Download binaries.
1. Download View Planner Harness OVA from [official page](https://www.vmware.com/products/view-planner.html).

## Deploy view Planner Harness.
2. Deploy View Planner harness OVA using vSphere client.
3. Select host to install and accept license.


    ![Summary](/img/review.png)


4. When asked, Provide a static IP.
5. Provide default password during OVA installation, this password is used for root user of the appliance.

    ![Password](/img/password.png)

6. Power on the VM once the OVA is installed, It may take few minutes to boot.
7. Once boot is complete, login to UI using [http://<Harness_IP>/vp-ui](http://<Harness_IP>/vp-ui).
8. Use default credentials:
```
        Default user name - vmware
        Default Password  - viewplanner
```

## Configure View Planner Harness.
9. Navigate to SERVERS tab and add your vCenter as Infra server.

    ![Infra](/img/Infra.png)

10. In SERVERS TAB, add your Active directory as Identity server. AD Server is required only for remote mode.

    ![AD](/img/AD.png)

11. Add your Horizon connection server as VDI server. This is required for only remote mode tests.

    ![VDI](/img/VDI.png)

12. You can use test button to validate configurations of added servers.

13. Optionally you can have a look at WORKLOAD AND WORK-PROFILE tab and create your own work-profiles.

With above steps completed, Your View Planner Harness is configured and ready to use now.



