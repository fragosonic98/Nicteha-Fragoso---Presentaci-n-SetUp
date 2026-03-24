### Bitácora de Sesión: Práctica de Comandos Git y Linux
Fecha: 23 de marzo de 2026
Duración aproximada: 30 minutos
Objetivo: Practicar comandos fundamentales de Linux y Git, desde la clonación de un repositorio hasta la realización de un push con cambios, documentando el proceso y los obstáculos encontrados.

## Ruta de Arranque (7 Pasos)
#Paso 1 — Ubícate: Abrí Git Bash y ejecuté pwd para confirmar mi ubicación actual. Luego usé ls -lah para listar todos los archivos en el directorio, incluyendo los ocultos, y ver los permisos de los archivos. Esto me dio un punto de partida claro.

<img width="941" height="443" alt="23 pwd ls -lah" src="https://github.com/user-attachments/assets/609791bc-2bb4-42be-ab27-aa7275f57d4e" />


#Paso 2 — Clona el proyecto: Navegué a la carpeta donde quería guardar el proyecto localmente y ejecuté el comando git clone git@github.com:fragosonic98/Nicteha-Fragoso---Presentaci-n-SetUp.git. Este comando descargó una copia completa del repositorio remoto a mi equipo.

<img width="718" height="447" alt="git clone succeed" src="https://github.com/user-attachments/assets/8d22a3f1-67db-44b7-a2d7-8332cb8a5292" />


#Paso 3 — Entra a la carpeta: Usé cd Nicteha-Fragoso---Presentaci-n-SetUp/ para ingresar al directorio que acababa de clonar. Verifiqué que estaba dentro con pwd y listé su contenido con ls -lah.

<img width="931" height="447" alt="10 cd directory" src="https://github.com/user-attachments/assets/895a8709-a16b-49ca-9d28-ad179874d2c4" />

#Paso 4 — Lee o crea el README: El repositorio ya tenía un archivo README.md. Lo revisé con cat README.md para ver su contenido. Mi objetivo era modificarlo, no crearlo de nuevo.

#Paso 5 — Haz un cambio pequeño y documentado: Inicialmente, cometí un error de interpretación. Pensé que debía crear un archivo nuevo (hello.txt) con mi usuario y color favorito. Sin embargo, después de leer mejor las instrucciones, entendí que la modificación debía hacerse directamente en el README.md. Corregí mi error y abrí el archivo README.md con nano README.md para agregar la información solicitada.

<img width="942" height="446" alt="25 nano readme" src="https://github.com/user-attachments/assets/56d9097c-50ef-4f2f-8c4e-a3f9ddb789f4" />

<img width="942" height="447" alt="26 update readme" src="https://github.com/user-attachments/assets/21c0b613-7bb0-4820-bab4-edc615e9a196" />



#Paso 6 — Guarda el cambio: Después de editar el README.md, ejecuté git status para ver los cambios pendientes. Luego, preparé los cambios para el commit con git add README.md y los confirmé localmente con un mensaje descriptivo: git commit -m "Updated README.md with username and favorite color". En el proceso, también utilicé git rm hello.txt para eliminar el archivo que había creado por error y git add . para incluir esa eliminación en el commit final.

<img width="936" height="447" alt="30 git add comm and push" src="https://github.com/user-attachments/assets/061af0ec-2c65-459d-9ac8-3053b132dd71" />


#Paso 7 — Sube el cambio: Finalmente, subí los cambios a la rama remota con git push origin nic/hello. Luego verifiqué en la página de GitHub que el commit y los cambios en el README.md eran visibles en mi rama nic/hello.

## Comandos Clave y su Explicación
git clone <url-del-repositorio>: Este comando fue el punto de partida. Sirve para descargar una copia exacta de un repositorio remoto (en este caso, desde GitHub) a mi computadora local, creando una carpeta con todo el historial del proyecto.

git checkout -B <nombre-rama>: Utilicé este comando para crear una nueva rama llamada nic/hello y cambiarme a ella de inmediato. La -B fuerza la creación de la rama, sobrescribiéndola si ya existía, lo cual fue útil para asegurar un punto de partida limpio.

git commit -am "<mensaje>": Este comando fue un atajo muy práctico. La bandera -a (o --all) le indica a Git que incluya automáticamente en el commit todos los archivos que ya estaban siendo rastreados (tracked) y que han sido modificados. La -m permite añadir el mensaje del commit directamente en la línea de comandos.

git rm <archivo>: Usé este comando para eliminar el archivo hello.txt que había creado por error. Lo importante es que git rm no solo borra el archivo del sistema de archivos, sino que también registra esta eliminación en el área de preparación (staging area), preparándola para el próximo commit.

## Problemas Encontrados y Soluciones
Error al cambiar de directorio (cd con "too many arguments"):

Problema: Intenté navegar a una ruta que contenía espacios en los nombres de las carpetas usando cd D:\Users\bonip\Videos\Grabaciones de pantalla\CSU - Comandos github. El terminal interpretó el espacio después de "CSU" como un argumento adicional, lanzando el error bash: cd: too many arguments.

<img width="931" height="447" alt="10 cd directory" src="https://github.com/user-attachments/assets/abcf6148-9892-492f-8012-84646522dd18" />


Solución: En lugar de escribir la ruta manualmente, abrí la carpeta de destino en el explorador de archivos de Windows, hice clic derecho y seleccioné "Open Git Bash here". Esto abrió la terminal directamente en la ubicación correcta, evitando el problema de los espacios.

<img width="358" height="447" alt="7open git bash here" src="https://github.com/user-attachments/assets/a8424890-8b0b-4c89-8583-69e8a6ae9cdb" />


Error al crear la rama (git checkout -B nic/hello /usa tu propio nombre con error "outside repository"):

Problema: Al intentar crear la nueva rama, copié el comando de ejemplo que incluía comentarios o texto de ayuda (/usa tu propio nombre). Git interpretó esa parte como una ruta de archivo adicional, generando el error fatal: '/usa': '/usa' is outside repository....

Solución: Identifiqué el error, eliminé el texto extraño y volví a ejecutar el comando correctamente: git checkout -B nic/hello. Esto creó la rama sin problemas.

Error de Interpretación de la Instrucción (Archivo vs. README):

Problema: Al principio, malinterpreté la tarea. Creé un nuevo archivo hello.txt con touch y lo edité con nano, en lugar de modificar el README.md que ya existía.

Solución: Me di cuenta del error al leer las instrucciones nuevamente. Corregí la situación editando el README.md con nano README.md para agregar la información correcta. Luego, para mantener el historial limpio, usé git rm hello.txt para eliminar el archivo no deseado y, finalmente, hice un nuevo commit que incluía tanto la modificación al README.md como la eliminación de hello.txt.

<img width="937" height="296" alt="28 git rm" src="https://github.com/user-attachments/assets/e52bb637-64b7-4776-b312-f183845cbb35" />


## Resultado Final (Git Log)
Al finalizar, ejecuté git log --oneline para ver un resumen del historial de commits en mi rama. El resultado mostró los dos commits que realicé, confirmando el proceso:

bash
f68fed5 (HEAD -> nic/hello, origin/nic/hello) Updated README.md with username and favorite color
cc98b55 Creates a text file with username and favorite color
6b3b625 (origin/main, origin/HEAD, main) Create README.md
El primer commit (cc98b55) fue mi intento inicial de crear el archivo de texto. El segundo commit (f68fed5) refleja la corrección final, donde actualicé el README.md y eliminé el archivo innecesario, dejando la rama nic/hello lista y con el cambio correcto documentado y subido a GitHub.
