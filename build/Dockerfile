FROM ubuntu:22.04
#FROM nvcr.io/nvidia/tensorflow:22.02-tf2-py3

RUN apt-get update
RUN apt-get install -y tzdata
RUN apt-get install -y cron bash
RUN apt-get install -y ffmpeg libsm6 libxext6
RUN apt-get install -y libxext-dev libgtk2.0-dev libgtk-3-dev libjpeg-dev libpng-dev libtiff-dev libxext-dev libxrender-dev python3-tk
RUN apt-get install -y x11-apps xauth
RUN apt-get install -y gnuradio
RUN apt-get install -y python3-pip python-is-python3

WORKDIR /radio

RUN pip install --upgrade pip
RUN pip install jupyter
RUN pip install matplotlib numpy scipy astropy pillow scikit-image pdbpp pandas scikit-learn
RUN pip install opencv-python lightgbm fastparquet seaborn ipaddress
COPY root.bashrc /tmp
RUN cat /tmp/root.bashrc >>/root/.bashrc && rm -f /tmp/root.bashrc
#ENTRYPOINT [ "sleep", "infinity" ]
ENTRYPOINT [ "cron", "-f" ]
