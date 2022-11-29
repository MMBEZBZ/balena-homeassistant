# FROM balenalib/%%BALENA_MACHINE_NAME%%-debian:bullseye-build
FROM pachyderm/opencv:arm64

WORKDIR /face

RUN apt-get update && apt-get install -y gcc cmake libboost-context-dev libboost-dev curl libpq-dev cmake 

COPY face/ .


RUN mkdir build 
WORKDIR /face/build 
RUN cmake .. && make -j4

CMD ["./LiveFaceReco"]