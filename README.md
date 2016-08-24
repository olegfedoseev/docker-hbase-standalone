# Docker image for standalone HBase

[![](https://images.microbadger.com/badges/image/olegfedoseev/docker-hbase-standalone.svg)](http://microbadger.com/images/olegfedoseev/docker-hbase-standalone "Get your own image badge on microbadger.com")

Small, standalone HBase for development. With REST and Thrift servers.

# Exposed ports

* 8080/8085 - REST API & Web UI
* 9090/9095 - Thrift API & Web UI
* 60000/60010 - HBase Master & Web UI
* 60020/60030 - HBase RegionServer & Web UI
* 2181 - ZooKeeper

# Volumes

You can mount volume for data at `/data`.
HBase will store its data at `/data/hbase`, ZooKeeper at `/data/zookeeper`.

# How to use

Pull it:

	docker pull olegfedoseev/hbase-standalone:0.98.21

Run it:
	docker run -it --rm \
		--name hbase \
		--hostname hbase \
		-p 9090:9090 \
		-p 9095:9095 \
		-p 2181:2181 \
		-p 60000:60000 \
		-p 60010:60010 \
		-p 60020:60020 \
		-p 60030:60030 \
		olegfedoseev/hbase-standalone:0.98.21
