# Repositorio para la prueba de concepto de Vitualhost y Proxy Reverso

En una instancia basada en Amazon Linux, clonar el proyecto actual y ejecutar los siguientes comandos para instalación básica:

`

sudo certbot certonly --standalone

wget https://raw.githubusercontent.com/christpaul01/virtualhost-proxyreverso/master/basico.sh && chmod +x basico.sh && bash basico.sh
 && chmod +x basico.sh && bash basico.sh

sudo cp ~/virtualhost-proxyreverso/configuraciones/app1-app2.conf /etc/httpd/conf.d/
cd /etc/httpd/conf.d
sudo service httpd restart

# comandos utiles
sudo systemctl status httpd
sudo systemctl restart httpd

`



Una vez terminado el script, salga de la terminar y vuelva a conectarse. Validar que los siguientes comandos:

**Comando Java:**

`
java -version
`

![java](imagenes/java.png)

**Comando Nmap:**

`
nmap localhost
`

![nmap](imagenes/nmap.png)

**Comando Free:**

`
free 
`

![free](imagenes/free.png)

En este punto tenemos disponible todas las herramientas necesarias instaladas.

**Configurando Virtualhost**

Es necesario contar con un servicio DNS, para poder registrar los registro tipo A, 
apuntando a la dirección IP de la máquina asignada en Amazon. En el archivo ``virtualhost.conf`` 
en la ruta de ``/etc/httpd/conf.d/``, deben cambio el valor ``CAMBIAR`` por la IP, ver imagenes.

![amazon-ip](imagenes/ip-amazo.png)

![archivo virtual host](imagenes/virtualhost.png)

Una vez modificado ejecutar el comando: 
```
sudo service httpd reload
```

