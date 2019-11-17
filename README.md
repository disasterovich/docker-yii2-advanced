# Lite multi-container Docker application for Yii 2 Advanced Project Template. Includes: nginx, php-fpm, php-cli (includes sshd), mysql, adminer

- Configure .env file in root directory, set paths, passwords, etc

- Configure nginx files in ./nginx/sites-enabled/

- Set hosts in your local hosts file:

 ```
 192.168.99.104  my-site.local
 192.168.99.104  backend.my-site.local
 192.168.99.104  frontend.my-site.local
 ```

 Where 192.168.99.104 is ip address of docker machine
 (docker-machine ip) 

- Optional step. This is necessary for deployment. Copy your public key id_rsa.pub in ./php-cli/keys
It will be used for access through ssh (default port 2222).

- Build and run docker containers

```
docker-compose up -d --build
```

- Open php-cli container:

```
docker exec -it <container name> /bin/sh
```

change directory:

``` 
cd /var/www/my-site.local
```

and install [yii 2 advanced project template](https://github.com/yiisoft/yii2-app-advanced/blob/master/docs/guide/start-installation.md).
