FROM centos:8
RUN dnf install -yq \
  curl \
  wget \
  bash \
  python3-devel \
  ffmpeg \
  automake \
  autoconf \
  cmake \
  curl \
  fontconfig \
  gcc-c++ \
  git \
  libjpeg-devel

WORKDIR /octoprint

ENV PYTHONUSERBASE=/octoprint/vendor

RUN pip3 install -U pip && \
  pip3 install -U OctoPrint

ENV PYTHONPATH=/octoprint/vendor:$PYTHONPATH

ENV PIP_USER true

COPY docker/entrypoint.sh /entrypoint.sh

CMD ["/entrypoint.sh"]
