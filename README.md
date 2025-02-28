# DB und Infra Repo


This repository contains the Database for the [IT Wintercamp Ticket System](https://github.com/IT-Wintercamp-2025) project.

## Server:
  - Rasperry Pi 4
  - 8GB RAM
  - 128 GB Storage SD Card
  - Image: Ubuntu 24.04.2 LTS arm64
  The Pi is automattically connecting to the specified WLAN that's defined in the Internet section.
  - **hostname:** pi-server
  - **Login:** pi
  - **passwd:** bier123
## Internet:
  To get internet on the Raspberry Pi 4, we use a Windows Laptop as Man In The Middle (MITM).
  1. Connect the Windows Laptop to a Internet Source like a WLAN, let's call it "baum"
  2. Creat a Access Point (AP) with the name "pi" and a very safe Password in example: "23456789"
  3. The Pi should connect to the AP and get an IP address. The default is Pi IP is 192.168.137.33
  4. To change the IP address, would be the easy way to do it via the Desktop and the nm-connection-editor
  5. If everything is working, the Windwos Laptop host a Subent and the Pi is in it, so you would be ablo to connect to it if you are in the same network.
   
## Database:
The database is a mariadb in a Docker Container and is running on the Raspberry Pi and at the same time also phpMyAdmin.

With this setup it is possbile to connect to the database with a local client or with a remote client and change live some data and test these with an application or view them in the db in a browser with phpMyAdmin.


## Side information:
  The Hotspot isn't a normal one, because you can use ssh or other protocols in the Subent.

  This hotspot is more a Access Point (AP)

  - A **oneliner** to monitor some stuff and get some information on the screen/ssh session.
  ###### while true; do  echo '' ; date ; echo '' ;echo '# --- Running Docker Container ---# ' ; docker ps ; echo '' ; w ; echo '' ; ip a | grep '192.168.137.33' ; echo  ''; echo 'WLANNNNNNNN: pi' ; echo 'WLAN Passwd: 23456789'; echo ''; echo 'Usernameeee: pi' ;echo 'Passwordddd: bier123' ; echo '' ; neofetch ; sleep 15; cls ; done

