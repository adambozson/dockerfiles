FROM archlinux/base
LABEL maintainer "Adam Bozson <adam@bozson.io>"

COPY pacman.conf /etc/pacman.conf
RUN pacman -Syu --noconfirm
RUN pacman -S wget file \
              nvidia nvidia-utils lib32-nvidia-utils \
              ttf-liberation xdg-user-dirs mesa-demos \
              pciutils base-devel git \
              wine-staging winetricks lib32-mpg123 \
              --needed --noconfirm


RUN pacman -S --noconfirm pulseaudio pulseaudio-alsa lib32-libpulse lib32-alsa-plugins
COPY pulseaudio.client.conf /etc/pulse/client.conf
ENV PULSE_SERVER=/tmp/pulseaudio.socket PULSE_COOKIE=/tmp/pulseaudio.cookie

RUN groupadd -g 1000 user \ 
    && useradd --no-log-init -rm -u 1000 -g 1000 user
USER user
ENV LANG en-GB

CMD ["bash"]

