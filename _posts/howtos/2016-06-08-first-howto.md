---
layout: post
category: howto
title: Ubuntu, Splunk, and CYD CGI
---

This is the first How-To which will have you install Ubuntu, Splunk Light, and the CGI for receiving the data from the CYD iPhone App. This initial How-To is a very quick run through but we will expand upon it adding screen captures and more detail on the installs and setup.

<p>Install Ubuntu Server</p>
<p>- Go to http://www.ubuntu.com/server to download and install</p>
<p>- More detailed steps will be added to assist you on the install</p>
<p>- The Ubuntu Server I have installed is 14.04 LTS Server</p>

Install Splunk Light on your Ubuntu Server
- The Splunk site has the instructions located <a href="http://docs.splunk.com/Documentation/SplunkLight/6.4.1/Installation/InstallonLinux">here</a>
- An example for install would be "sudo dpkg -i splunklight-6.4.0-f2c836328108-linux-2.6-amd64.deb"

Install CollectYourData CGI
- First we need to setup Apache to allow running of CGI's
- cd /etc/apache2/mods-enabled
- sudo ln -s ../mods-available/cgi.load
- sudo service apache2 reload
- Download the <a href="https://github.com/collectyourdata/CYD-iPhone-CGI">CYD-iPhone.cgi</a> and place it in the "/usr/lib/cgi-bin/" directory on your Ubuntu Server then run the command
- sudo chmod +x /usr/lib/cgi-bin/CYD-iPhone.cgi

Xcode and CYD iPhone App
- Download Xcode and install on your Mac
- Dowload the CYD iPhone App <a href="https://github.com/collectyourdata/CYD-iPhone-App">source code</a>
- Build and Run the source code to view the App
- Update the Server field in the App to point to the CGI on the Ubuntu Server
- For example, "http://192.168.0.1/cgi-bin/CYD-iPhone.cgi"
- Click SEND to send a test message

Final Splunk setup
- If everything is setup correctly so far, your test message should be contained in "/tmp/CollectYourData-iPhone"
- Now just go into your Splunk Light software and setup the CollectYourData-iPhone file to be read continously by Splunk Light
