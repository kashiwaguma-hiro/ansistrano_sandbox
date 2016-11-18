FROM kashiwaguma-hiro/sshd:0.0.1


RUN mkdir /tmp/src/ &&\
    touch /tmp/src/mainte.html &&\
    mkdir /tmp/dest/



EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
