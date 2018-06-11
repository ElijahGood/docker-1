FROM debian

RUN apt-get update -q
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get install -yq --no-install-recommends \
      ca-certificates \
      openssh-server \
      wget \
      postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && bash script.deb.sh
RUN apt-get update && EXTERNAL_URL="http://gitlab.example.com" apt-get install -yq gitlab-ce
RUN apt update && apt install -y tzdata
RUN echo "/opt/gitlab/embedded/bin/runsvdir-start&\nEXTERNAL_URL="localhost" && gitlab-ctl reconfigure\ncat" >> entrypoint.sh && chmod 755 /entrypoint.sh

EXPOSE 22
EXPOSE 80

ENTRYPOINT ["bash", "entrypoint.sh"]
