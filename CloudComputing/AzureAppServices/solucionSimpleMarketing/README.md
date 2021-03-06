# Solución Simple de Marketing en Azure
En este tutorial aprenderemos a implementar una solución de CMS Wordpress agregandole componentes como de CDN y Redis Cache.

El diagrama de arquitectura es el siguiente:

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/diagrama.PNG" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/diagrama.PNG" width="649" height="338" alt="Diagrama de Arquitectura de Solución" />

Los componentes dentro de Azure que utilizaremos para esta solución son los siguientes:

* Wordpress - Azure App Service
* Cuenta de Storage
* CDN de Microsoft
* Redis de Microsoft

# Pasos para implementarlo
## Creación de Wordpress dentro de Azure
1.  Ingresamos al Portal de azure https://portal.azure.com
<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/portal.PNG" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/diagrama.PNG" width="649" height="338" alt="Portal de Azure" />
2.  Creamos un nuevo grupo de recurso
<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionGrupoRecurso.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionGrupoRecurso.png" width="649" height="338" alt="Creacion grupo de recursos" />
3.  Dentro del grupo de recurso creamos un nuevo Wordpress

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress1.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress1.png" width="649" height="338" alt="Creacion grupo de recursos" />

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress2.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress2.png" width="649" height="338" alt="Creacion grupo de recursos" />

Al seleccionar la base de datos seleccionamos Azure MySQL
<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress3.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress3.png" width="649" height="338" alt="Creacion grupo de recursos" />

Esperamos la implementación del Wordpress
<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress4.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress4.png" width="649" height="338" alt="Creacion grupo de recursos" />


4.  Una vez está el deployment listo procedemos a finalizar la instalación del Wordpress

En el portal de Azure abrimos el nuevo Wordpress

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress5.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress5.png" width="649" height="338" alt="Creacion grupo de recursos" />

Abrimos la URL nueva 

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress6.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress6.png" width="649" height="338" alt="Creacion grupo de recursos" />

Creamos el titulo del wordpress, elegimos un nombre de usuario y contraseña. Muy importante, debemos guardar estos valores para más adelante. 

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress7.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress7.png" width="649" height="338" alt="Creacion grupo de recursos" />

Luego wordpress nos mostrará una confirmación de instalación exitosa

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress8.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress8.png" width="649" height="338" alt="Creacion grupo de recursos" />


5.  Luego ingresamos al dashboard de wordpress con nuestro usuario y contraseña y hemos completado este paso!

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress9.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress9.png" width="649" height="338" alt="Creacion grupo de recursos" />


<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress10.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionWordpress10.png" width="649" height="338" alt="Creacion grupo de recursos" />


## Creación de Cuenta de Storage
1.  En el grupo de recurso que creamos elegimos agregar

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage1.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage1" width="649" height="338" alt="Creacion Storage 1" />

2.  Buscamos "Storage Account"

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage2.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage2.png" width="649" height="338" alt="Creacion Storage 2" />

3.  Le ponemos un nombre y usamos los parametros por defecto

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage3.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage3.png" width="649" height="338" alt="Creacion Storage 3" />

4.  Creamos la Cuenta y abrimos la pestaña de claves de acceso

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage4.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage4.png" width="649" height="338" alt="Creacion Storage 4" />

5. Anotamos y guardamos el nombre de la cuenta y la clave primaria

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage5.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionStorage5.png" width="649" height="338" alt="Creacion Storage 5" />

## Creación de Redis 
1.  Ingresamos al grupo de recurso y seleccionamos agregar

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis1.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis1.png" width="649" height="338" alt="Creacion Redis 1" />

2.  Buscamos Redis y seleccionamos la opción de microsoft, ingresamos nombre y activamos el puerto

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis2.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis2.png" width="649" height="338" alt="Creacion Redis 1" />

4.  Creamos la cuenta de Redis

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis3.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis3.png" width="649" height="338" alt="Creacion Redis 1" />

5.  Abrimos el Redis y buscamos las llaves de acceso

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis4.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis4.png" width="649" height="338" alt="Creacion Redis 4" />

6.  Copiamos las llaves de acceso en nuestro notepad

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis5.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionRedis5.png" width="649" height="338" alt="Creacion Redis 5" />

## Creación de CDN
1.  Abrimos nuestro grupo de recurso y presionamos agregar

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN1.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN1.png" width="649" height="338" alt="Creacion CDN 1" />

2.  Buscamos CDN y elegimos la opción de Microsoft, luego especificamos nombre de cdn y parametros

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN2.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN2.png" width="649" height="338" alt="Creacion CDN 2" />

4.  Creamos la cuenta y la abrimos

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN3.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN3.png" width="649" height="338" alt="Creacion CDN 3" />

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN4.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN4.png" width="649" height="338" alt="Creacion CDN 4" />

5. Ahora procedemos a crear un nuevo endpoint conectado, le definimos un nombre y en tipo de origen escogemos "storage account",  luego en nombre del host, escogemos la cuenta de storage que creamos anteriormente.

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN5.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN5.png" width="649" height="338" alt="Creacion CDN 5" />

6. Copiamos la url de nuestro CDN en nuestro notepad:

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN6.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN6.png" width="649" height="338" alt="Creacion CDN 6" />

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN7.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/creacionCDN7.png" width="649" height="338" alt="Creacion CDN 7" />



## Configuración de CDN con Wordpress
1.  Ahora volvemos al dashboard de nuestro wordpress, con nuestro usuario y contraseña

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp1.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp1.png" width="649" height="338" alt="configuracionWp1" />

2.  Seleccionamos plugins

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp3.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp3.png" width="649" height="338" alt="configuracionWp3" />

3. Agregamos un nuevo plugin y buscamos "Azure" e instalamos el siguiente plugin:

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp4.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp4.png" width="649" height="338" alt="configuracionWp4" />


4. Una vez seleccionado preciona activar:

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp5.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp5.png" width="649" height="338" alt="configuracionWp5" />

5. Una vez instalado, nos vamos a las opciones del plugin:

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp6.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp6.png" width="649" height="338" alt="configuracionWp6" />

6. Y agregamos los parametros que obtuvimos de nuestro storage y nuestro cdn:

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp7.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp7.png" width="649" height="338" alt="configuracionWp7" />

7. Finalmente le damos aceptar y hemos terminado!

<img src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp8.png" data-canonical-src="https://raw.githubusercontent.com/feranto/azureDemos/master/CloudComputing/AzureAppServices/solucionSimpleMarketing/imagenes/configuracionWp8.png" width="649" height="338" alt="configuracionWp8" />


