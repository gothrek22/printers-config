FROM fedora:36

RUN dnf -y install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm && \
  dnf -y install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

RUN dnf install -yq \
  autoconf \
  automake \
  avrdude \
  bash \
  cmake \
  curl \
  ffmpeg \
  fontconfig \
  gcc-c++ \
  git \
  libjpeg-devel \
  procps \
  python3-devel \
  wget

WORKDIR /octoprint

ENV PYTHONUSERBASE=/octoprint/vendor

RUN pip3 install -U pip && \
  pip3 install -U OctoPrint

ENV PYTHONPATH=/octoprint/vendor:$PYTHONPATH

ENV PIP_USER true

COPY docker/entrypoint.sh /entrypoint.sh

CMD ["/entrypoint.sh"]
