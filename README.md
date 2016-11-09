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
$ ansible-playbook -i hosts deploy.yml -c paramiko
```
