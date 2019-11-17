FROM php:7.2-cli

RUN docker-php-ext-install pdo_mysql

RUN apt-get update && apt-get install git openssh-server supervisor mc -y

RUN mkdir -p /var/run/sshd /var/log/supervisor

RUN sed -i -r 's/.?PermitRootLogin.+/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -i -r 's/.?PubkeyAuthentication.+/PubkeyAuthentication yes/' /etc/ssh/sshd_config

RUN mkdir -p /root/.ssh
RUN chmod 700 /root/.ssh
COPY ./keys/id_rsa.pub /root/.ssh/authorized_keys
RUN chmod 600 /root/.ssh/authorized_keys

EXPOSE 22

WORKDIR /var/www/${HOST_NAME}

COPY ./supervisord/supervisord.conf /etc/supervisor/supervisord.conf
CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]
