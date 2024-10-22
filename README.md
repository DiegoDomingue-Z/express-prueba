# EXPRESS 
* Que es ?

Express permite crear servidores en Node.js, que pueden servir tanto aplicaciones web (con HTML dinámico) como APIs para que el frontend consuma datos.

La combinación de Express con otros frameworks de frontend permite construir aplicaciones completas y funcionales, donde Express maneja el backend y el frontend puede ser gestionado por tecnologías específicas para la interfaz de usuario.

* Solicitudes 

Solicitud HTTP: El cliente (por ejemplo, un navegador) envía una solicitud HTTP al servidor.

Conversión a formato binario: Esta solicitud se convierte a formato binario para su transmisión a través de la red.

Escuchar en el puerto: El servidor está configurado para escuchar en un puerto específico (por ejemplo, el puerto 3000).

Recibe la solicitud: El servidor recibe la solicitud a través del protocolo HTTP.

Procesar la solicitud: El servidor procesa la solicitud, que puede incluir el acceso a bases de datos o la ejecución de lógica de negocio.

Crear la respuesta: Una vez procesada la solicitud, el servidor crea una respuesta adecuada (por ejemplo, una página web o un archivo).

Convertir respuesta a formato binario: La respuesta también se convierte a formato binario para su envío.

Enviar respuesta HTTP: El servidor envía la respuesta HTTP de vuelta al cliente.

Almacenar en buffer (del cliente): La respuesta se almacena temporalmente en un buffer en la máquina del cliente.

Procesar el buffer: El cliente procesa los datos del buffer y los convierte en un formato comprensible, como texto o elementos visuales en una página web.

# Ciclo de Vida de una Solicitud en Express

Recepción de la Solicitud: Cuando un cliente hace una solicitud al servidor (por ejemplo, al acceder a una URL), Express comienza a procesar esa solicitud.

Ejecución de Middleware: Express ejecuta todos los middleware que se han configurado, en el orden en que fueron añadidos. Esto incluye middleware para servir archivos estáticos, para parsear cuerpos de solicitudes, y cualquier middleware que hayas definido.

* Respuesta del Middleware:

Si un middleware maneja la respuesta (es decir, envía una respuesta al cliente usando res.send(), res.json(), res.end(), etc.), entonces el ciclo de vida de esa solicitud termina ahí para ese middleware en particular. El flujo no continuará a los siguientes middleware o rutas.
Si un middleware no envía una respuesta (por ejemplo, si solo realiza alguna lógica o procesamiento), debe llamar a next() para pasar el control al siguiente middleware en la cadena.


# Handlebars como si fuera una máquina de hacer tarjetas personalizadas.

Tienes una plantilla de tarjeta (esto sería tu archivo .handlebars), que es un diseño genérico donde dejas espacios en blanco para poner el nombre, el mensaje y otros detalles.
Cuando alguien te pide una tarjeta, tú no creas una nueva desde cero. Simplemente usas la plantilla y la llenas con los detalles que te piden (por ejemplo, el nombre y el mensaje).
Al final, entregas una tarjeta completa y personalizada a la persona que te la pidió. Este proceso de llenar los espacios y entregar la tarjeta es lo que se conoce como renderizar.
En este caso, tu "cliente" es el navegador, y la "tarjeta" es la página web que ve el usuario.

* ¿Qué es renderizar?
Renderizar es simplemente el proceso de generar algo visible o comprensible para el usuario a partir de una plantilla y datos. En términos más simples, es convertir el código y los datos en algo que el usuario pueda ver (como una página web con texto, imágenes, etc.).

# como renderizar algo 
la idea de Handlebars es que tengamos separado lo que es la vista el modelo y el controlador 



# app.use()
Se utiliza para registrar middleware. Un middleware es una función que se ejecuta en el proceso de una solicitud, antes de enviar una respuesta. Se usa para hacer cosas como manejo de errores, autenticar usuarios, registrar logs, etc.
Por ejemplo, si pones un middleware para todas las rutas:

# app.get()
Se usa para definir una ruta (o endpoint) que responde a solicitudes HTTP GET. Es decir, cuando alguien accede a una URL específica en tu aplicación, este método determina qué hacer.

# app.set()
app.set() es para configurar opciones o ajustes en la aplicación. Estos son ajustes globales que afectan el comportamiento de Express.

Por ejemplo, si quieres configurar el motor de plantillas (como Handlebars) o establecer un valor de configuración específico.

* ¿COMO FUNCIONA LA RENDERIZACION CON LOS ARCHIVOS STATICOS EN UNA
* CARPETA Y OTRA LAS VITAS O ARCHIVOS HTML O HBS

Los Señores:

Señor del Agua: Representa los archivos estáticos (CSS, imágenes, etc.). Él proporciona los "ingredientes" que embellecen y dan estilo a tu aplicación.
Señor del Limón: Representa las vistas (archivos .hbs). Él agrega el contenido y la estructura a la respuesta que se le envía al cliente.
El Recipiente (Servidor):

Tú eres el recipiente (el servidor), que toma todos los ingredientes y los mezcla. Eres responsable de juntar todos los elementos para crear algo que sea útil y presentable.
La Petición (Corredor):

Cuando el corredor hace una solicitud de agua (hace una petición HTTP), tú como servidor, recoges los ingredientes de los dos señores: el agua y el limón.
Entonces, mezclas el agua (los archivos estáticos) y el limón (las vistas) en el recipiente (el servidor).
La Entrega (Respuesta al Cliente):

Al final, sirves la mezcla (la respuesta) al corredor, que en este caso sería el cliente (el navegador del usuario). Él recibe el "agua de limón", que representa la respuesta HTML completa.


# npm  i dotenv   

 al declarar variables en un archivo .env, es como si estuvieras pasando directamente esas variables al entorno de ejecución de tu aplicación. Cuando utilizas dotenv, esas configuraciones se cargan en process.env, lo que te permite acceder a ellas desde cualquier parte de tu código sin tener que "hardcodearlas" (escribirlas directamente en tu código fuente).

Esto te da mucha flexibilidad, ya que puedes cambiar el valor de esas variables sin tocar el código. Por ejemplo, si mañana cambias la base de datos o la clave de una API, solo necesitas modificar el archivo .env, y tu aplicación seguirá funcionando correctamente sin necesidad de modificar el código en sí.

En resumen:

Archivo .env: Guarda las variables de entorno (configuraciones sensibles o específicas del entorno).
Dotenv: Carga esas variables en process.env.
process.env: Contiene las variables que la aplicación usará mientras se ejecuta.

* La ventaja principal de usar dotenv es que mantienes la información sensible y las configuraciones separadas del código. Esto facilita cambiar configuraciones sin modificar el código y mejora la seguridad al no exponer datos importantes como claves API, contraseñas o configuraciones de producción en el código fuente.

* Ejecutamos el método .config(): Esto busca automáticamente un archivo llamado .env en el directorio raíz de tu proyecto, lo lee, y carga las variables de entorno definidas en ese archivo en process.env. Así, esas variables estarán disponibles en toda tu aplicación.


# "start": "node app.js"
se coloca en el package.jon para indicarle a la mayoria de los hosting cual es el comando para iniciar la aplicacion 

* para probarlo coloca npm start 

# environments
Los environments o entornos en programación son configuraciones que definen cómo debe ejecutarse una aplicación en diferentes contextos o situaciones. Dependiendo del entorno en el que se esté ejecutando la aplicación, ciertos comportamientos o configuraciones pueden cambiar.


# como funcionan los puertos en los hosting
Analogía:
Imagina que en tu casa (entorno local), decides en qué cuarto trabajar (puerto). Pero si te vas a una oficina compartida (hosting), te asignan un escritorio específico (puerto) para evitar que ocupes el espacio de otro.

