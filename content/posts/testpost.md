---
title: "Part 1: Set-up a blog on your home raspberry-pi server."
date: 2020-05-10T22:14:17+05:30
draft: false
tags: [
    "raspberry-pi",
    "home server",
    "web hosting",
    "NGINX",
    "Dynamic IP",
    "DHCP IP",
    "no-ip",
]
---

This is a two part artical, read [part-2 here](/posts/hugo-static-site-on-pi/)


I bought a raspberry-pi few weeks back and have been experimenting with it since. Pi is a nifty little computer, it can make you wonder with different roles and tricks it can perform for you. 

Being a performance engineer I started to test its limits to see how many roles a pi 4B+ can perform simultaneously in a home 
environment. As of today one little device in my home is:

1. Providing shared storage for all home devices using samba.

2. Acting as a media server using KODI.

3. Blocking adds in my home network using Pi-hole.

4. Acts as an always on desktop for long running scripts.

And it can do more as evident by the low CPU and memory usage of the device. what more can i do on a home server you ask, how about hosting this blog?

Let's get started:

## Setup HTTP server.

I decided to use NGINX as it's light and fast in compare to apache for serving static sites. And that is what we need for a simple blog. Process to setup is fairly simple:

1.  Install NGINX using command:
```
sudo apt install nginx
```
2. Start the nginx service:
```
sudo /etc/init.d/nginx start
```
3. Test the server by visiting [localhost](http://localhost) or the ip of pi.

And Voila, our http server is ready.

## Do you need static IP?

No, although static IP makes the performance and setup process simpler, it's not a must. I used a *dynamic domain* service called no-ip.com, It regularly updates public IP of your home network to its data base and points all the request to most recent IP. This should be enough for a small blog like this one. Here is the process to setup:

1. Visit no-ip.com and create a free account.

2. Choose a new domain name when asked, i selected c

3. Download Dynamic DNS Update Client from [www.noip.com/download?page=linux](https://www.noip.com/download?page=linux)

4. Extract contents of the client file and use following commands to build and install the client:
```
> make
> make install
```

5. you might encounter few dependencies error while compiling above, just install the dependencies first and retry the command.

6. Last step is to setup Port forwarding in your router, this makes sure that HTTP requests coming to your router are forwarded to your pi. This can be done by accessing your router configuration and accessing the Port Forwarding section, this is how configuration is my router looks like:


![port forwarding](/img/port_forwarding.png)


7. With this you should be able to access page served by your pi's NGINX server from the domain name created using no-ip.com. You can also choose your own domain by moving to a paid plan.

Now our domain and http server are ready, so all we need is a real blog instead of default NGNIX page. In part two of this blog i will discuss steps to setup a static blog site using a static site generator.

This is a two part artical, read [part-2 here](/posts/hugo-static-site-on-pi/)
