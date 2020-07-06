# Docker Setup

## Install Docker

1. Install Docker

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

2. Add your user to the `docker` group `sudo usermod -aG docker rasp`
3. Log out and log back in to apply the change
4. Test whether Docker is working by running the _Hello World_ container `docker run hello-world`
5. If it works, the container will output a message that explains what it did.
