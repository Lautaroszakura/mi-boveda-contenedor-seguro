# mi-boveda-contenedor-seguro
1. Introduccion
El objetivo de la practica es aplciar conceptos fundam,entales de ciberseguridad relacionados con la gestion de identidades digitales, la proteccion de contraseñas y el cifrado de datos
Para realizar la actividad se utilizan:
- KeePassXC, un gestor de contraseñas que permite almacenar credenciales de forma segura
- Veracrypt, una herramienta que permite crear contenedores cifrados para proteger archivos sensibles

2. Objetivos
* Crear una boveda de contraseñas protegida mediante una contraseña maestra
* Incorporar un archivo lalve como mecanismo adicional de proteccion
* Generar contraseñas robustas y diferentes para distintas cuentas
* Crear un contenedor de 100MB con VeraCrypt
* Comprobar el montaje y desmontaje

3. Desarrllo
3.1. Configuracion de la boveda de contraseñas
En una primera etapa se utiliza KeePassXC para crear una base de datos destinada al almacenamiento seguro de credenciales
Se configurara una contraseña maestra robusta, formada por varias palabras aleatorias, y se incorpora un archivo llave como mecanismo adicional de proteccion

<img width="1600" height="1098" alt="WhatsApp Image 2026-10-28 at 19 28 10" src="https://github.com/user-attachments/assets/74e26265-dbfe-4e6f-93b2-09cef83dc1b7" />


Como palabra para la contraseña robusta se utilizo una frase de una pelicula: "Mi nombre es Maximo Decimo Meridio" la cual de por si tiene bastantes caracteres, y si le sumamos cambiar las  vocales por numeros parecidos y simbolos -,_,@ quedaria lo suficientemente robusta como para no correr peligro

Se crearan tres registros como ejemplo para diferentes cuentas. Para cada registro se generara una contraseña aleatoria de al menos 16 caracteres, incluyendo mayusculas, minusculas, numeros y simbolos

<img width="1600" height="1273" alt="WhatsApp Image 2026-10-28 at 19 29 43" src="https://github.com/user-attachments/assets/7b09b6e4-c5b8-42de-abd3-b18d3d2f5296" />

El uso de contraseñas unicas permite reducir el riesgo de que la filtracion de una credencial comprometa otras cuentas en otros servidores

<img width="1600" height="1173" alt="WhatsApp Image 2026-10-28 at 19 31 34" src="https://github.com/user-attachments/assets/bce4ab4f-f58c-4023-8e29-8172f17372a9" />

Configuracion del archivo llave
Como medida adicional de proteccion, se configura un archivo llave asociado a la base de datos de KeePassXC
El mecanismo requiere disponer tanto de la contraseña maestra como del archivo lalve para desbloquear la boveda
El archivo llave debe conservarse en un lugar seguro y no deberia publicarse en el repositorio

3.2. Creacion del contenedor cifrado
En esta seguda etapa se utilizara Veracrypt parqa crear un contenedor cifrado
Se selecciona la opcion de creacion de un contenedor de archivos cifrado y se configura en un volumen estandar de 100MB
Se mantendran los parametros de cifrado predeterminados y se establecera una contraseña distinta a la utilizada en KeePass
Durante el proceso de creacion, se debera mover el raton aleatoriamente dentro de la ventana, con fin de crear entropia y aleatoriedad
Finalmente se completara el formateo y se verifica que el volumen se haya creado correctamente

Montaje del volumen
Una vez creado el contenedor, se procede a montar desde Veracrypt
Se seleccionara una letra de unidad disponible, se busca el archivo contenedor y se introduce la contraseña correspondiente
Cuando el volumen se monta correctamente, aparece como una unidad disponible en el Explorador de archivos de Windows, lo que permitira acceder a los archivos almacenados dentro del contenedor y trabajar con ellos normalmente mientras el volumen permanezca desbloqueado

Creacion de archivo de aprendizajes
Dentro del volumen montado se crea un archivo llamado aprendizajez.txt
En el se registraran tres conceptos importantes
- Gestion de contraseñas, los gestores permiten almacenar credenciales de forma organizada y protegida, ademas de generar contraseñas robustas y unicas
- Proteccion adicional, Utilizar un archivo llave junto con una contraseña maestra agrega un requisito de acceso a la boveda
- Cifrado de datos, un contenedor cifrado permite proteger la confidencialidad de los archivos almacenados cuando el volumen esta desmontado

Desmontaje del volumen
Una vez finalizada la actividad, se desmonta el volumen desde Veracrypt
Despues de realizar esta accion, la unidad deja de estar disponible como un disco accesible desde el Explorador de archivos, aunque el archivo contenedor continua existiendo en la ubicacion original
