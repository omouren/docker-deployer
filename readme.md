# docker-deployer

Docker image to use Deployer (Deployment tool for PHP) without the need to have PHP on your host.

See [Deployer.org](https://deployer.org/)

On GitHub : [deployphp/deployer](https://github.com/deployphp/deployer)

## How to use
[See on Docker Hub](https://hub.docker.com/r/omouren/docker-deployer/)
``` bash
# To run "dep"
$ docker run --rm -ti -v $(pwd):/app omouren/docker-deployer:latest
# To run "dep init"
$ docker run --rm -ti -v $(pwd):/app omouren/docker-deployer:latest init
# To run "dep deploy" with SSH Agent Forwarding
$ docker run --rm -ti -v $(pwd):/app -v $(dirname $SSH_AUTH_SOCK):$(dirname $SSH_AUTH_SOCK) -e SSH_AUTH_SOCK=$SSH_AUTH_SOCK omouren/docker-deployer:latest deploy
```

## Alias
Now just add an alias to use it more simply (in your ~/.bash_aliases for example)
``` bash
alias dep="docker run --rm -ti -v $(pwd):/app omouren/docker-deployer:latest"
# Or
alias dep="docker run --rm -ti -v $(pwd):/app -v $(dirname $SSH_AUTH_SOCK):$(dirname $SSH_AUTH_SOCK) -e SSH_AUTH_SOCK=$SSH_AUTH_SOCK omouren/docker-deployer:latest"
```
