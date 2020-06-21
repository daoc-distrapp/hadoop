# hadoop
Configuraciones, programas, ejemplos, ... relacionados con Hadoop

## Cluster Hadoop-Docker
En el archivo docker-compose.yml se encuentra la configuración del cluster, el cual se compone de:

### HDFS
Un NameNode (namenode)

Tres DataNode (datanode1, datanode2, datanode3)

### YARN
Un ResourceManager (resourcemanager)

Un NodeManager (nodemanager)

### Ejecución
Arranque el cluster mediante `docker-compose -d up`

Esta parte puede demorar bastante hasta que se descarguen todas las imágenes y el sistema se estabilice.

Eventualmente, si ejecuta (en otro terminal) `docker ps`, los seis contenedores deberían indicar en su status `(healthy)`

Vamos a probar ahora con los ejemplos en https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-mapreduce-examples/3.2.1/hadoop-mapreduce-examples-3.2.1.jar así que descargue este archivo

Cargue el archivo en el namenode (preferentemente) o el resourcemanager (en teoría cualquier nodo del cluster debería funcionar) `docker cp hadoop-mapreduce-examples-3.2.1.jar namenode:.`

Para los datos, vamos a usar un pequeño archivo de texto (la Biblia en inglés) en el primer ejemplo `http://www.gutenberg.org/cache/epub/10/pg10.txt`

Cargue este archivo también en el namenode `docker cp pg10.txt namenode:.`

Vamos a crear un directorio en hdfs para subir nuestro archivo de texto `hdfs dfs -mkdir -p input`

Pasemos ahora el archivo a hdfs `hdfs dfs -put pg10.txt input/`
