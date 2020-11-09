# Jenkins with suggested plugins ready

A simple Jenkins image with suggested plugins installed

Use following commands to build & push to Quay.io;

```
docker build --pull -t quay.io/enterprisecoding/jenkins-suggested:latest .
docker push quay.io/enterprisecoding/jenkins-suggested:latest
```

Use following commands to start container;

```
echo "admin" | docker secret create jenkins-user -
echo "admin" | docker secret create jenkins-pass -


docker run --name jenkins -d -p 8080:8080 -p 50000:50000  --secret jenkins-user --secret jenkins-pass quay.io/enterprisecoding/jenkins-suggested:latest

```