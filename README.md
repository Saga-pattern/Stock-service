# Stock-service

## How to build and push to docker
Clone repo
```
git clone https://github.com/Saga-pattern/Stock-service.git
```

Go to the project
```
cd Stock-service
```

Build project. Push image to docker hub
```
docker build -t stock-service .
```
```
docker tag stock-service <your-repo>:latest
```
```
docker push <your repo>:latest
```

## Event flow send and receive
