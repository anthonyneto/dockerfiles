FROM ubuntu:zesty

# docker run -it --rm \
#   --name audio-test \
#   --device /dev/dri \
#   --device /dev/snd \
#   --device /dev/input \
#   -e DISPLAY=unix$DISPLAY \
#   -e PULSE_SERVER=unix:/run/user/1000/pulse/native \
#   -v /tmp/.X11-unix/:/tmp/.X11-unix/ \
#   -v /dev/shm:/dev/shm \
#   -v /run/user/1000/pulse:/run/user/1000/pulse \
#   -v /var/lib/dbus:/var/lib/dbus \
#   anthonyneto/audio-test

RUN apt update \
  && apt install -y sudo pulseaudio \
  && useradd -G audio -G video -G staff -m user

ADD user-sudoer /etc/sudoers.d/user

USER user

CMD /bin/bash
