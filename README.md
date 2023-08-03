## dockerfiles
Dockerfile projects for development environment

### ubuntu

The compiler contains `g++ clang rust curl vim wget ...`

### Usage

docker run -it --rm --name ubuntu-dev --log-opt max-size=1g --log-opt max-file=5 -v /home/:/home/ --workdir /home -P ubuntu
