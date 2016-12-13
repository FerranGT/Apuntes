#Instalar Mongo

http://brew.sh/index_es.html

https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/

#Creando un proyecto

mkdir

npm init -y // crea el json con las dependencias

sudo npm install express mongodb --save// --save añade como dependencia al json

Si voy a usar pug en express sudo npm install pug


#Arrancar Mongo

mongod --dbpath ~/data/db //Aqui escucha, el servidor

En otra ventana de la shell: 
mongo //Aqui es el cliente


#Comandos

show dbs //nos muestra todas nuestras bases de datos

use skylabDB /nos crea la BD o nos cambia a la BD escogida

show collections // nos muestra el contenido de la BD

db.collection.help()

Ejemplo para un comando en concreto db.collection.find().help()

 db.movies.insert({ // Inserto mi primera coleccion (objeto), y tambien creo el nombre de la coleccion
    year: 1985,
    title: 'Back to the Future'
 }) 

 show collections



 db.movies.insertMany([
{
    year: 1981,
    title: 'En busca del arca perdida'
},
{
    year: 1989,
    title: 'Indiana Jones y la última cruzada'
},
{
    year: 1984,
    title: 'Indiana Jones y el templo maldito'
},
{
    year: 1989,
    title: '    Regreso al futuro II'
}
]) 


db.movies.find() // en movies hay que poner el nombre de nuestra coleccion

db.movies.find().pretty()

db.movies.find().count()

db.movies.update({
    title: 'Regreso al futuro II'//condicion de busqueda se pueden poner varias
    $set {
        title: 'Back to the future II'//campos que queremos actualizar
    }
})

db.movies.remove({
    title: 'Regreso al futuro II'//condicion de busqueda se pueden poner varias
})


db.collection.drop() // Elimina la coleccion





#Creando un programa

Creamos el directorio con mkdir // sin espacios

npm init -y

npm install express mongodb --save



Importando un json que tengo en mi carpeta de proyecto

$ mongoimport --db test --collection restaurants --drop --file primer-dataset.json

show dbs // veo todas las BBDD

use test // cambio a la BBDD test

show collections // veo la collecion que hay

db.restaurants.find().pretty() // veo todo el array de objetos

db.restaurants.find().count() // el numero de documentos(objetos) de la coleccion


#Añadir comandos al script en el packet.json

"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node app",
    "dev": "nodemon app"
},


#Mongoose

npm install mongoose --save