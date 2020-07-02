ADempiere Business gRPC Docker Server
=====================
Use this server for enable all business data layer of ADempiere as a service, this docker project is related to https://github.com/erpcya/adempiere-gRPC-Server

[Docker](https://www.docker.io/) file for trusted builds of [ADempiere gRPC Deploy](http://erpya.com/) on https://hub.docker.com/r/erpya/adempiere-grpc-business.

You will need use a file with a structure like it: [business_connection.yaml](business_connection.yaml)
```yaml

server:
    port: 50052
database:
    host: localhost
    port: 5432
    name: "database"
    user: adempiere
    password: adempiere
    type: PostgreSQL
```

Run the latest container with:
```shell
    docker pull erpya/adempiere-grpc-business
```

```shell
docker run --name adempiere-grpc-business -it \
	-p 50052:50052 \
	-v $(pwd)/business_connection.yaml:/opt/Apps/ADempiere-gRPC-Server/bin/business_connection.yaml \
	erpya/adempiere-grpc-business
```
