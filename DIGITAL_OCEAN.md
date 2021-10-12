# Hosting docker images in Digital Ocean

ssh into droplet

## Install docker

## pull docker samples

git clone https://github.com/mpab/docker

## Setup firewall

```console
sudo ufw allow 'Nginx FULL'
sudo ufw enable
sudo ufw app list
sudo ufw status
```

## Install nginx

```console
sudo apt update
sudo apt install nginx
systemctl status nginx
```

## Get droplet IP and check nginx

```console
curl -4 icanhazip.com
curl <IP>
```

And/or point your web browser at the returned http IP

## Configure domains in nginx

add hosts to server_name in config

```console
sudo nano /etc/nginx/sites-available/default
#
server_name (host).com www.(host).com
#
sudo nginx -t
sudo service nginx reload
```

## Configure certbot

```console
sudo apt-get install python-certbot-nginx
# or...
sudo apt-get install python3-certbot-nginx

sudo certbot --nginx -d (host).com
# choose not to redirect HTTP to HTTPS until you have tested things work as expected
```

```log
- Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/swaplink.app/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/swaplink.app/privkey.pem
   Your cert will expire on 2022-01-10. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot again
   with the "certonly" option. To non-interactively renew *all* of
   your certificates, run "certbot renew"
```

## References

<https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04>

<https://linuxconfig.org/firewall-ufw-status-inactive-on-ubuntu-20-04-focal-fossa-linux>