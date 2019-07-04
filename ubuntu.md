# Ubuntu command

## fix error [AH00037: Symbolic link not allowed or link target not accessible: /var/www/..]

I needed the public directory so that Nginx could access files in my project directories. This solution came to me today:

```
sudo chmod 750 /home/quannh
sudo adduser www-data quannh
```

So I gave r-x access to my home directory to the user group to which my user belongs to. Then I added Nginx user to my group.