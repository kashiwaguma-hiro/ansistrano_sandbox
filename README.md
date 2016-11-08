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

4. entry docker container

```bash
$ 
```