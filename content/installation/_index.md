---
title: "Installation"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Installation with PECL
### Linux
```bash
sudo pecl install kafka
```
In your `php/conf.d` folder add a `kafka.ini` with the following:
```ini
extension=kafka.so
```
### Windows
Download DLLs from PECL and  put `librdkafka.dll` in the root PHP directory (same level as `php.exe`)  
and the `php_rdkfaka.dll` file in your PHP extension directory (`ext` by default).
Add the following line to your `php.ini` file:
```ini
extension=php_kafka.dll
```
### Manual installation
```bash
git clone https://github.com/php-kafka/php-kafka.git
cd php-kafka
phpize && ./configure && make -j5 all && make install
```
In your `php/conf.d` folder add a `kafka.ini` with the following:
```ini
extension=kafka.so
```
