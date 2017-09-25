# mongodb-demo replica

## Usage

Create containers with `docker-compose`.

```
$ docker-compose up -d
```

Initiate replica set.

Connect to the primary mongod container. 

```
$ mongo
```

Use `rs.initiate()` on one.

```
rs.initiate( {
    _id : "rs0",
    members : [ { _id : 0, host: "mongo-pri:27017" } ]
} )
```

Add the remaining members to the replica set.

```
rs.add("mongo-sec1")
rs.add("mongo-sec2")
```
