FROM ubuntu
RUN apt update && apt upgrade -y && apt install sshpass openssh-server sudo python3 python3-apt -y && service ssh start
RUN ln -s /usr/bin/python3 /usr/bin/python
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config && echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config
RUN useradd -rm -d /home/ansible_user -s /bin/bash -g root -G sudo ansible_user && echo 'ansible_user:admin' | chpasswd
RUN echo 'ansible_user ALL=(ALL) NOPASSWD: ALL' > /etc/sudoers.d/ansible_user

CMD ["/usr/sbin/sshd", "-D"]
