# Jenkins with suggested plugins ready

A simple Jenkins image with suggested plugins installed

Use following commands to build & push to Quay.io;

```
docker build --pull -t quay.io/enterprisecoding/jenkins-suggested:latest .
docker push quay.io/enterprisecoding/jenkins-suggested:latest
```

Use following commands to start container;

```
echo "admin" > jenkins-user
echo "admin" > jenkins-pass

docker run --name jenkins -d -p 8080:8080 -p 50000:50000  -v  jenkins-user:/var/jenkins-user -v jenkins-pass:/var/jenkins-pass quay.io/enterprisecoding/jenkins-suggested:latest

```