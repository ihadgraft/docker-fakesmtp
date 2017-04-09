# Example configuration

    services:
      php:
        image: dukewebservices/php:7.0-fpm
        links:
          - mail
        environment:
          - PHP_INI_SENDMAIL_PATH: '/usr/sbin/sendmail -t -i -S mail'
      
      mail:
        image: dukewebservices/fakesmtp:latest
        volumes:
          - ./persistent/mail:/var/mail
