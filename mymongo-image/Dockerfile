# step 1: getting base image (O.S.) we will use alpine, i.e. a light linux distribution
FROM alpine

# step 2 : install a software

# RUN apk add binutils

# now we well install via links

RUN echo "http://dl-cdn.alpinelinux.org/alpine/v3.6/main" >> /etc/apk/repositories

RUN echo "http://dl-cdn.alpinelinux.org/alpine/v3.6/community" >> /etc/apk/repositories

RUN apk update
RUN apk add mongodb=3.4.4-r0
RUN apk add binutils

# binutil is a program, apk add is kind of yum install of linux.

# step 2.5 : configure that software
# creating data/db directory.
# mounting it
VOLUME [ "/data/db" ]

# /data is working directory, meaning anyone who opens container shell will land in this /data directory
WORKDIR /data

# since mongo is a service, we are providing it with a port.
EXPOSE 27017

# step 3 : set default commands
# format is : CMD {command name sperated by apostophe}

# CMD {"npm" "install"}
CMD [ "mongod" ]

# so basically we installed alpine and installed binutils program in it. now we want to store this image.
