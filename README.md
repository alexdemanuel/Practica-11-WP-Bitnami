# Practica-11-WP-Bitnami


# 1. Crearmos la maquina en amazon con ubuntu
  - Creamos una nueva instancia
  - Seleccionamos la AMI para instalar el sistema
	- Seleccionamos el tipo de instancia
	- Configuramos la instancia (red, ip...)
	- Le asignamos una unidad de almacenamiento y su capacidad
	- TAGS: palabras clave que ayudan a encontrar la maquina
	- Reglas de seguridad: agragamos SSH ,HTTP y HTTPS para que se abran esos puertos y podamos acceder a tanto la maquina        como la pagina web
	- Creamos un certificado para poder acceder la maquina via SSH remotamente
  - Accedemos por consola a la carpeta donde se encuentra el certificado
	- Le cambiamos los permisos al certificado con: 
  
 ```bash
  chmod +x nombre-certificado.pen
```
  - Conectamos a la maquina poniendo en consola:  

```bash
  ssh -i "nombre-certificado.pem" usuario@DNS-publico-de-la-maquina
		  Ejemplo:
            		ssh -i "ubuntu-18.04.pem" ubuntu@ec2-18-212-164-248.compute-1.amazonaws.com
  ``` 

# 2 Descargamos el CMS(wordpress) 
```bash
	wget https://bitnami.com/redirect/to/347002/bitnami-wordpress-4.9.8-2-linux-x64-installer.run
``` 
# 3 le cambiamos los permisos
```bash
		chmod +x bitnami-wordpress-4.9.8-2-linux-x64-installer.run
``` 
# 4 comenzamos la instalacion
```bash
		sudo ./bitnami-wordpress-4.9.8-2-linux-x64-installer.run
```  
  
- Utilidades extras
- Seleccionamos la carpeta donde la vamos a instalar
-	Creamos el usuario de administrador (nombre,correo,usuario y contraseña)


  - Le ponemos un nombre a la pagina
	- Le podemos configurar el soporte de correo (en este caso no)
	- Comienza a instalarse
	- Lanzamos wordpress
  
  # 5 Conectar a Wordpress
  - Ponemos la ipv4 publica que nos asignan amazon y accederemos a la pagina
  -Para acceder al panel de control de wordpress ponemos: http://ip-servidor/wp-admin y nos logueamos con las credenciales      del usuario creado en la instalación de wordpress
  
