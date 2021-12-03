# Reto: Movilidad Urbana
# Team

-  Jose Granger - A01023661
-  Jorge Cabiedes - A01024053

## Diagrama de Clase y Protocolo de Agentes

![](https://i.imgur.com/1OwPz1P.png)

## Jerarquia de Acciones

* Darle a carro un destino aleatorio
* Darle a carro una posicion inicial aleatoria
* Correr algoritmo de pathfinding para el carro
* Seguir camino regresado
    *    Si se encuentra obstaculo, pausar camino (luz roja,otro carro)

## Instrucciones de Instalacion

### Descargas

Antes que nada se necesitan instalar 4 componentes criticos para que funcione el programa.

* Un IDE de programación
* Python 3.8
* Mesa : `pip install mesa`
* Flask : `pip install flask`

### LocalHost

Para correr el programa en localhost se tiene que navegar al folder que contiene el archivo usando la terminal y correr el siguiente commando : 

`python server.py`

Una vez creado eso podra ver en la consola el link a la simulacion local usando Mesa.

En caso de querer verlo en unity se tendra que usar el siguiente commando: 

`python server_unity.py`

Una vez que se haya empezado el servidor, abrir el projecto en Unity y poner los parametros preferidos en la parte superior derecha.

Asegurese de que el url sea el que uso python para iniciar el servidor.

### IBM Cloud

Para hostear el servidor en IBM Cloud, se necesita instalar el CLI de [Cloud Foundry](https://github.com/cloudfoundry/cli#downloads). Siguiendo las instrucciones del [IBM-Cloud repo](https://github.com/IBM-Cloud/get-started-python)

Una vez que se haya instalado todo esto se necesitan utilizar los siguientes comandos en sequencia en el folder donde se encuentra el archivo de server_unity.

```
cf api https://api.ng.bluemix.net
cf login
cf push
```

En la seccion de login asegurarse de poner su usuario de IBM Cloud.

El push tomara unos segundos pero en cuanto le de la confirmacion, el link que se uso como api va a funcionar como nuestro servidor. Es este link que tendrian que poner el el parametro de url de Unity, como mencionado anteriormente.

Despues de esto solo quedaria poner sus parametros de preferencia en Unity y correr.

## Video de Ejecución

https://drive.google.com/drive/folders/1xj9D3aAvMFHnHMzqMkTSQ4sEfCePEtz4?usp=sharing

## Reflexion Individual

### Jose Granger Salgado

#### Análisis

El modelo de multiagentes que utilizamos es la forma mas efficiente que pudimos pensar para realizar este reto, usando lo que aprendimos en la entrega anterior. Tomamos en menta la forma mas eficiente y corta para lograr cumplir los requerimientos del reto. 

No queriamos que se realizara una misma función docenas de veces pero tampoco queriamos encontrar ineficiencia en el programa.

Al mismo tiempo queriamos que la simulación fuera totalmente funcional sin importar la cantidad de agentes presentes y cambios de estados requeridos.

Es por esto que decidimos usar un algoritmo de pathfinding que usa BFS, solamente corre una vez por carro y el carro solo sigue el camino amenos de encontrar un obstaculo en donde pausa el movimiento.

La ventaja de esto es que encuentra el camino mas optimo, con parametros aleatorios y en un corto plazo. Ademas de esto solo se necesita correr una vez y darle las coordenadas al carro.

Aunque nosotros consideramos que esta solución es la mas eficiente tanto en espacio, tiempo y complejidad. Puede que exista un algoritmo que nos pueda dar el mismo resultado de una forma mas eficiente. 

Un problema es que aveces se puede generar trafico en los semaforos. Lo cual puede que se solucione si se implementa un sistema donde los carros se pueden comunicar información y basa sus caminos en estas nuevas variables. 

Otra posible solución podria desactivar calles si tienen muchos carros en espera, para que no se añadan mas carros al monton, o posiblemente una forma de darle timers a los carros para que viajen al mismo tiempo que cambian de color los semaforos.

Se pueden idear varias formas de poder potencialmente mejorar el producto segun nuestras variables predefinidas y lo que aprendimos a lo largo de curso, pero consideramos que la solucion propuesta es cerca de la ideal.

En cuanto al diseño grafico, en la simulacion de Mesa elegimos elementos simples con colores claros para que se puedan distinguir los objetos 2D con claridad, pero en Unity como no tenemos ese problema decidimos hacer una simulación de una cuidad futuristica con carros del mismo genero, principalmente porque nos gusto como se veia.

#### Reflexión

Al inicio del semestre, tenia una idea muy diferente de lo que este projecto iba a tratar. Creia que iba a tener aprendizajes mas de Inteligencia Artificial, y en cierta forma, los temas que vimos estan cercamentes relacionados con IA. 

La realización de Modelos Multiagentes me parecio muy util para una gran variedad de sistemas, el futuro del mundo esta en la automatización, todas las areas en el mundo se estan dirigiendo a eso, y con estos conocimientos podemos tener una facil entrada a esta area de gran importancia.

Aunque fue un poco de lastima que fue un curso corto, no se pueden subestimar el valor que nos dio. Nos dio una oportunidad de entender como muchos sitemas funcionan. (Carros de manejo automatico, roombas, robots de envio, simulaciónes de todo tipo de temas, etc...).

El proceso de aprender fue un poco dificil ya que teniamos que aprender muchas cosas en un span de tiempo muy corto, pero creo que pudimos lograr un producto final interesante y funcional.

Estoy emocionado para poder hacer un projecto en el futuro con lo que he aprendido en esta clase, especialmente lo de Unity, ya que nos permiten darle un toque extra a nuestras simulaciones y poder traer la tercera dimensión a nuestros projectos aunque no tengan que ver con modelacion de multiagentes.

### Jorge Cabiedes Acosta

#### Análisis

#### Reflexión
