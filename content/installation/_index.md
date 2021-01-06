---
title: "Installation"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Installation with PECL
Not yet support (WIP)

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
