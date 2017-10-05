## Alberto Bravi, albertobravi.com

* cd /etc/nginx/sites-enabled
* sudo ln -s /var/www/beautyaway.it/beautyaway_nginx beautyaway

copiare i certificati ssl: https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-14-04

* sudo git clone https://github.com/letsencrypt/letsencrypt /opt/letsencrypt
* cd /opt/letsencrypt
* ./letsencrypt-auto certonly --standalone --email alberto.bravi@gmail.com -d albertobravi.com -d www.albertobravi.com
* sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048
* touch /var/log/le-renew.log
* sudo chmod 777 /var/log/le-renew.log
* crontab -e
* 30 2 * * 1 /opt/letsencrypt/letsencrypt-auto renew >> /var/log/le-renew.log
* 35 2 * * 1 /etc/init.d/nginx reload
