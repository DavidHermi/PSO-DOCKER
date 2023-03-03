# PSO-DOCKER
 
 
 
 
 
 
 
 
 1º Paso, configuracion del docker, configurar el punto yml:
    -Hacemos el punto yml empezando por el primer servicio que seria la db, pero antes configuramos la version de docker.
    despues pasamos a la db
    
 
    db:
    image: postgres:13
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD=odoo
      - POSTGRES_USER=odoo
    ports:
      - "5430:5432"
    volumes:
      - dam22_odooDavid:/var/lib/postgresql/data 
     
      
  --Como puedes observar se añade la imagen de la base de datos, sus datos, los puertos a los que esta conectados y el volumen en el que se mete.
 
  2º Paso, Configuramos la instalacion de Odoo, en el punto yml, en el segundo servicio que lo llamaremos odooo
  
  ```
  image: odoo:14.0
    container_name: dam22_odooDavid
    volumes:
      - ./conf:/etc/odoo
    ports:
      - "8069:8069"
    depends_on:
      - db
volumes:
    dam22_odooDavid:
  ```
   
    
 --La configuracion se distribuiria de la siguiente manera: Imagen de la instalacion, contenedor, volumenes adicionales que se crean, puertos, que depende de la base d edatos por lo cual va en el mismo volumen.
  
  
  3º Paso, iniciamos en visual estudio code, el proyecto con el docker-compose.yml, podremos ejecutar los siguientes comandos:
    
- Comando para iniciar el docker-compose.yml.
```
docker-compose up
```
- Comando para cerrar el docker-compose.yml.
```
docker-compose down
```
- Comando para parar el docker-compose.yml.
```
docker-compose stop
```

4º paso, una vez inciamos el docker compose, lo abrimos en el navegador y instalamos el servicio

      
  
  
  

    
