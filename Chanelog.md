## Changelog

## Spring 2025

[ ] Revisions

- Custom jupyter image includes a language server and minio client

[x] Upgrades

    - jupyter / spark 3.5.3
    - drill to 1.21.2
    - cassandra 4.1.7
    - elasticsearch 8.17.0
    - minio 2024-12-13T22-19-12Z
    - mongo 6.0
    - neo4j 5.26
    - redis 7.4
    - confluent kafka 7.8.0

[ ] Tests Matrix

| System | Spark | Drill | Notes |
| ----- | ----- | ----- | ----- |
| Hadoop/Hive/HDFS | ✅ | N/a | Hadoop 3.3.4 |
| minio | ✅ | ✅ | |
| Mongo | ✅ | ✅ | |
| Cassandra | ✅ | ✅ | |
| Redis | ✅ | N/a | |
| Neo4j | ✅ | N/a | |
| Elasticsearch | ✅ | ✅ | |
| Kafka | ✅ | ✅ | |
| Iceberg (new) | ? | ? | |

[ ] Update Docker instructions
