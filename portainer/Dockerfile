### ex) make image 
# $ docker build -t ${user}/portainer:1.24.1
### ex) run
# $ docker run -d -p 9000:9000 \
#   --name portainer \
#   --restart always \
#   -v "/var/run/docker.sock:/var/run/docker.sock"
#   -v "/opt/portainer:/home/${user}/docker/portainer/data"
#   ${user}/portainer:1.24.1
# --------------------------------------------------------- #

# ARG user="neruo"

FROM portainer/portainer:1.24.1

#ENV DEBIAN_FRONTEND=noninteractive
#RUN set -x \
# && apt-get update \
# && apt-get install -y --no-install-recommends \
#    tzdata \
# && apt-get -y clean \
# && rm -rf /var/lib/apt/lists/*
# ENV TZ Asia/Tokyo

# VOLUME "/var/run/docker.sock:/var/run/docker.sock"
# VOLUME "/opt/portainer:/home/${user}/docker/portainer/data"

