# LAB9
## Pre-Laboratorio
1) Desde la terminal de Ubuntu ejecute este comando para actualizar el sistema operativo : __sudo apt update && sudo apt upgrade__

<img width="1440" alt="Captura de pantalla 2024-05-21 a la(s) 12 04 43 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/4aafcb65-9324-43c4-b803-f7b14ec77787">

2) Para instalar los paquetes de cliente correspondientes MySQL y PostgreSQL : ingrese los comandos: **sudo apt install mysql-client** y **sudo apt install postgresql-client**

## Laboratorio
1) Instalacion del servidor de MySQL con el comando **sudo apt install mysql-server**
2) Crear una tabla de ejemplo en MySQL:

    1- Iniciar secion de cliente de MySQL con el comando **mysql -u root -p**
  <img width="1440" alt="Captura de pantalla 2024-05-21 a la(s) 12 24 35 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/efbb53ec-5350-4490-a97b-4abb805867dc">
    2- Para crear una base de datos de ejemplo ejecutamos el comando : **CREATE DATABASE ejemplo;**
   <img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 41 45 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/4bbe065a-00db-43cb-b419-7c703166b4b1">

     3- Para seleccionar la base de datos recien creada se utiliza el comando **USE nombredeDatabase;** en nuestro caso **USE ejemplo;**
   <img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 42 05 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/dd09b85b-1f5e-4d32-8bbd-b4a48c10423e">

     4- Crear una tabla con datos de ejemplo: **CREATE TABLE usuarios (
id INT PRIMARY KEY, nombre VARCHAR(50), email VARCHAR(100));**
<img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 42 27 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/3e708637-f874-4925-ba59-0d7c090488ea">

      5- Una vez ya creada la tabla se le pueden insertar datos con el comando **INSERT INTO nombreTabla** ejemplo : **INSERT INTO usuarios (id, nombre, email)
VALUES (1, 'Juan', 'juan@example.com'),
(2, 'María', 'maria@example.com'),
(3, 'Pedro', 'pedro@example.com');**


<img width="1064" alt="Captura de pantalla 2024-05-21 a la(s) 12 42 47 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/23f2d5a5-0c8f-4cc5-81d9-0270159d24fc">

    6- Para verificar que la tabla se haya creado correctamente se utiliza el comando : **SELECT * FROM nombreTabla;** en nuestro caso **SELECT * FROM usuarios;**
  <img width="779" alt="Captura de pantalla 2024-05-21 a la(s) 12 44 50 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/2ffc1e0a-0e1d-49e2-ac13-19c9e02b63a3">

3) Para consultar la tabla de ejemplo iniciamos secion en el cliente de MySQL, seleccionamos la base de datos y verificamos los datos de la tabla. 
   <img width="970" alt="Captura de pantalla 2024-05-21 a la(s) 12 53 30 p  m" src="https://github.com/JulianaHernandezC/LAB9/assets/131790646/e820f130-c3c3-4e3b-9ecb-931c723a8977">


