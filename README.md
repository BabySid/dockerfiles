## dockerfiles
Dockerfile projects for development environment

### ubuntu

The compiler contains `g++ clang rust curl vim wget ...`

#### Build

`cd ubuntu && docker build -t babysid/ubuntu:latest . --no-cache`

#### Usage

`docker run -it --rm --name ubuntu-dev --log-opt max-size=1g --log-opt max-file=5 -v $(echo $HOME):/home/ --workdir /home -P babysid/ubuntu:latest`


