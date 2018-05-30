# Dockerised InfluxDB Timeshift Proxy

[Dockerfile](https://github.com/juris/docker-influxdb-timeshift-proxy)
[Source code](https://github.com/maxsivanov/influxdb-timeshift-proxy)

Run standalone:

```sh
docker run -d --name influxdb-timeshift-proxy -e INFLUXDB=influx:8086 juris/influxdb-timeshift-proxy
```

Kubernetes container snippet (add to InfluxDB or Grafana pod):

```yml
      containers:
      - name: influxdb-timeshift-proxy
        image: juris/influxdb-timeshift-proxy
        ports:
        - containerPort: 8089
        env:
        - name: INFLUXDB
          value: influxdb:8086
```