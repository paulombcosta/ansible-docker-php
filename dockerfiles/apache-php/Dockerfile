FROM williamyeh/ansible:debian8
MAINTAINER Paulo Costa <paulombcosta@gmail.com>

ADD ansible /srv/ansible
WORKDIR /srv/ansible

# Add localhost to the default ansible hosts
RUN echo localhost ansible_connection=local >> /etc/ansible/hosts

RUN ansible-playbook apache-php-container.yml -vvvv

EXPOSE 80

CMD /usr/sbin/apache2ctl -D FOREGROUND
