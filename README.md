
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table de Contenido</summary>
  <ol>
    <li>
      <a href="#hadoop-installation">Instalacion de Hadoop</a>
      <ul>
        <li><a href="#map-reduce-exercise">Map reduce</a></li>
        <li><a href="#word-count-exercise">Contador de palabras</a></li>
      </ul>
    </li>
    <li>
      <a href="#spark-installation">Instalacion de spark</a>
      <ul>
        <li><a href="#word-count-exercise-spark">Contador de palabras con Spark</a></li>
        <li><a href="#word-count-exercise-spark-extension">Contador de palabras por condiciones</a></li>
      </ul>
    </li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## Introduccion
En este Readme se van a demostrar y a describir cada uno de los pasos a seguir para la instalacion de Hadoop y Spark en entornos linux, para este caso, ubuntu y centos.

Sitemas operativos usados:
* Se creo una maquina virtual para la instalacion de Hadoop, esta vm tiene como OS Centos 6 
* Se creo una VM para la instalacion de Spark con ubunto 20

## Instalacion de Hadoop
Al ver el contenido del archivo part-r-0000 podemos observar el número de palabras que contiene las iniciales kms[a-z]+ y las palabras que lo contienen

<img width="599" alt="Screen Shot 2021-09-18 at 4 12 44 AM" src="https://user-images.githubusercontent.com/19766554/133883895-537ccb4f-1054-4014-b3e9-5048f3925ee4.png">

### Configuración cluster
Se crean las carpetas de datanode y namenode luego de configurar los archivos *-sites.xml y se da acceso general sobre esa carpeta

<img width="605" alt="Screen Shot 2021-09-18 at 4 13 03 AM" src="https://user-images.githubusercontent.com/19766554/133883930-c3e212ad-ec8d-4d43-8c2c-2467392ec46c.png">

Creamos el hdfs o administrador de información con el comando hadoop hdfs -format

<img width="697" alt="Screen Shot 2021-09-18 at 4 13 19 AM" src="https://user-images.githubusercontent.com/19766554/133883960-b9819be7-a3c1-4ea5-9b9b-d84cd87934d8.png">

Luego iniciamos todos los servicios de Hadoop con el hdsf con el comando 

  ```sh
  start-dfs.sh
  ```

  <img width="699" alt="Screen Shot 2021-09-18 at 4 13 38 AM" src="https://user-images.githubusercontent.com/19766554/133883993-b446f7e0-05d6-4a3b-be35-64073ee98582.png">

Podemos evidenciar el correcto funcionamiento de los procesos ejecutados por java asociados a HDFS

  ```sh
  con ps -ef | grep java
  ```
  
  <img width="657" alt="Screen Shot 2021-09-18 at 4 14 05 AM" src="https://user-images.githubusercontent.com/19766554/133884025-77c3a218-0c43-4262-a7d2-1e1416a18f64.png">

 Comprobación del correcto funcionamiento por medio del puerto 9870
 
 <img width="603" alt="Screen Shot 2021-09-18 at 4 14 15 AM" src="https://user-images.githubusercontent.com/19766554/133884051-88f04897-d593-4fc3-b9ad-641ec3f866e9.png">


### Talle 1
1. Comprobación de archivos example

<img width="700" alt="Screen Shot 2021-09-18 at 4 14 25 AM" src="https://user-images.githubusercontent.com/19766554/133884073-d7c72f6f-b8c7-4375-b9ef-39ff4936ed3c.png">

2. Ejecución jars de ejemplos

  <img width="673" alt="Screen Shot 2021-09-18 at 4 14 40 AM" src="https://user-images.githubusercontent.com/19766554/133884087-fe66a992-a552-4787-9163-843057e80c9b.png">
  
3. Ejecución de la clase gerp para hacer la búsqueda de palabras con un resultado de salida

<img width="653" alt="Screen Shot 2021-09-18 at 4 14 56 AM" src="https://user-images.githubusercontent.com/19766554/133884105-5ea0e57e-c5b5-441b-b7e4-62e5a7ac539b.png">

4. Resultado de ejecución en el directorio especificado

<img width="601" alt="Screen Shot 2021-09-18 at 4 15 04 AM" src="https://user-images.githubusercontent.com/19766554/133884124-7d8a9d5d-7cb6-412d-99b7-bcb018c1edae.png">

### Ejercicio 2

1. Cargamos el archivo cuento.txt con un cuento de prueba y lo cargamos al hdfs

<img width="576" alt="Screen Shot 2021-09-18 at 4 15 14 AM" src="https://user-images.githubusercontent.com/19766554/133884143-8da654dd-6ee9-4efa-bf81-c3460fb88a37.png">

2. Si nos dirigimos al browse directory podemos evidenciar el archivo cuento .txt

<img width="604" alt="Screen Shot 2021-09-18 at 4 15 23 AM" src="https://user-images.githubusercontent.com/19766554/133884154-1a1b81dc-4611-41cb-9813-78e038f15775.png">

3. Ejecutamos el ejercicio de word count

<img width="600" alt="Screen Shot 2021-09-18 at 4 15 32 AM" src="https://user-images.githubusercontent.com/19766554/133884168-b6539549-9b36-4a15-b346-5da3f86d4c27.png">

4. Nos dirigimos al explorador de archivos y podemos evidenciar el resultado en el archivo part-r-000000

<img width="605" alt="Screen Shot 2021-09-18 at 4 15 40 AM" src="https://user-images.githubusercontent.com/19766554/133884188-b4739674-b0f9-40ba-8e1a-c202be52ab5d.png">

5. Descargamos el archivo, lo abrimos y podemos evidenciar los resultados de cada palabra y la cantidad de repeticiones de la misma

<img width="609" alt="Screen Shot 2021-09-18 at 4 15 49 AM" src="https://user-images.githubusercontent.com/19766554/133884203-18bc1635-85ac-4ff7-ba2a-d4ad90d2e497.png">


## Instalacion de Spark

Se realiza la instalacion y configuracion de Spark

<img width="601" alt="Screen Shot 2021-09-18 at 4 15 59 AM" src="https://user-images.githubusercontent.com/19766554/133884239-72279fa7-e2c6-43ab-b3b3-64de906006c5.png">

### Ejercicio 1 Spark
1. Inicializamos el shell de spak, y cargamos un archivo con la información que deseamos analizar, este archivo sera almacenado en memoria con el nombre de fichero

<img width="594" alt="Screen Shot 2021-09-18 at 4 16 08 AM" src="https://user-images.githubusercontent.com/19766554/133884249-7cf99a27-7df7-4b89-9227-175d5b6fed04.png">

2. procedemos a realizar la transformación de la data, el proceso que se hace con la data que está en fichero, es separar y eliminar data innecesario por medio de flatMap, luego con map se crea un nuevo arreglo retornando una tupla, con el valor de la palabra y 1 como valor de correlación, luego reduceByKey lo que hace es tomar el valor de correlación asignado y validar con las demás conciencias, sumando 1 y retornando el arreglo con esta tupla.

<img width="603" alt="Screen Shot 2021-09-18 at 4 16 17 AM" src="https://user-images.githubusercontent.com/19766554/133884284-cf52de85-db95-458c-8c2a-443ff4473086.png">

3. Se procede a guardar la información en un archivo llamado results, como en hadoop obtenemos dos archivos part-00000 es el archivo con los resultados de ejecución, y _ success 

<img width="597" alt="Screen Shot 2021-09-18 at 4 16 25 AM" src="https://user-images.githubusercontent.com/19766554/133884299-62761909-c567-4669-9f01-794cb50aabf2.png">

4. Al ingresar al archivo de resultados se observa lo siguiente

<img width="597" alt="Screen Shot 2021-09-18 at 4 16 32 AM" src="https://user-images.githubusercontent.com/19766554/133884317-0f5380f4-a44b-4f24-9c34-97e360318a6b.png">

### Ejercicio 2 Spark (Bono) - categorizando por sustantivos, adjetivos, verbos, preposiciones, etc.

1. Construir el RDD

  ```sh
lines = sc.textFile('adj_noun_pair.txt', 4)
  ```
  
 2. Convertir el texto a pares de palabras

  ```sh
pairs = lines.map(lambda l: tuple(l.split()))
pairs.cache()  # or pairs.persist()
  ```
  
   2. Calculo del numero total de pares y contruccion de la tabla de pares

  ```sh
pairs = lines.map(lambda l: tuple(l.split()))
pairs.cache()  # or pairs.persist()

N = pairs.count()
  ```
3. Luego contruimos la tabla de frecuencia para los pares

  ```sh
pair_freqs = pairs.map(lambda p: (p,1)).reduceByKey(lambda f1, f2: f1 + f2)
  ```

4. Calculamos la frecuencia de los adjetivos y los pronombres

  ```sh
a_freqs = pair_freqs.map(lambda pf: (pf[0][0], pf[1])).reduceByKey(lambda x,y: x+y)
n_freqs = pair_freqs.map(lambda pf: (pf[0][1], pf[1])).reduceByKey(lambda x,y: x+y)
  ```
  
5. Definiendo los pares de alta prefuencia

  ```sh
THRESHOLD=100
pair_freqs = pair_freqs.filter(lambda pf: pf[1] >= THRESHOLD)
  ```
  
6. Difucion de los adjetivos y suntantivos

  ```sh
a_dict = sc.broadcast(a_freqs.collectAsMap())
n_dict = sc.broadcast(n_freqs.collectAsMap())
  ```

6. Calculando el PMI de los pares

  ```sh
def pmi_score(pair_freq):
    w1, w2 = pair_freq[0]
    f =	pair_freq[1]
    pmi = math.log2((f*N)/(a_dict.value[w1]*n_dict.value[w2]))
    return pmi, (w1, w2)
  ```



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[hadoop-url]: https://hadoop.apache.org
[spark-url]: https://spark.apache.org
