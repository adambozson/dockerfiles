FROM archlinux/base:latest

RUN pacman -Syu --noconfirm
RUN pacman -S --needed --noconfirm pulseaudio pulseaudio-alsa avahi shairport-sync sudo

COPY pulseaudio.client.conf /etc/pulse/client.conf

RUN groupadd --gid 1000 alarm \
    && useradd -rm --uid 1000 --gid 1000 alarm \
    && echo 'alarm ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER alarm
ENV PULSE_SERVER=/tmp/pulseaudio.socket PULSE_COOKIE=/tmp/pulseaudio.cookie

