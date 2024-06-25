FROM python:3.8-slim
RUN pip install ansible
RUN apt-get update && apt-get install -y sshpass
WORKDIR /usr/src
CMD ["ansible-playbook", "-i", "hosts", "play.yml", "-vvv"]