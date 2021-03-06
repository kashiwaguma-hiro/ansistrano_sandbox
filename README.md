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

4. deploy execute on local enviroment
```bash
$ docker exec -it ansistranosandbox_ansible_1 bash
```

Deploy to apis.
```bash
$ ansible-playbook -i local -l apis deploy.yml --extra-vars "major_version=v1 module_name=master.zip" -c paramiko
```

Deploy to batchs.
```bash
$ ansible-playbook -i local -l batchs deploy.yml --extra-vars "major_version=v1 module_name=master.zip" -c paramiko
```

Deploy to subscribeers.
```bash
$ ansible-playbook -i local -l subscribers deploy.yml --extra-vars "major_version=v1 module_name=master.zip" -c paramiko
```

# optional
## create mainte.html only.
```bash
$ ansible-playbook -i local -l apis --tags "mainte" deploy.yml  -c paramiko
```

Check apis hosts, successed crate mainte.html.
```bash
$ ls /tmp/dest/
mainte.html
```

## remove mainte.html only for ansistranosandbox_api2_1.
```bash
$ ansible-playbook -i local -l ansistranosandbox_api2_1 --tags "unmainte" deploy.yml  -c paramiko
```

Check ansistranosandbox_api2_1 hosts, successed remove mainte.html.
```bash
$ ls /tmp/dest/
```