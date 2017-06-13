# drupal-cron
A dockerized Cron for Drupal

Executes drush cron periodically.

Usage example:

```
app:
   image: introbay/php:7.0-apache
   links:
    - db:mysql
   volumes:
    - ./html:/var/www/html
   ports: 
    - 80:80
cron:
   image: introbay/drupal-cron:latest
   links:
    - db:mysql
   volumes_from:
    - app
db:
   image: mysql:5.6
   volumes:
    - ./db:/var/lib/mysql
```
