FROM kashiwaguma-hiro/sshd:0.0.1


RUN mkdir /tmp/src/ &&\
    touch /tmp/src/mainte.html &&\
    mkdir /tmp/dest/

RUN touch /tmp/src/health_check_ng.html


EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
