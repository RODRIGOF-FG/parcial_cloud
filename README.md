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
```cmd
CREATE USER 'admin'@'%' IDENTIFIED BY '*123456';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'%' WITH GRANT OPTION;
```

<br>

![img_1](recursos/1.10.png)

<br>


# AA 

<br>

![img_1](recursos/1.11.png)

<br>


# AA 

<br>

![img_1](recursos/1.12.png)

<br>


# Paso 2 - Configuracion instancia - Servidor web tomcat 10 

<br>

![img_1](recursos/2.png)

<br>


# bbb

<br>

![img_1](recursos/2.1.png)

<br>
# bbb

<br>

![img_1](recursos/2.2.png)

<br>
# bbb

<br>

![img_1](recursos/2.3.png)

<br>


# bbb

<br>

![img_1](recursos/2.4.png)

<br>

# bbb

<br>

![img_1](recursos/2.5.png)

<br>

# bbb

<br>

![img_1](recursos/2.6.png)

<br>

# bbb

<br>

![img_1](recursos/2.7.png)

<br>
# bbb

<br>

![img_1](recursos/2-8.png)

<br>



