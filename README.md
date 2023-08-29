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
### Reserve product
Stock service will listen for event from kafka "reserve-product" topic and then proceed to check stock

### Product reserved
After checking the product is correct and in stock. The stock service will send events to kafka's "product-reserved" topic.

### Product cancelled
If the product check does not exist or the inventory is not enough. The stock service sends events to kafka's "product-cancel" topic.

### Product update
The stock service will receive events from kafka's "product-update" topic. After that, we will proceed to increase the number of products that need to be updated
