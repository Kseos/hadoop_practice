Кластер Hadoop с Hue:

git clone https://github.com/knight99rus/hadoop_full_pack --config core.autocrlf=input

cd hadoop_full_pack/docker-files

docker compose up --no-start

docker start database
docker start superset_cache
docker start superset_db
docker start superset_init

docker compose up -d

| Сервис    | URL               | Примечания                          |
|-----------|-------------------|-------------------------------------|
| Namenode  | localhost:9870    | Управление HDFS                     |
| Datanode  | localhost:9864    | Мониторинг узлов хранения данных    |
| Hive      | localhost:10002   | Hive сервер                         |
| Hue       | localhost:8888    | Веб-интерфейс Hadoop                |
| Spark     | localhost:8080    | Spark Master                        |
| Superset  | localhost:8008    | Аналитическая платформа             |