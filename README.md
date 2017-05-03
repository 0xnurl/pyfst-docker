# PyFST Docker Image
## Easily install and run Pyfst using OpenFST 1.6.0 and Python 3.6

* Pyfst: [http://pyfst.github.io/](http://pyfst.github.io/)
* OpenFST: [http://www.openfst.org/twiki/bin/view/FST/WebHome](http://www.openfst.org/twiki/bin/view/FST/WebHome)
 
Pyfst will be installed in a [virtualenv](https://virtualenv.pypa.io/en/stable/) in the container home directory: `~/venv/`. See Dockerfile for more information.
 
### Usage

#### Pull from Docker Hub 
`$ docker pull 0xnurl/pyfst-docker`

https://hub.docker.com/r/0xnurl/pyfst-docker/

#### or Clone and Build
`$ docker build -t pyfst:latest ./docker/`

#### Starting the container
```
$ docker run -i -t pyfst:latest
```
Parameters explained: 
* `-i` - Interactive shell
* `-t` - Spawn a terminal