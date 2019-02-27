# docker-gitlab
Dockerfile creates an image with Ubuntu 16.04 and Gitlab CE.

## Procedures
### 1. Build an Image using Dockerfile
To create an image
```
docker build -t image-name:version .
```

For other Gitlab CE Version
```
docker build --build-arg GITLABCE_VERSION=11.7.5-ce.0 -t gitlab-ce:11.7.5 .
```

For list of Gitlab CE Version, visit this link:
```
https://packages.gitlab.com/gitlab/gitlab-ce/packages/
```

### 2. Create a Gitlab Container
To create a container
```
docker run -p 8443:443 -p 8000:80 -p 2222:22 --name my_gitlab --restart always -d gitlab-ce:11.8.0
``` 

Reconfigure Gitlab
```
docker exec -ti my_gitlab gitlab-ctl reconfigure
```