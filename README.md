# RUDYAttackDemo
Commands to execute
mkdir rudydos
cd rudydos
virtualenv --no-site-packages env
source env/bin/activate
touch pip.req run.py
Open pip.req add following text
requests
requesocks
beautifulsoup4

pip install -r pip.req

Download rum.py file

Setup Doku Server
sudo apt-get install apache2 libapache2-mod-php php-xml
sudo a2enmod rewrite
cd /var/www
sudo wget https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz
sudo tar xvf dokuwiki-stable.tgz
sudo mv dokuwiki-*/ dokuwiki
sudo chown -R www-data:www-data /var/www/dokuwiki
sudo nano /etc/apache2/sites-enabled/000*.conf

Replace
DocumentRoot /var/www/html
with
DocumentRoot /var/www/dokuwiki

sudo a2ensite apache2-dokuwiki
sudo service apache2 reload

sudo nano /etc/apache2/apache2.conf

For directory /var/www/ replace
AllowOverride None
with
AllowOverride All

sudo service apache2 restart
Visit site 192.168.131.129/doku.php

Start the attack
python ./run.py --connections 500 --target http://192.168.131.129/doku.php

Attack started


