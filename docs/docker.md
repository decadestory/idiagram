
## zookeeper
```
docker run -d --name zookeeper --privileged=true --network app-tier  \
    -e ALLOW_ANONYMOUS_LOGIN=yes \
    -v /data/zookeeper/:/bitnami/zookeeper \
    bitnami/zookeeper
```

## kafka
```
docker run -d --privileged=true --name kafka \
    --network app-tier \
    -p 9092:9092 \
    -e KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper:2181 \
    -e KAFKA_CFG_MAX_REQUEST_SIZE=419430400 \
    -e ALLOW_PLAINTEXT_LISTENER=yes \
    -e KAFKA_ZOOKEEPER_PROTOCOL=PLAINTEXT \
    -e KAFKA_CFG_LISTENERS=PLAINTEXT://:9092 \
    -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://192.168.4.11:9092 \
    -v /data/kafka:/bitnami/kafka \
    -v /data/kafka_config:/opt/bitnami/kafka/conf \
    bitnami/kafka
 ```


 ## kafka-map
 ```
docker run -d \
   -p 8001:8080 \
   -v /opt/kafka-map/data:/usr/local/kafka-map/data \
   -e DEFAULT_USERNAME=admin \
   -e DEFAULT_PASSWORD=admin \
   --name kafka-map \
   --restart always dushixiang/kafka-map:latest
```

 ## clickhouse

 ```
 docker run -d -p 8123:8123 -p 9000:9000 --name clickhouse \
    --ulimit nofile=262144:262144 \
    -v /data/clickhouse:/var/lib/clickhouse \
    -v /data/clickhouse-log/clickhouse-server:/var/log/clickhouse-server \
    -v /data/clickhouse-config/clickhouse-server/config.xml:/etc/clickhouse-server/config.xml \
    -v /data/clickhouse-config/clickhouse-server/users.xml:/etc/clickhouse-server/users.xml \
    --privileged=true \
    -e CLICKHOUSE_PASSWORD=123456 \
    --restart=always \
    clickhouse/clickhouse-server
 ```

 ## redis
```
docker run -p 6379:6379 --name redis \
-v /data/redis/conf/redis.conf:/etc/redis.conf \
-v /data/redis/data:/data \
--restart=always \
-d redis:5.0.5 redis-server /etc/redis.conf \
--requirepass "123456"
```

 
 ## nginx
 ```
 docker run --name nginx-gateway -p 80:80 -v /data/nginx-gateway-config/nginx.conf:/etc/nginx/nginx.conf -d nginx

 docker run --name nginx --privileged -p 80:80 -v /data/nginx:/etc/nginx -v /data/websites:/data/websites -d nginx
 ```