# Nginx

## 1. Installing Nginx

    sudo apt update
    sudo apt install nginx

## 2. Adjusting the Firewall

If you followed the prerequisite server setup tutorial, then you have the UFW firewall enabled. Check the available ufw application profiles with the following command:

    sudo ufw app list

Output
```
Available applications:
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
```

Let's enable the most restrictive profile that will still allow the traffic you've configured, permitting traffic on port 80:
```
sudo ufw allow 'Nginx HTTP'
```

Verify the change:
```
sudo ufw status
```
Output
```
Status: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere                  
Nginx HTTP                 ALLOW       Anywhere                  
OpenSSH (v6)               ALLOW       Anywhere (v6)             
Nginx HTTP (v6)            ALLOW       Anywhere (v6)
```

## Checking your Web Server
Check with the systemd init system to make sure the service is running by typing:

    systemctl status nginx


