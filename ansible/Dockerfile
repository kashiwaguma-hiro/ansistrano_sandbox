FROM ansible/centos7-ansible:stable

# powerd by https://docs.docker.com/engine/examples/running_ssh_service/
RUN yum install -y openssh-server

RUN mkdir /var/run/sshd
RUN echo 'root:rootroot' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]