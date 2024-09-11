# Verwende m1k1o/neko als Basis-Image
#FROM m1k1o/neko:latest
ARG BASE_IMAGE=m1k1o/neko:base
FROM $BASE_IMAGE

# Installiere OBS Studio und Xvfb
RUN apt-get update && apt-get install -y openbox obs-studio ffmpeg xvfb libxcb-xinerama0

# Kopiere die angepasste supervisord.conf in den Container
COPY supervisord.conf /etc/neko/supervisord/obs.conf

# copy configuation files
COPY openbox.xml /etc/neko/openbox.xml

# Starte supervisord, um Xvfb und OBS zu starten
CMD ["supervisord", "-c", "/etc/neko/supervisord.conf"]