[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-f059dc9a6f8d3a56e377f745f24479a46679e63a5d9fe6f495e02850cd0d8118.svg)](https://classroom.github.com/online_ide?assignment_repo_id=5971833&assignment_repo_type=AssignmentRepo)
# tarea2-peps

## Pascual Barrer Ferrer

## Comandos básicos
---

Para empezar creamos un directorio de trabajo en local para hacer las pruebas e iniciamos git:

![](1_Creación_carpeta_y_git_init.png)

A continuación creamos un archivo de texto y ejecutamos `git status` para ver los cambios respecto al registro que lleva git. Nos muestra un mensaje diciendo que el nuevo archivo todavía no se encuentra en seguimiento. Para remediarlo ejecutamos un `add` y hacemos el primer `commit`. Si volvemos a comprobar el estado de git vemos que ahora todos los cambios están actualizados en git.

![](2_Creación_archivo_con_contenido.png)

Para ir añadiendo cambios, insertamos una línea al archivo y hacemos un `commit -am` para no tener que hacer el `add` y el `commit` por separado (`-a` viene de `add`):

![](3_Otra_línea_al_archivo.png)

Dejando ahora de lado la terminal, vamos a la página oficial de Bitbucket y nos creamos una cuenta. Para facilitar las cosas, utilizamos una cuenta de Google:

![](4_Creación_cuenta_Bitbucket.png)

Al finalizar el proceso de alta de la cuenta nos aparece la siguiente pantalla. Aquí clicamos sobre crear repositorio.

![](5_Creación_repo_Bitbucket.png)

Lo que nos lleva a la siguiente pantalla. Seleccionamos una serie de opciones a nuestro gusto y clicamos en crear repositorio.

![](6_Creación_repo_Bitbucket_2.png)

Una vez creado el repositorio nos aparece una nueva pantalla (similar a las que aparecen en GitHub y GitLab) con todos los comandos que podemos usar para sincronizar nuestro nuevo repositorio remoto con el que tenemos ya creado en local.

![](7_Comandos_para_origin.png)

Antes de ponernos manos a la obra con los comandos necesitamos hacer un paso previo: dar de alta una contraseña para acceder a los repositorios que creemos en Bitbucket. Para ello nos dirigimos a la esquina inferior izquierda de la pantalla y hacemos clic en el icono con nuestro avatar (o iniciales si no hemos elegido uno) y seleccionamos Personal settings.

![](8_Personal_settings.png)

En la nueva pantalla que aparece, clicamos sobre App passwords en la barra lateral y le damos a Create app password. Rellenamos una serie de detalles como la etiqueta (podemos poner lo que queramos) y seleccionamos permisos de lectura y escritura en los repositorios. Copiamos la contraseña que nos aparece y ya tendremos lo necesario para acceder a Bitbucket desde la terminal.

![](8b_Crear_pass.png)

![](9_Crear_pass.png)

Volvemos a la terminal y añadimos el `origin` con el comando que copiamos de la pantalla de bienvenida al nuevo repositorio. Hacemos `push` e introducimos la contraseña que hemos copiado en el paso anterior.

![](10_origin_y_push.png)

Si comprobamos que el `push` ha ido bien recargando la página donde tenemos el repositorio remoto vemos que, efectivamente, nuestros cambios se ven reflejados:

![](11_Repo_bitbucket.png)

Añadamos otra línea a nuestro archivo para poder ver como revertir un cambio en git. Si después del cambio no hemos hecho un `add` podemos usar los comandos de la siguiente imagen. Cuando miramos el contenido del archivo vemos que se ha recuperado la versión que tenía guardada git antes del cambio.

![](12_Nueva_línea_y_reset.png)

Ahora vamos a añadir más cambios: recuperamos la segunda línea y añadimos una tercera. Por cada línea hacemos un `commit -a` para que git tenga constancia de todo este historial de versiones:

![](13_Nuevas_líneas_y_commit.png)

Ahora que hemos hecho diversos `commit`, si queremos volver a una versión X podremos hacerlo mediante un `checkout`. Si al escribir `git checkout` pulsamos tabulación la consola nos ofrecerá todo el historial de versiones disponible para que nosotros podamos elegir fácilmente a qué versión queremos regresar.

![](14_Resets_posibles.png)

Elegimos una, por ejemplo, la segunda en la que habíamos añadido sólo la primera línea (identificada por el hash d8682dd), luego miramos el archivo y veremos que, efectivamente, hemos recuperado la versión deseada.

![](15_Checkout_realizado.png)

Que estemos en esta versión ahora no significa que las demás (las posteriores a la actual) hayan desaparecido. Si repetimos la operación de escribir `git checkout` y pulsar tabulación vemos que siguen estando todos los `commit` que hemos hecho.

![](16_Checkouts_posibles.png)

Recuperemos todos los cambios, es decir, volvamos al HEAD, y hagamos `push` para tenerlo todo guardado en remoto.

![](17_Volviendo_HEAD_y_push.png)

Después de hacerlo, hacemos un cambio en remoto para ver cómo funciona el `pull`.

Antes del cambio

![](18_archivo_remoto_sin_tocar.png)

Después del cambio

![](19_archivo_remoto_cambiado.png)

Pulsamos en el botón azul (Commit) para guardar los cambios. Vamos a una terminal y hacemos `pull`.

![](20_pull.png)

Como podemos observar los cambios hechos en remoto se han descargado correctamente a nuestra copia local.
