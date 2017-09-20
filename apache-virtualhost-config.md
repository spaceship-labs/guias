# Configuración de un nuevo subdominio del gitserver

Creando el repositorio GIT
	1.-Nos situamos en la carpeta /var/cache/git/ del server
	2.-creamos la carpeta del repositorio: mkdir proyecto.git y entramos en el directorio: cd proyecto git
	3.-iniciamos le nuevo repositorio: git init --bare
	4.-modificamos el archivo siguiente archivo para que haga el checakout de manera correcta:
		/var/cache/git/proyecto.git/hooks/post-receive
		solamente necesita la linea: GIT_WORK_TREE="direacción en /var/www/ de nuestro proyecto" git checkout -f
	5.- ahora ya podemos subir desde el cliente usando git remote add 
	
	
# Configurando virtualhost en Apache
1. dentro del apache (en nuestro caso apache2) /etc/apache2/ se encuentra un archivo que necesitamos modificar:
`/etc/apache2/sites-available/sites`, 
ahi se define le virtual host solamente tenemos que agregarle un alias para nuestro proyecto por ejemplo:
```
<VirtualHost *:80>
    DocumentRoot /var/www/htdoc/proyecto
    ServerName  example.com 
    ServerAlias www.example.com 
    ServerAdmin admin@example.com
    SetEnv APPLICATION_ENV "git_config"
    <Directory "/var/www/htdocs/sitefolder"
      Allow from all
      AllowOverride All
      Order allow,deny
    </Directory>
    DirectoryIndex index.html index.php
</virtualHost>
```
		

4.-reseteamos el apache `/etc/init.d/apache2 restart`
	
	