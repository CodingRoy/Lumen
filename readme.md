# Lumen
[![Build Status](https://travis-ci.org/CodingRoy/Lumen.svg?branch=master)](https://travis-ci.org/CodingRoy/Lumen)
Setting up a Laravel Lumen project from scratch.
Hopefully to create something that looks stunning and works like a charm, a simple blog/ forum or something..

### Installation on Ubuntu server
- While performing a clean install for Ubuntu server optionally opt-in for the 'OpenSSH server' for easy "copy & paste access". (Do not install any other snaps)
- No matter what project you do always apply the latest updates:
```sh
sudo apt update && sudo apt upgrade -y
``` 
- Lets install the requirements for composer and phpunit, oh and GIT ofcourse ;):
```sh
sudo apt install curl php-cli php-mbstring php-xml git unzip
```
- Now download the composer installer:
```sh
cd ~
curl -sS https://getcomposer.org/installer -o composer-setup.php
```
- Verify that the installer matches the SHA-384 hash for the latest installer found on the [Composer Public Keys / Signatures page](https://composer.github.io/pubkeys.html). Copy the hash from that page and store it as a shell variable like this:
```sh
HASH=48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5
```
- Now we let php check if the installer matches the hash key (You will see "Installer verified" if it matches):
```sh
php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```
- To install composer globally, use the following command which will install Composer as a system-wide command named composer, under /usr/local/bin:
```sh
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```
- After cloning this repository install the packages using Composer: 
```sh
composer install
```

##### Woo! You are ready to run and edit this repository! (that was easy right?)

### But wait.. How  do I run the app?
That's easy, just run: 
```sh
php -S localhost:8000 -t public
```

If you want the app to run on the default HTTP port use:
```sh
sudo php -S localhost:80 -t public
```

In both cases you can replace localhost with your internal IP if you want to acces it from other clients