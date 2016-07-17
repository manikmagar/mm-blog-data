title=Set up a VPS for hosting JBake blog
status=Draft
date=2016-06-21
tag=VPS Setup
categories=JBake
~~~~~~

In [previous blog](http://manik.magar.me/blog/2016/06/Moving-From-Wordpress-to-baking-with-JBake-on-VPS.html), I mentioned about moving to JBake powered static blogging system. I can now write my blog posts on Github and then trigger remote deployment of my blog to my VPS without logging onto box. In this post, I will explain how I wired everything on my [Digital Ocean (Referral*)](https://m.do.co/c/fff9bf2cbe08) VPS. [*This is a referral link and you can get 2 months free VPS when followed].

I am using basic $5/month Ubuntu droplet on [Digital Ocean](https://m.do.co/c/fff9bf2cbe08) that has 512MB RAM, 20GB SSD. 

****Step 1: ****
Register/Login on [Digital Ocean](https://m.do.co/c/fff9bf2cbe08) and Spin off an Ubuntu based droplet. You can follow instruction on DO Community [here](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04) to do initial setup of droplet. If you already have a VPS, you can skip this step.

****Step 2: **** Now we will need a web server for our blog. I am using [Nginx](https://nginx.org/en/) but if Nginx is not setup properly it might give a bad performance. Thanks to https://easyengine.io/ guys who really made my nginx setup easy. Installation and Site creation with EE is as easy as running below two commands - 

```
wget -q0 ee rt.cx/ee && sudo bash ee
sudo ee site create example.com --html
```

This will create a site HTML only site with all required nginx configuration and mount it on /var/www/example.com/.

****Step 3: **** Install [JBake](http://jbake.org/download.html). Easiest way to install and maintain JBake is via [SDKMan](http://sdkman.io/). Install SDKMan with a simple command `curl -s "https://get.sdkman.io" | bash` and then run `sdk install jbake` to have jbake on your machine.

****Step 4 ****
