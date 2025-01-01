Скачиваем образ:
docker pull jupyter/pyspark-notebook

Запускаем контейнер:
docker run -d -it --name sparkbook -p 8888:8888 -p 4040:4040 -v sparkvolume:/home/media jupyter/pyspark-notebook:latest


Jupyter работает по адресу:
localhost:8888


Jupyter просит ввести Token ID, выполняем следующее:
docker logs sparkbook

В строке https://127.0.0.1:8888 находим токен

SparkUI:
localhost:4040
(пока не выполняется никаких действий, SparkUI может быть не доступен, но Spark работает)

Можно проверить работу
docker exec -it sparkbook bash
pyspark

>>> spark.range(1000 * 1000* 1000).count()