# Repositorio para la prueba de concepto de Vitualhost y Proxy Reverso

Para hacerlo posible se hizo un fork al repositorio virtualhost-proxyreverso del professor @vacax.
Se modificaron los archivos tal como `seguro.conf` encontrado en configuraciones del cual cambiamos los campos que decian CAMBIAR a nuestro sitio.

Tambien se modifico el archivo `configuraciones/proxyreverso.conf` cual contenia un error de sintaxis. Le faltaba una P en la linea 5.


En una instancia basada en Amazon Linux, clonar el proyecto actual y ejecutar los siguientes comandos para instalación básica:



```
wget https://raw.githubusercontent.com/christpaul01/virtualhost-proxyreverso/master/basico.sh && chmod +x basico.sh && bash basico.sh
 && chmod +x basico.sh && bash basico.sh
```

# comandos para instalar let'sEncrypt
```
sudo systemctl stop httpd

sudo certbot certonly --standalone
```

Incluimos los sitios app1.christopherpaul.me y app2.christopherpaul.me 
`(Evitaremos separarlos con coma para que ambos puedan tener sus archivos diferentes)`

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

Es necesario contar con un servicio DNS, en nuestro caso usaremos namecheap, para poder registrar los registro tipo A, 
apuntando a la dirección IP de la máquina asignada en Amazon. 

![amazon-ip](imagenes/ip-amazo.png)


Una vez modificado ejecutar el comando: 
```
sudo service httpd reload
```

De ahi se puede visitar app1.christopherpaul.me y app2.christopherpaul.me, deberiamos de tener dos aplicaciones corriendo
en un mismo hosts teniendo la misma direccion IP. 
