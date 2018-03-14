FROM ubuntu:17.10

RUN apt-get update && apt-get install -y evolution evolution-ews dbus-x11 && rm -rf /var/cache/apt/

# Replace 1000 with your user / group id
RUN export uid=1000 gid=1000 username=my_user &&\
    mkdir -p /home/${username} &&\
    echo adding user &&\
    addgroup --gid ${gid} ${username} &&\
    adduser -disabled-password --gecos "" --gid ${gid} --uid ${uid} ${username} &&\
    echo added user &&\
    usermod -G sudo ${username} &&\
    chown ${uid}:${gid} -R /home/${username}

USER ${username}
ENV HOME /home/${username}
CMD /usr/bin/evolution
