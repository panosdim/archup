```
   ###    ########   ######  ##     ## ##     ## ########  
  ## ##   ##     ## ##    ## ##     ## ##     ## ##     ## 
 ##   ##  ##     ## ##       ##     ## ##     ## ##     ## 
##     ## ########  ##       ######### ##     ## ########  
######### ##   ##   ##       ##     ## ##     ## ##        
##     ## ##    ##  ##    ## ##     ## ##     ## ##        
##     ## ##     ##  ######  ##     ##  #######  ##        
```

#ArchUp
This utility let you know for package updates when you log in. In order to
achieve that, it is using the checkupdates script that comes installed with pacman
package. It writes the result of checkupdates script to `/etc/motd` file. When the
user logs in the system the contents of motd file are shown as message of the day to
the user.
This utility is NOT updating the system, it only provides a notification. It is up to
the user to update the system. This utility is run every one hour to check for updates.
If you need more frequent check for update then edit the `archup.timer` file before install.
The user then must update the system using `archup -u`, otherwise the contents of motd
file are not cleared and he must wait until the next trigger of archup utility 
(default is every 1 hour) in order the `/etc/motd` file to be cleared.

##Requirements
In order for this utility to work you need and Arch Linux with systemd, bash and
pacman installed.

##Installation
Run the install script as root
```
# ./install
```

##Usage
When you log in and see a message that some packages need update then update the
system with the `archup -u` command:
```
  # ssh padi@goflex.dtdns.net
  padi@goflex.dtdns.net's password: 
  Warning: No xauth data; using fake authentication data for X11 forwarding.
  X11 forwarding request failed on channel 0
  Last login: Thu Aug 24 12:08:10 2017 from 129.192.10.2
  Following packages need update
  gnutls 3.5.14-1 -> 3.5.15-1
  icu 59.1-1 -> 59.1-2
  lz4 1:1.7.5-1 -> 1:1.8.0-1
  vim 8.0.0851-1 -> 8.0.0987-1
  vim-runtime 8.0.0851-1 -> 8.0.0987-1
  #
  # archup -u
  [sudo] password for padi: 
  :: Synchronizing package databases...
  core                    185.2 KiB   231K/s 00:01 [######################] 100%
  extra is up to date
  community is up to date
  alarm is up to date     0.0   B  0.00B/s 00:00 [------------------------]   0%
  aur is up to date       0.0   B  0.00B/s 00:00 [------------------------]   0%
  :: Starting full system upgrade...
  there is nothing to do 
```

##Contacts
If you have problems, questions, ideas or suggestions, please contact me at:
Panagiotis Dimopoulos panosdim@gmail.com