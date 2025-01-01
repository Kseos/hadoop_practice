Для подключения jupyter notebook к hive

docker pull apache/hive:4.0.1

docker run -d -p 10000:10000 -p 10002:10002 --env SERVICE_NAME=hiveserver2 --name hive apache/hive:4.0.1

docker exec -it hive hiveserver2 beeline -u 'jdbc:hive2://hiveserver2:10000/'