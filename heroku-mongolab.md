#Heroku

 git init

 heroku create

 git add --all

 git commit -m "all"

 git push heroku master

 heroku config:set ENVIRONMENT=production

 heroku info -> Vemos la url de nuestro heroku

 heroku logs

 agregar al packet json el script start

 "scripts": {
        "start": "node app"
  }, 

  y 

  "engines": {
    "node": "6.9.1"
  },

#MongoLab // dbuser:admin    dbpassword:admin12345

##Creando una nueva BBDD

https://mlab.com/home --> Create new en MongoDB Deployments

Plan: Single-node, Standard Line, Sandbox

Database Name: El nombre de la BBDD

Apretar el boton Create new MongoDB deployment

Ir a la pestaña users y crear un usuario, admin  admin12345

##Conectando por shell y Node

To connect using the mongo shell:
 
mongo ds135797.mlab.com:35797/curlingthecurl -u admin -p admin12345


To connect using Node:

mongodb://admin:admin12345@ds135797.mlab.com:35797/curlingthecurl



Para importar un json a la BBDD de MongoLab

Desde el shell en la carpeta donde tenemos el json

mongoimport -h ds135797.mlab.com:35797 -d curlingthecurl -c appointments -u admin -p admin12345 --file appointments.json --jsonArray





