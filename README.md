Practica 1: Hacer una pagina con wordpress 
Vamos a Portal.Azure.com
Vamos a marketplace
Buscamos wordpress y elegimos la primera opcion
Le damos a crear
Creamos un nuevo grupo de recursos, elegimos la suscripcion, elegimos la region y le ponemos nombre a la pagina.
si queremos podemos añadir etiquetas
Creamos el recurso
Una vez creado el recurso vamos al URL que nos dan
Aqui llenamos lo que se nos solicita
Para acceder a la configuración vamos al dominio y colocamos wp-admin
Aqui ya podemos editar nuestra pagina.

Practica 2: Usar NoteBooks en azure Machine learning
Creamos una Azure Machine Learning desde Portal.Azure.com
Colocamos suscripcion, grupo de recursos, la region y un nombre
Vamos a ml.azure.com
Vamos al area de trabajo que creamos desde portal.azure
Vamos al apartado de proceso / Compute
Creamos una instancia de proceso
Le ponemos nombre y seleccionamos el tamaño de maquina virtual que nos convenga
Vamos al apartado notebooks
creamos un archivo
Escribimos nuestro codigo
ejecutamos

Practica 3: Maquina virtual en una maquina virtual
Vamos a Portal.Azure.com
Buscamos Maquinas virtuales. y creamos una
Colocamos suscripcion, grupo de recursos, nombre y region
Seleccionamos windows 10 pro
Elegimos el tamaño standart
Ponemos un nombre de usuario y contraseña
Abrimos solo el puerto RDP
le damos a crear
creamos otra maquina virtual igual
ahora en redes en red virtual seleccionamos la “nombre de red”_group-vnet
Y asegurense de que las 2 maquinas esten en la misma red virtual
Creamos la segunda maquina virtual
Entramos a una maquina virtual
le damos a RDP y descargamos el RDP
y abrimos el archivo con la aplicacion remote desktop
colocamos el usuario y la contraseña
vamos al apartado de redes y vamos a  la red _group-vnet y a dispositivos conectados, ahi salen las direcciones ip
configuramos la virtual machine 1
buscamos powershell y lo abrimos como administrador
escribimos:  New-NetFirewallRule -DisplayName “Allow ICMPv4-In” -Protocol ICMPv4
escribimos: mstsc /v:”ip de la otra maquina”
e iniciamos sesion en la otra maquina
asi conectamos 2 maquinas virtuales

Practica 4: App Service, la pagina web
vamos a portal.azure.com
buscamos appservices
creamos uno
colocamos suscripcion, nombre, grupo de recursos y region
elegimos el entorno de ejecucion PHP8.0
Elegimos el tamaño
y lo creamos
ve al acordeon de Azure y ve a semana 2 y ve a lab de Azure App Service
clonamos el repositorio, copiamos el link en SSH
vamos a la terminal y vamos a donde lo quieras copiar
ponemos git clone y el link pegado
creamos un repositorio y subimos el codigo por carpeta (elige la pagina web)
vamos al recurso
vamos a centro de implementacion
en origen ponemos github
iniciamos sesion en github
buscamos el repositorio
en rama colocamos main
agregar un flujo de trabajo
guardamos
vamos al repositorio
actualizamos y en actions veremos como se implementa
nos da los links de la pagina

Practica 5: Azure functions, pagina rara
Vamos a portal.azure.com
buscamos azure functions
le damos en crear
ponemos suscripcion, grupo de recursos, nombre y region
ponemos en pila del entorno el lenguaje que nos convenga
usamos windows
y consumo serverless
lo creamos
vamos al recurso
vamos al apartado de funciones
creamos una funcion
ponemos un HTTP trigger
una vez se cree vamos a codigo y prueba
damos a probar/ejecutar
y cambiamos “Azure” por “bryan”
asi y solo la utilizamos donde ocupemos

Practica 6: Azure logic App, lector de twits
Vamos a portal.azure.com
buscamos logic apps
creamos una
colocamos suscripcion, grupo de recursos, nombre y region
en plan colocamos consumo
la creamos
entramos al recurso
le damos a a diseñador de aplicacion logica
creamos en logic apps una aplicacion logica en blanco
colocamos twitter
y en por cada nuevo tweet
ponemos un nombre
iniciamos sesion con una cuenta de twitter
colocamos el # de donde queremos sacar los tweets
con 5 segundos
abrimos un google drive y hacemos un archivo con columnas que digan id del tweet, twiteado por, texto del tweet, localizacion, sentimiento y fecha
agregamos un paso a logic apps
ponemos text 
azure cognitive services
elegimos sentimiento
abrimos otro portal.azure.com
buscamos cognitive services
creamos un servicio de lenguaje
colocamos suscripcion, grupo de recursos, nombre y region
plan de tarifa gratis
confirmamos todo y creamos
abrimos el recurso
vamos a claves y punto de conexion
copiamos la clave y la ponemos en el logicapp
tambien el url y le damos nombre
le damos en crear
en document ponemos id del tweet
en document text el texto del tweet
siguiente paso
ponemos google sheet
insertar file
iniciamos sesion con nuestra cuenta de google
seleccionamos el archivo que hicimos
en hoja de calculos ponemos tweets
agregamos todos los parametros
id del tweet, id del tweet
twiteado por, twiteado por
texto del tweet, texto del tweet
localizacion, ubicacion
sentimiento, sentiment
fecha, creado
lo ejecutamos y ya estaria

Practica 7: Azure virtual network
Vamos a portal.azure.com
creamos un grupo de recursos - buscando grupo de recursos

Creamos una red virtual - ponemos suscripcio, nombre, grupo, region (asegurate de que esten en la misma region australia -central) y en direccion ip debe aparecer 10.0.0.0/16
eliminamos la default sub red
agregamos una sub red llamada subnet1, en intervalo ponemos 10.0.0.0/24
la agregamos
revisamos y la creamos

Creamos otra red virtual - ponemos sucripcion, nombre, region y en direccion ip debe aparecer 10.1.0.0/16
agregamos una subnet2, en intervalo 10.1.0.0/24
agregamos
revisamos y creamos

creamos dos maquinas virtuales en linux - ponemos sucripcion, nombre, grupo, region. usuario, contraseña, tamaño deben estar en la misma region que las redes australia central, ponemos usuario y contraseña en ambas
en puertos de entrada elegimos SSH
vamos a redes y usamos la red virtual 1
en la maquina virtual 2 ponemos la red virtual 2
y las creamos

vamos al recurso de la maquina virtual 1
abrimos el Azure Cloud Shell
vamos a conectar SSH y copiamos lo ultimo que viene despues del >
ponemos bash
ponemos ssh y lo que copiamos
ponemos yes
ponemos la contraseña
ya estas conectado con la maquina virtual
pon sudo apt-get moo

vamos a la red virtual 1, a emparejamientos
agregamos un emparejamiento
le ponemos nombre, le ponemos nombre del vinculo, agregamos suscripcion, seleccionamos la  red virtual destino (la 2)
dejamos todo igual
la agregamos
esperamos hasta que diga conectado

vamos a red virtual 2 y vamos a dispositivos conectados, copeamos la ip de la vm 2
en el cloud shell ponemos ping “direccion ip”
y ya estan conectadas

Practica 8: Blob storage
vamos a portal.azure.com
buscamos cuentas de almacenamiento
le damos a crear
ponemos suscripcion, grupo de recursos, nombre y region
rendimiento: estandar si no ocupas mucha velocidad
redundancia: lo dejamos igual
en acceso de red asegurense de que este habilidado el acceso publico y que se el enrutamiento de microsoft
y la creamos
vamos al recurso
vamos al apartado contenedores
creamos un contenedor
le ponemos nombre
nivel de acceso: contenedor lector anonimo
entramos al contenedor
cargar
seleccionamos un archivo
y lo cargamos

Practica 9: File Storage
vamos al apartado recursos compartidos de archivos
agregamos uno
le ponemos nombre
nivel: transaccion optimizada
la creamos
cargamos
seleccionamos el archivo
y cargamos el archivo
damos click en conectar
elegimos el dispositivo
en mac ponemos el codigo en la terminal
en windows usamos powershell

Practica 10: queu storage
vamos al apartado colas
agregamos una cola
ponemos nombre
accedemos
agregamos mensaje

Practica 11: table storage (clase 6 57:00)
Vamos al apartado table
agregamos una tabla
vamos a explorador de almacenamiento
buscamos tablas
le damos click
agregamos una entidad
le ponemos nombre y el valor

Practica 12: creacion de base de datos sql desde cloud shell
Vamos al acordeon
semana 2 consultas sql para azure sql database
abrimos el cloud shell

ponemos git clone https://github.com/MicrosoftLearning/DP-900T00A-Azure-Data-Fundamentals dp-900
ponemos cd dp-900/sql
ponemos bash setup.sh

vamos a donde se creo
abrimos base de datos sql
vamos a establecer firewall del servidor
agregamos la direccion IPv4 del cliente
guardamos
vamos al apartado editor de consultas
iniciamos sesion
usuario: sampleLogin
contraseña: samplePassword123!

ahi podemos ver las tablas que se hicieron
ponemos SELECT * FROM Inventory
ponemos SELECT * FROM CustomerOrder
ponemos INSERT INTO Inventory (Id, Inventory.name, Stock) values(7, ’Strawberry',500);
ponemos SELECT * FROM Inventory
asi nos da los datos

Practica 13: Cosmos (clase 6 1:38:00)
Vamos a portal.azure.com
buscamos cosmos
creamos uno
seleccionamos Nucleo SQL
agregamos suscripcion, grupo de recursos, nombre y region
aplicamos el descuento de nivel gratis
revisamos y lo creamos

vamos al recurso
elegimos el lenguaje que queramos (node.js)
creamos un contenedor items
podemos descargar la aplicacion o abrir el explorador de datos
en todolist-items-items
le damos a new item
ponemos “id” : “1!,
ponemos “nombre” : “Jesus”,
ponemos “apellido” : “Guzman,
le damos a save
y a update
asi podemos poner mas items
para consultar vamos al apartado de doble ventana
SELECT * FROM c
SELECT * FROM c where c.id = “1”

Practica 14: Alerta de azure health
Vamos a portal.azure.com
buscamos service health
le damos click
ahi podemos seleccionar de nuestra suscripcion de nuestra region y de nuestros servicios
damos click en añadir alerta
en servicios ponemos los servicios que nos interesa
en region elegimos la region que nos interesa
en tipo de evento que tipo de errores debe notificar
seleccionamos grupo de acciones
creamos un grupo de acciones
agregamos suscripcion, nombre, grupo de recursos.
notifcacion
en notificaciones ponemos correo electronico
en nombre  el nombre que queramos
en la pestaña ponemos nuestro correo
revisamos y creamos el recurso
en grupos de acciones de prueba podemos probarlo, click en grupo de acciones de prueba
seleccionamos el ejemplo y test
vamos a nuestro correo y ahi llega la alerta
ponemos nombre de una regla 
le damos a crear regla de alertas

Practica 15: Alerta Azure monitor
vamos a portal.azure.com
creamos una maquina virtual de windows
buscamos monitor
abrimos la maquina virtual
en monitor vamos a metricas seleccionamos la maquina virual y le damos a aplicar
seleccionamos en metrica el percentage CPU
en en apartado alertas
creamos una regla de alertas
seleccionamos nuestra suscripcion y en filtrar maquinas virtuales elegimos la que creamos y en listo
en condicion buscamos servicio percentage CPU
valor umbral 40
granulacion cada 1 minuto y listo
en detalles ponemos gravedad y nombre y creamos
ya esta listo, cada que la maquina virtual pase del 40% de procesamiento mandara una notificacion

practica 16: plantillas arm 
en azure crea un grupo de recursos llamado practica-16
crea un documento en visual studio llamado azuredeploy.json
descarga la extension azure resource manager
coloca esto en el documento
{
      "$schema": "https://schema.managment.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
      "contentVersion" : "1.0.0.0",
      "resources" : [
      {
            "type" : "Microsoft.Storage/storageAccounts",
            "apiVersion" : "2021-09-01",
            "name" : "micuentadealmacenamiento",
            "location" : "Central US",
            "sku" : {
                  "name" : "Standard_LRS"
            },
            "kind" : "StorageV2",
            "properties" : {
                  "supportsHttpsTrafficsOnly" : true
            }
      }
      ]
}

en tu terminal (con cli)
pon:  az deployment group create --name mi-primera-plantilla --resource-group practica-16 --template-file azuredeploy.json
si sale running ya se esta implementando
vamos al grupo de recursos
a implementaciones y ahi esta

Practica 17: IA  ML auto(clase 8, 25:00)
vamos a ml.azure.com
creamos un area de trabajo
agregamos suscripcion, nombre, grupo de recursos y region
la creas

vamos al area de trabajo
vamos al aparado proceso/compute
vamos a crear una instancia de proceso
le damos a nuevo, ponemos nombre, elegimos CPU, elegimos el tamaño que nos deje
la creamos

vamos al link de bicis semana 3 acordeon (https://aka.ms/bike-rentals)

vamos al apartado datos, creamos de archivos web
pegamos el link de bicis
le ponemos nombre
tabular
descripcion datos de renta de bicis
NO omitir validacion de datos
encabezado de columna: solo el primer archivo tiene encabezados
delimitador: coma
añadimos todas las etiquetas menos el Path
creamos

vamos al apartado proceso
a clusteres de proceso
creamos uno
region
dedicado
CPU
tamaño
nombre
numero minimo de nodos, 2 maximo 0 minimo
creamos

vamos al apartado ml automatizado
le damos a nuevo trabajo
seleccionamos la de renta de bicis
siguiente
le damos a crear
le ponemos nombre
columna destino: rentals
seleccionar un tipo de proceso: cluster de proceso (el que creamos)
y seleccionamos el que creamos
seleccionamos regresión
lo finalizamos

Practica 18: IA Face
vamos a ml.azure.com
creamos un espacio de trabajo
creamos una instancia de trabajo
vamos al apartado notebooks
le damos en + y en crear archivo
le ponemos nombre.jpynb
vamos al acordeon github.com/josejesusguzman/face-api-consumption-python
https://github.com/josejesusguzman/face-api-consumption-python/blob/main/face-consumption.py
vamos al apartado codigo de pyton explicado
le damos en raw
copiamos y pegamos el contenido en el notebook
vamos a portal.azure.com
buscamos face api
creamos una
añadimos lo que nos pida
plan de tarifa gratis
creamos
vamos al recurso
vamos a claves y punto de conexion
copiamos la clave 1 y la ponemos donde dice “suscription key” en el codigo
copiamos el link y lo ponemos donde dice “face api url” en el codigo
buscamos una imagen y copiamos la direccion de imagen
y la pegamos donde se nos indica en el codigo

Practica 19: Custom Vision 
vamos a https://www.customvision.ai/
iniciamos sesion
le damos en new proyect
le ponemos nombre, descripción y recurso
en recurso le ponemos nombre, suscripcion, grupo de recursos
en kind ponemos Cognitive Services
la region que sea
pricing tier el gratis
lo creamos
seleccionamos el recurso
le ponemos clasification
le ponemos multiclass
le ponemos general A2
lo creamos

descargamos imagenes de lo que sea como galaxias
añadimos las imagenes al proyecto
añadimos un tag de lo que es
el tag negativo es para esto no
le damos a train
quick training
le damos train

le damos a quick test
ponemos imagenes que queremos que la ia analice
listo entrenaste una IA 

Practica 20: chat bot
vamos a qnamaker.com
le damos a create a knowledge base
le damos a create a qna service
lo creamos
le damos a refresh
le ponemos la suscripcion
ponemos el azure qna service
el lenguaje en español

le ponemos nombre
en chit-chat le ponemos none
lo creamos
en el knowledge base
creamos pares de preguntas y respuestas
le damos en save and train
le damos en test y ya estaria
le damos en publish y publish
el http lo podemos poner donde queramos
le damos en create bot
rellenamos todo y dejamos todo igual
plan de tarifa free
node.js
lo creas
nos vamos al recurso
vamos al apartado canales

Practica 21:  IoT hub
vamos a portal.azure.com
buscamos Centro IoT
vamos a un simulador de una raspberry pi https://azure-samples.github.io/raspberry-pi-web-simulator/#GetStarted
creamos un centro de IoT
llenamos lo que nos pide y lo creamos
vamos al recurso
vamos al apartado dispositivos
le damos a agregar dispositivo
en id ponemos sensorTemperatura
guardamos
le damos click e id del dispositivo
copiamos la cadena de conexion principal
vamos al simulador y donde dice your IoT hub device connection string lo pegamos

practica 22: sentinel-Log analytics
Vamos a portal.azure.com
buscamos sentinel
creamos uno
creamos un area de trabajo de log analytics
colocamos los datos que nos pide
lo creamos
seleccionamos el area de trabajo de log analytics
lo agregamos al sentinel
vamos al apartado libros-hacen el match entre muchos datos para analizarlos
en el apartado MITRE ATT CK son posibles ataques
en inteligencia sobre amenazas analiza nuestros datos

practica 23: Azure key vault 
Vamos a portal.azure.com
buscamos key vault
creamos uno
rellenamos los datos
en directiva de acceso habilitamos todo
revisamos y creamos
vamos al apartado claves
podemos crear una clave 
en secretos podemos guardar nuestrar contraseñas o certificados.

practica 24: grupos de seguridad
Vamos a portal.azure.com
creamos 1 maquina virtual-windows 10 pro
en redes en grupo de seguridad le ponemos ninguno
en administracion le deshabilitamos el diagnostico de arranque
lo creamos

vamos al apartado de redes
a reglas de puerto de entrada

buscamos grupos de seguridad de red
creamos uno
llenamos los datos
lo creamos

vamos al recurso
vamos a interfaces de red
y damos en asociar
ponemos la maquina

en reglas de seguridad de entrada agregamos una 
origen any
destino any
servicio custom
intervalos origen *
intervalos destino 3389
protocolo TCP
accion permitir
prioridad 300
nombre permitir
la agregamos

vamos a reglas de salida
agregamos una
origen any
intervalos origen *
destino service tag
etiqueta internet
servicio custom
intervalos destino *
protocolo TCP
accion denegar
prioridad 400
nombre nointernet
agregamos

Practica 25: gobernanza-azure policy-directivas
Vamos a portal.azure.com
buscamos directiva
vamos a definiciones
definicion de directiva
ubicacion en tu suscripción
nombre regla de ubicación
descripcion no se pueden crear recursos fuera de continente americano
guardamos
le damos a asignar a un grupo de recursos o algo

vamos a asignar directivas
asignamos una
a un grupo de recursos
no exclusiones
definicion buscamos ubicaciones permitidas
vamos a parametros
buscamos las ubicaciones permitidas y las seleccionamos
creamos
ahora si intentas crear recursos fuera del continente americano no te dejara