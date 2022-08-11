---
title: "Nginx"
date: 2021-06-14T20:22:00+02:00
draft: false
toc: false
images:
tags:
  - nginx
  - web
---

## The Internet:

Whenever you browse a website on the internet, your computer is making a request to a server that is hosting the website. These web servers play a curcial role in the running of the internet. Without them there wouldn't really be much of an internet.

## What does a Web Server do?:

A Web Server is basically like a normal computer, that recieves an input from a user and provides an output (the website we see). Servers consist of both hardware and software, and together work hand in hand to run the website being hosted. Our computers connect to webservers through either the HTTP or HTTPS protocol (Hyper Text Transfer Protocol / Secure).
The hardware on a webserver could be anything from the normal personal computer you have in your home, to the massive supercomputers found in data centers like at Google. The software on the other hand is what actually handles all the HTTP/HTTPS requests and runs the website. Without the Web Server software, you just have a big machine sitting and doing nothing.
Below is a basic diagram of how a Web Server works:
<img src="https://i.imgur.com/j6NIT1q.png" class="w-full h-auto" />

<figcaption>Also known as the Client-Server model</figcaption>

As you can see, The clients make a request to the server through the internet, and the server then sends back the response which is the website we see. Pretty simple right?

## How does the Software work?:

As mentioned above, the software is what basically runs the whole website. It operates over various communication protocols as mentioned, in order for computers on the internet to connect to it. There are various types of Web Servers you can use, but two of the most popular ones are Apache and NGIX. As a matter of fact this website is currently using NGINX.

## What can NGINX do?:

NGINX is an OpenSource Web Server, that can also be used as a reverse proxy, HTTP cache, and a load balancer. Most high-level companies such as Google, DuckDuckGo, Microsft and Facebook use NGNIX because of its reliability.

## How can I set up NGINX for my website?:

First off some prerequisites:

- A server/computer running linux (Debian based such as Ubuntu Server)
- An active internet connection
- Basic knowledge of the Linux terminal
  <br />

This tutorial is going to contain instructions for all **Debian** based systems that use the `apt` package manager

#### Step 1:

We need to first update the system and then install nginx with `apt`.

```bash
sudo apt update
sudo apt install nginx
```

The `apt` package manager will now install the nginx server.

#### Step 2:

Next we will need to configure our firewall to allow clients to connect to the server.

```bash
sudo ufw app list
```

You should see the following output:

```bash
Output
Available applications:
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
```

As shown above, there are three different profiles for NGINX.

- Nginx Full - Opens both port 80 (HTTP) and port 443 (HTTPS)
- Nginx HTTP - Opens port 80 (HTTP)
- Nginx HTTPS - Opens port 443 (HTTPS)

It is best practice to rather use the Nginx HTTPS profile, however assuming you have not set up SSL yet, that won't be possible. So for now we will allow all traffic through port 80. But don't worry, this can be changed later.

```bash
sudo ufw allow 'Nginx HTTP'
```

Then verify that the profile has been selected by typing;

```bash
sudo ufw status
```

Output:

```bash
Output
Status: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere
Nginx HTTP                 ALLOW       Anywhere
OpenSSH (v6)               ALLOW       Anywhere (v6)
Nginx HTTP (v6)            ALLOW       Anywhere (v6)
```

#### Step 3:

Now we need to enable our webserver to start up automatically whenever we turn on the server. We can make use of the `systemctl` command.

First start the service:

```bash
systemctl start nginx
```

Then enable it on boot:

```bash
systemctl enable nginx
```

You should now be able to see the current status of Nginx by typing in:

```bash
systemctl status nginx
```

Output:

```bash
Output
● nginx.service - A high performance web server and a reverse proxy server
   Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
   Active: active (running) since Fri 2018-04-20 16:08:19 UTC; 3 days ago
     Docs: man:nginx(8)
 Main PID: 2369 (nginx)
    Tasks: 2 (limit: 1153)
   CGroup: /system.slice/nginx.service
           ├─2369 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;
           └─2380 nginx: worker process

```

And thats it. Your Web Server is now up and running. You should be able to access it by typing in:

```bash
http://{server_ip}
```

Eg:

```bash
http://192.168.1.23
```

And you should then see the default Nginx landing page. This page means that everything is running correctly.

<br />
<img src="https://i.imgur.com/4595Umo.png" class="w-full h-auto">
