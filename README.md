# hadoop
Configuraciones, programas, ejemplos, ... relacionados con Hadoop

## Cluster Hadoop-Docker
En el archivo docker-compose.yml se encuentra la configuración del cluster, el cual se compone de:

HDFS
Un NameNode (namenode)

Tres DataNode (datanode1, datanode2, datanode3)

YARN
Un ResourceManager (resourcemanager)

Un NodeManager (nodemanager)

Ejecución
Arranque el cluster mediante `docker-compose -d up`

Esta parte puede demorar bastante hasta que se descarguen todas las imágenes y el sistema se estabilice.

Eventualmente, si ejecuta (en otro terminal) `docker ps`, los seis contenedores deberían indicar en su status `(healthy)`
