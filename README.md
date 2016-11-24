# ansistrano_sandbox

# usage

1. build core image.(first only.)
```bash
$ docker build -t kashiwaguma-hiro/sshd:0.0.1 ./core
```

2. build web and batch image.(first only.)
```bash
$ cd ..
$ docker-compose build
```

3. up web and batch.
```bash
$ docker-compose up -d
```

4. deploy execute
```bash
$ docker exec -it ansistranosandbox_ansible_1
$ ansible-playbook -i local deploy.yml -c paramiko
```

# optional

## create mainte.html only.
Try it command.
```bash
ansible-playbook -i local -l apis --tags "mainte" deploy.yml  -c paramiko
```

Check apis hosts, successed crate mainte.html.
```bash
root@c196958b6238:~# ls /tmp/dest/
mainte.html
```

## remove mainte.html only for ansistranosandbox_api2_1.
Try it command.
```bash
ansible-playbook -i local -l ansistranosandbox_api2_1 --tags "unmainte" deploy.yml  -c paramiko
```

Check ansistranosandbox_api2_1 hosts, successed remove mainte.html.
```bash
root@c196958b6238:~# ls /tmp/dest/
```