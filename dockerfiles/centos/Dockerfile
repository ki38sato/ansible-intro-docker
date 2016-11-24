FROM centos:6.8

RUN yum -y install openssh-server sudo \
  && ssh-keygen -f /etc/ssh/ssh_host_rsa_key -N '' -t rsa \
  && ssh-keygen -f /etc/ssh/ssh_host_ecdsa_key -N '' -t ecdsa \
  && sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config \
  && echo "root:" | chpasswd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]