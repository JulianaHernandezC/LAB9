# LAB9
## Pre-Laboratorio
- Desde la terminal de Ubuntu ejecute este comando para actualizar el sistema operativo : __sudo apt update && sudo apt upgrade__

<img width="1440" alt="Captura de pantalla 2024-05-21 a la(s) 12 04 43 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/4aafcb65-9324-43c4-b803-f7b14ec77787">

- Para instalar los paquetes de cliente correspondientes MySQL y PostgreSQL : ingrese los comandos: __sudo apt install mysql-client__ y __sudo apt install postgresql-client__

## Laboratorio
1) Instalacion del servidor de MySQL con el comando __sudo apt install mysql-server__
2) Crear una tabla de ejemplo en MySQL:

3) Iniciar secion de cliente de MySQL con el comando __mysql -u root -p__
<img width="1440" alt="Captura de pantalla 2024-05-21 a la(s) 12 24 35 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/efbb53ec-5350-4490-a97b-4abb805867dc">

  
4) Para crear una base de datos de ejemplo ejecutamos el comando : __CREATE DATABASE nombre;__ en mi caso : __CREATE DATABASE ejemplo;__
<img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 41 45 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/4bbe065a-00db-43cb-b419-7c703166b4b1">

5)Creamos un usuario con el comando __CREATE USER 'username'@'%' IDENTIFIED BY 'password';__ el nombre de usuario que elegí fue __lab9__ .

6)Le doy privilegio a ese usuario para que administre la base de datos. Comando: __GRANT ALL PRIVILEGES ON 'nombreBaseDatos'.* TO 'username'@'%';__
<img width="1415" alt="Captura de pantalla 2024-05-27 a la(s) 2 24 49 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/c7e00c5f-2ba0-4214-9643-55616b9e0a68">


7) Para seleccionar la base de datos recien creada se utiliza el comando __USE nombredeDatabase;__ en mi caso __USE ejemplo;__
<img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 42 05 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/dd09b85b-1f5e-4d32-8bbd-b4a48c10423e">


8) Crear una tabla con datos de ejemplo: __CREATE TABLE usuarios (
id INT PRIMARY KEY, nombre VARCHAR(50), email VARCHAR(100));__
<img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 42 27 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/3e708637-f874-4925-ba59-0d7c090488ea">


9) Una vez ya creada la tabla se le pueden insertar datos con el comando __INSERT INTO nombreTabla__ ejemplo : __INSERT INTO usuarios (id, nombre, email)
VALUES (1, 'Juan', 'juan@example.com'),
(2, 'María', 'maria@example.com'),
(3, 'Pedro', 'pedro@example.com');__


<img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 42 47 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/23f2d5a5-0c8f-4cc5-81d9-0270159d24fc">


10) Para verificar que la tabla se haya creado correctamente se utiliza el comando : __SELECT * FROM nombreTabla;__ en nuestro caso __SELECT * FROM usuarios;__
<img width="779" alt="Captura de pantalla 2024-05-21 a la(s) 12 44 50 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/2ffc1e0a-0e1d-49e2-ac13-19c9e02b63a3">

11) Para consultar la tabla de ejemplo iniciamos secion en el cliente de MySQL, seleccionamos la base de datos y verificamos los datos de la tabla. 
<img width="50%" alt="Captura de pantalla 2024-05-21 a la(s) 12 53 30 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/e820f130-c3c3-4e3b-9ecb-931c723a8977">

12) Con el comando __sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf__  entramos en el archivo de configuracion de mysql en la parte de redes para habilitar otros puertos y que no solo se permita el local host. 
13) Editamos el archivo y comentamos con '#' la linea "bind-address = 127.0.0.1" y agregamos "bind-address = 0.0.0.0". Para que de esta forma se acepten conexiones remotas y este servidor escuche de cualquier otro servidor. Es decir, que cualquier persona se pueda conectar a él a traves de cualquier otra red.

<img width="80%" alt="Captura de pantalla 2024-05-27 a la(s) 1 50 40 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/b1dd4aee-0624-4872-a2fd-1edd2dcc1eca">


14) En la configuracion de red de la maquina virtual creamos una entrada al grupo de seguridad para el puerto 3306. 
<img width="60%" alt="Captura de pantalla 2024-05-27 a la(s) 2 30 16 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/8f249b9c-455e-449c-8743-c2f855262b77">

<img width="50%" alt="Captura de pantalla 2024-05-27 a la(s) 2 33 38 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/c098e2a6-59ae-4bdb-95e1-5d17c4436eb8">

15) Luego en el MySQL Workbench hacemos la primer prueba de conexion. Para eso completamos algunos datos como la IP publica de la VM, el nombre de usuario y el nombre de la base de datos. Ademas, le creamos un nombre a la conexion, en mi caso le puse "Laboratorio09".

<img width="50%" alt="Captura de pantalla 2024-05-27 a la(s) 2 37 24 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/3ca95fcf-57db-4ff1-b148-a3d3ba3a1076">

Hacemos la prueba de conexion y nos pedira la contraseña del usuario:

<img width="70%" alt="Captura de pantalla 2024-05-27 a la(s) 2 42 27 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/62f877f5-5488-4f73-927a-65135d0087b6">

<img width="372" alt="Captura de pantalla 2024-05-27 a la(s) 2 42 51 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/9061828d-46fe-4e0d-bee1-1c2fb23f25d3">


16) Por ultimo, podemos observar la tabla creada en Mysql desde el workbench.
<img width="70%" alt="Captura de pantalla 2024-05-27 a la(s) 3 46 10 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/bffbab28-8e52-46f1-86f4-bc20b7a33bbd">

17) Cree otra tabla llamada "estudiantes".
<img width="396" alt="Captura de pantalla 2024-05-27 a la(s) 3 57 52 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/a64166a5-7788-4cf6-b5f9-8736b28c8022">
<img width="70%" alt="Captura de pantalla 2024-05-27 a la(s) 3 59 21 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/16c01b49-1ca0-49f0-9cf6-bdcd5ccf412e">


