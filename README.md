# Jenkins with suggested plugins ready

A simple Jenkins image with suggested plugins installed

Use following commands to build & push to Quay.io;

```
docker build --pull -t quay.io/enterprisecoding/jenkins-suggested:latest .
docker push quay.io/enterprisecoding/jenkins-suggested:latest
```

Use following commands to start container;

```
mkdir secrets
echo "admin" > secrets/jenkins-user
echo "admin" > secrets/jenkins-pass

docker run --name jenkins -d -p 8080:8080 -p 50000:50000  -v ${PWD}/secrets:/var/secrets quay.io/enterprisecoding/jenkins-suggested:latest

```