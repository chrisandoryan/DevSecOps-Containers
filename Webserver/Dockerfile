FROM httpd

RUN apt update
RUN apt install openssh-server -y
RUN mkdir -p /var/run/sshd

# authorize SSH connection with root account
RUN sed -ri 's/#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config
RUN sed -ri 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN service ssh restart

# change password root
RUN echo "root:docker" | chpasswd

RUN service ssh restart

EXPOSE 80
EXPOSE 22
