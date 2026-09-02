# Health Check

- It is important that you use depends_on and condition

```yaml
version: '3.9'
services:
    elasticsearch:
        image: docker.elastic.co/elasticsearch/elasticsearch:5.4.3
        healthcheck:
            test: |
                curl -X PUT elasticsearch:9200/scheduled_actions -H "ContentType: application/json" -d '{"settings":{"index":{"number_of_shards":'1',"number_of_replicas":'0'}}}' &&
                curl --silent --fail localhost:9200/_cat/health ||
                exit 1
            interval: 11s 
            timeout: 10s 
            retries: 3
        environment:
            - discovery.type=single-node
            - ES_JAVA_OPTS=-Xms1g -Xmx1g
            - xpack.security.enabled=false
    main:
        image: alpine
        depends_on:
            elasticsearch:
                condition: service_healthy
```
