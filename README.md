# iperf3 service in a Docker container

## Install Docker and Docker-compose

### Windows

Not yet support

https://docs.docker.com/docker-for-windows/install/

and it contained docker-compose.

### Linux

Install Docker and select Docker CE is fine.

- [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)
- [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)
- [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)
- [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

Install docker-compose.

https://docs.docker.com/compose/install/

## Run it

```shell
> git clone git@github.com:tknv/iperf3-docker-compose
> cd iperf3-docker-compose
> docker-compose build --no-cache
> docker-compose up
```

## iperf3 it

```shell
> iperf3 -c <Dcoker host IP address> -p 50001
```

## Customize it

`vim docker-compose.yml`

```yaml
...
    ports:
      - "<which port from>:5001/tcp"
      - "<which port from>:5001/udp"
...
    command: iperf3 -s <options> -p 5001
...
```

That's it.


