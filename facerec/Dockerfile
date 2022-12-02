FROM balenalib/raspberrypi4-64-debian:bullseye-build
# FROM debian:bullseye
# FROM dimonds90/ubuntu_opencv4.4_cp38_runtime_armv8
# FROM pachyderm/opencv
# LABEL org.opencontainers.image.authors="mohammedmahfood2020@gmail.com"

# WORKDIR /home/
# COPY installOpenCV.sh .

# RUN chmod +x installOpenCV.sh
# RUN ./installOpenCV.sh





# Installing openCV



# Setup Environment Variable
ENV cvVersionChoice=1
ENV cvVersion="master"
ENV cwd="/home/"

WORKDIR $cwd
RUN apt-get update
RUN apt -y install software-properties-common
# RUN apt -y install gnupg
# RUN add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"
# RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 40976EAF437D05B5
# RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3B4FE6ACC0B21F32


RUN apt-get update -y
# 	apt-get remove -y 
RUN apt install -y git \
    build-essential \
    cmake \
    git \
    pkg-config \
    g++
#     libgtk-3-dev \
#     libavcodec-dev \
#     libavformat-dev \
#     libswscale-dev \
#     libv4l-dev \
#     libxvidcore-dev \
#     libx264-dev \
#     libjpeg-dev \
#     libpng-dev \
#     libtiff-dev \
#     gfortran \
#     openexr \
#     libatlas-base-dev \
#     # python3-dev \
#     # python3-numpy \
#     libtbb2 \
#     libtbb-dev \
#     libdc1394-22-dev \
#     libopenexr-dev \
#     libgstreamer-plugins-base1.0-dev \
#     libgstreamer1.0-dev
RUN git --version
RUN wget https://github.com/prepkg/opencv-raspberrypi/releases/latest/download/opencv_64.deb
RUN sudo apt install -y ./opencv_64.deb
# RUN cd /usr/include/linux && \
# 	ln -s -f ../libv4l1-videodev.h videodev.h && \
# 	cd $cwd

# RUN apt-get install -y \
# 	libgstreamer1.0-dev \
#     libgstreamer-plugins-base1.0-dev \
# 	libgtk2.0-dev \
# 	libtbb-dev \
# 	qt5-default \
# 	libatlas-base-dev \
# 	libfaac-dev \
# 	libmp3lame-dev \
# 	libtheora-dev \
# 	libvorbis-dev \
# 	libxvidcore-dev \
# 	libopencore-amrnb-dev \
# 	libopencore-amrwb-dev \
# 	libavresample-dev \
# 	x264 \
# 	v4l-utils \
# 	libprotobuf-dev \
# 	protobuf-compiler \
# 	libgoogle-glog-dev \
# 	libgflags-dev \
# 	libgphoto2-dev \
# 	libeigen3-dev \
# 	libhdf5-dev \
# 	doxygen




# RUN /bin/sh -c 'echo "/usr/local/lib" >> /etc/ld.so.conf.d/opencv.conf'
# RUN ldconfig







#  Building and Running Face regocntion
WORKDIR /face

# RUN apt-get update && apt-get install -y build-essential gcc cmake libboost-context-dev libboost-dev curl libpq-dev cmake 

RUN apt-get clean
COPY face/ .


RUN mkdir build 
WORKDIR /face/build 
RUN cmake .. && make -j4

CMD ["./LiveFaceReco"]
