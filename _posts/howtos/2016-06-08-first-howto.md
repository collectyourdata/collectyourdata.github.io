---
layout: post
category: howto
title: Ubuntu, Splunk, and CYD CGI
---

This is the first How-To which will have you install Ubuntu, Splunk Light, and the CGI for receiving the data from the CYD iPhone App. This initial How-To is a very quick run through but we will expand upon it.

Install Ubuntu Server
- Go to http://www.ubuntu.com/server to download and install
- More detailed steps will be added to assist you on the install
- The Ubuntu Server I have installed is 14.04 LTS Server

Install Splunk Light.
- The Splunk site has the instructions located <a href="http://docs.splunk.com/Documentation/SplunkLight/6.4.1/Installation/InstallonLinux">here</a>
- An example for install would be "sudo dpkg -i splunklight-6.4.0-f2c836328108-linux-2.6-amd64.deb"

Install CollectYourData CGI
- First we need to setup Apache to allow running of CGI's
- cd /etc/apache2/mods-enabled
- sudo ln -s ../mods-available/cgi.load
- sudo service apache2 reload
- Download the "CYD-iPhone.cgi" and place it in "/usr/lib/cgi-bin/" location on your Ubuntu Server then run the command
- sudo chmod +x /usr/lib/cgi-bin/CYD-iPhone.cgi

Install CYD App. Use Xcode to compile and install to iPhone
- Install Xcode and download the CYD App project
