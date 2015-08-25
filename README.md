# Server Configs  
This is a collection of server configuration files I use in my own local development. I periodically format my PC to keep things clean and fast (and to make sure I don't start hoarding things), and so I have to set up my local development environment again each time I do. They are here as a backed-up central location for my own reference, but feel free to use anything you like. 

***DO NOT USE THESE ON PRODUCTION SERVERS***  
These are not production safe configurations. They have not been tested, vetted, approved, or recommended for use in anything than a low security local development environment. They might not even work out of the box on your system. Read each config before you use it.

```bash
$ git clone git://github.com/bitdagger/serverconf.git
```

It’s more likely you’ll want to read the configuration files and find snippets relevant to your particular workflow.  

## Contents
* Apache 2.4  
These hardly differ much from the defaults, but it does set up MIMEmagic, has the include and loadmodule lines for php as well as the config files for php5 and phpmyadmin, and has a vhosts config for subdomain resolution on the local.dev domain.  

* BIND  
Very simple DNS caching and zone for the local.dev domain to point everything at the loopback address. Forwarders are set to Google's public DNS servers. The zone file goes in `/var/named` and should be readable by `named`, and you'll need to touch `/var/logs/named.log` and make it writable by `named`.  

* PHP  
Almost straight default with a few provisions for a Laravel/composer/phpmyadmin/wordpress style environment. Still needs some TLC.  

* Samba  
Basic public/read-only/private share config. Mostly just used for my home network to move files around and network storage.  

## Installation  
Eventually I'll probably include a Makefile, but for now a manual copy-paste into the respective applications' config directories is all it takes. In a few cases you might need to touch and/or set permissions on log files and such.

License
-------

Public domain; see the included `UNLICENSE` file. It’s just configuration, do
whatever you like with it if any of it’s useful to you. 
