# FROM balenalib/%%BALENA_MACHINE_NAME%%-debian:bullseye-build
FROM pachyderm/opencv:arm64

WORKDIR /face

RUN install_packages gcc cmake libboost-context-dev libboost-dev curl libpq-dev cmake 

COPY face/ .


RUN mkdir build 
RUN CD build 
RUN cmake .. && make -j4

CMD ["./LiveFaceReco"]