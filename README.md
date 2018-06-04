supervisor-sshd-dind
====================

A Docker image to run SSH server and DIND (Docker in Docker). Useful to validate locally Ansible playbooks. 

## How to build

### Build an image based on CentOS 7

```
cd centos/7
docker build -t supervisor-sshd-dind:centos7 .
```

## Usage

```
docker run -d -e USER=developer -e PASSWORD=developer --privileged -t supervisor-sshd-dind:centos7
```


