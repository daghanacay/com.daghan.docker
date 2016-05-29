#Prerequisites
Docker run

#Build the docker as follows

$docker build -t daghan/eclipse .

do not forget the "." at the end.

#Usage

Create a seerate directory and in the directory create two folders that will be used to persist eclipse plugins and workspace as follows

mkdir -p .eclipse
mkdir -p workspace


Then run the following command 

docker run -ti --rm \
           -e DISPLAY=$DISPLAY \
           -v /tmp/.X11-unix:/tmp/.X11-unix \
           -v /home/daghan/git:/home/developer/git \
           -v `pwd`/.eclipse:/home/developer/.eclipse \
           -v `pwd`/workspace:/home/developer/workspace \
           -p 8080:8080/tcp \
           --name eclispe_mars2 \
           daghan/eclipse

