# parcial_cloud

**Despliegue .war**

# Paso 1 - Configuracion de instancia para la Base de datos 

- Actualizar repositorios de la instancia:
<br>

```cmd
sudo su apt update -y

```

<br>


<br>

![img_1](recursos/1.png)

<br>


- Instalar MySql en Ubuntu:

```cmd
apt install mysql-server

```
<br>

![img_1](recursos/1.1.png)

<br>


- Verificar estado de Mysql

```cmd
systemctl status mysql 

```
<br>

![img_1](recursos/1.2.png)

<br>

- Ingresar a Mysql como root

```cmd
mysql -u root -p 

```

<br>

![img_1](recursos/1.3.png)

<br>


- Dentro de mysql debemos de cambiar la contraseña de root de la siguiente manera: 

```cmd
FULL PRIVILEGES;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '*123456';
exit;

``` 

<br>

![img_1](recursos/1.4.png)


![img_1](recursos/1.5.png)

<br>
- Restablecer MySql en Ubuntu:

```cmd
systemctl restart mysql

```

<br>

![img_1](recursos/1.6.png)

<br>


- Ingresar con las nuevas credenciales a mysql

<br>


```cmd
mysql -u root -p 

```


<br>

![img_1](recursos/1.7.png)


<br>


- Crear base de datos y tabla


```cmd
CREATE DATABASE vettrack;
USE vettrack;
CREATE TABLE mascotas (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre_mascota VARCHAR(100) NOT NULL,
    nombre_dueno VARCHAR(100) NOT NULL
);
```

<br>

![img_1](recursos/1.8.png)


![img_1](recursos/1.9.png)

<br>
- Crear nuevo usuario para conexion remota

<br >


```cmd
CREATE USER 'admin'@'%' IDENTIFIED BY '*123456';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'%' WITH GRANT OPTION;
```

<br>

![img_1](recursos/1.10.png)

<br>


<br>
- Habilitar que cualquier dispositivo se pueda conectar a mi bd



<br>

![img_1](recursos/1.11.png)

<br>


<br>
- reinicair servicio mysql


<br>

![img_1](recursos/1.12.png)

<br>


# Paso 2 - Configuracion instancia - Servidor web tomcat 10 


<br>
- Instalar jdk 

<br >


```cmd
apt install jdk-default -y
```
<br>

![img_1](recursos/2.png)

<br>


<br>
- Instalar tomcat10 

<br >


```cmd
apt install tomcat10 tomcat10-admin
```
<br>

<br>

![img_1](recursos/2.1.png)

<br>
<br>
- Configurar usuario



<br>

![img_1](recursos/2.2.png)

<br>
<br>
- Ingresar por puerto 8080



<br>

![img_1](recursos/2.3.png)

<br>


<br>
- Ingresar credenciales




<br>

![img_1](recursos/2.4.png)

<br>

<br>
- Panel de admin




<br>

![img_1](recursos/2.5.png)




![img_1](recursos/2.6.png)

<br>

<br>
- Seleccionar archivo .war y desplegar




<br>

![img_1](recursos/2.7.png)

<br>
<br>
- Despliegue exitoso en: http://18.116.8.96:8080/VetTrack/




<br>

![img_1](recursos/2-8.png)

<br>



