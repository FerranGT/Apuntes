#Javascript

ECMA 2015 no funciona correctamente en todos los navegadores

Double negation !! is a quick way to convert any value to its correspondent boolean.

`!!0
false
!!1
true
!!""
false
!!"hola"
true
!!undefined
false
!!null
false´

Applying this techniqe we could check how any value converted to boolean is true but:

""
null
undefined
0
NaN
false
Because of this, these values are also called Falsy Values

Cuando ponemos una variable en un if, el if la convierte en booleano internamente para evaluarla

=== Equality and Type

Returns true when both operands are equal AND when they have the same data type. It's usually better and safer using this equality comparison (there are no uncontrolled conversions behind the curtains)

1 == 1;
true
1 == '1'; realiza conversion de tipo
true
1 === '1'; no realiza conversion de tipo
false
1 === 1;
true

Conversions

var s = "100"; typeof s; 
"string" 
s = s * 1; Es una manera rapida de convertir una string en un number
100 
typeof s; 
"number"

Operador ternario

`var result = (a === 1) ? "a is one" : "a is not one";`  si es true result="a is one" si es false result= "a is not one"

switch

var a = '1';
var result = '';
switch (a) { 
  case 1: 
    result = 'Number 1'; 
    break; 
  case '1': 
    result = 'String 1'; 
    break; 
  default: 
    result = 'I don\'t know'; 
    break;
}
result;
Parts in a switch structure are:

The switch sentence
An expression between parenthesis.
This expression will usally be a variable, but it can be any expression that returns a value
Some case blocks between braces
Every case sentence is followed by an expression.
The result of this expression (case) is compared with the expression that is after the switch .
If the equal comparison returns true, the block code after that case is executed
It can (and it should) be a sentence break at the end of every case block.
These break cause the exit from the switch (so we assure only a case block is executed)
There also can (and should) be a sentence default followed by a code block that'll be executed if no case is evaluated to true


Concatenar strings

var name='juanma';

var names= 'pepe' + juanma;

Otra manera de declarar funciones cortas

var sayhi = function() {return "hi!"}

function sum(){
    console.log (arguments) // nos captura todos los elementos que le pasamos en una funcion actua como pseudoarray
    
    for (i in arguments){
        result += arguments[i];
    }


}

parseInt()

parseInt() takes a value and tries to transform it in an integer If the transformation fails it returns NaN.
parseInt() can take a second optional parameter that sets the numerical base of the number passed as first argument (decimal, hexadecimal, binary, etc…)

parseInt('123')
123
parseInt('abc123')
NaN
parseInt('1abc23')
1
parseInt('123abc')
123

It's recommended especifying always the base (usually 10) to avoid issues with the interpretation, el segundo paramatro le indicamos la base

parseInt(" 0xF", 16);
15
parseInt(" F", 16);
15
parseInt("17", 8);
15
parseInt(021, 8);
15
parseInt("015", 10);
15
parseInt(15.99, 10);
15
parseInt("FXX123", 16);
15
parseInt("1111", 2);
15
parseInt("15*3", 10);
15
parseInt("15e2", 10);
15
parseInt("15px", 10);
15
parseInt("12", 13);
15

#Declaracion de Funciones

`function f(){ return 1; }`

`var f = function(){ return 1; }`

Otro ejemplo:

`function declaration1 (a,b){` // el resultado de la suma se queda en return pero no se guarda en ningun sitio, lo puedes mostrar por pantalla o anidarlo en otra funcion
  `return a+b;`
`}`


`var sum = function declaration2 (a,b){` // el resultado de la suma se guarda en la var sum
  `return a+b;`
`}`


**Como las funciones tambien son objetos podemos hacer:**

`declaration1.location = "Barcelona";`

Puedes poner las funciones en un array

`var f = function (x) {`
    `return x + 1;`
`};`
`var g = function(x) {`
    `return x * 2;`
`};`
`var lst = [f, g, f];` // a list of functions!
`var y = lst[1](5);` // same as g(5) -> 10


Anonimous functions are those that doesn't have a name and can be used to:

Pass that function as an argument of a function
Define a function and execute it inmediately, te permite ahorrarte la declaracion de una varianle

`function(a){ return a; }` // funcion anonima

When we pass a function A as an argument of another function B and B executes A, we tell that A is a callback function

`function invoke_and_add(a, b){ return a() + b(); }`
`function one() { return 1; }`
`function two() { return 2; }`
`invoke_and_add(one, two);`
`3`
`invoke_and_add(one, function(){return 7;})`
`8`


var sum = function (a,b) {return a+b;}

var a = sum // function () {...}
var b = sum(2,3) // 5
var c = sum () // Nan => undefined + undefined
var d = sum (2,3,4,5,6,) // 5

a(4,5) // 9
b(4,5) // error


function operate (a,b,operation){
    return operation(a,b);
}

function sum (a,b){
    return a+b;
}

function mult (a,b){
    return a*b;
}

operate(3,4,sum)//7
operate(3,4,mult)//12
operate (sum(2,4)/*6*/,mult(3,4)/*12*/,sum)//18

#Closures

If we define a function n() inside of another function f() , n() will have access to all the variables in its scope and its father's scope. This is what is called scope chain

var a = 1;
function f(){
  var b = 1;
  function n() {
    var c = 3;
  }
}

Functions have what is called as lexical scope which means they create theis scope (which variables can they access) when they are defined, not when they are executed

function f1(){ var a = 1; return f2(); }
function f2(){ return a; }
f1();
a is not defined
var a = 5;
f1();
5
a = 55;
f1();
55
delete a;
true
f1();
a is not defined


var a = 123;
function f() {
  alert(a);// undefined, pq sabe que esta funcion tiene una variable local a, pero no tiene ningun valor asignado
  var a = 1;// a=1
  alert(a);
}
f();


Una variable si no la declaras pero le asignas un valor la creas pero si la llamas sin haberle asignado un valor ni haberla declarado esta undefinida y da error


A closure is created when a function maintains a link with the scope of the father, even after the parent function has finished

function f(){
  var b = "b";
  return function(){
    return b;
  }
}

b is not defined //desde el global
var n = f();
n();
"b"
slides 38, 39, 40
38 - undefined y new value
39 -  foo() // undefinesd pq la var aun no esta asignada
      bar() // this will run!  
40 - 2



Because functions are values, you can pass functions as arguments and return them from other functions. Here is a definition of callTwice that takes a function f as an argument and invokes it twice in a row.

var addOne = function (x) {
    return x + 1;
};
var callTwice = function(f, x) {
    return f(f(x));
    // var myvalue = f(X)//4
    //return myvalue // 5

};
var y = callTwice(addOne, 3);
// => addOne(addOne(3)) => 5

Define a function named applyTest that takes two arguments, a function f and an input x. Your function should return a list that contains x, the function f on the input x, and the function f on the input 0.

var applyTest = function (f,x) {
    return [x, f(x),f(0)];
    
    
};


var makeFunction = function () {
    var addOne = function (x) {
        return x + 1;
    };
    return addOne; // return the function
};
// makeFunction is a function with no arguments
 
var f = makeFunction();
// f is a function that takes one argument
 
var y = f(3);
// now y is 4
Remember there's a difference between a function and a function applied to its arguments. It's the difference between f and f(x). If a function doesn't take any arguments there is still a difference. makeFunction is a function that takes no arguments, makeFunction() is the result of calling that function. Which is itself another function...

Define a function named generate that takes one argument, a function f. It should return an array that consists of the function f and another function that doubles its input.

`var generate = function (f) {`
    `return [f,function(x){return x*2}];`    
`};`


#Function Scope

Many languages have block scope, which means that variables declared at the start of a block like an if or a for loop are valid within that block. JavaScript is a bit different, all variables have function scope.

This means that all the variables declared in a function are available everywhere in the function. Here's an example that shows how this can be a little surprising.

var cow = "purple"; // just a random cow
 
var f = function (x) {
    var r = 0;
    cow = "glue";
    if (x > 3) {
        var cow = 1; // a local variable
        r = 7;
    }
    return r;
};
 
var z = f(2); // ...
Does cow get turned into "glue" when you call f(2)? No, cow is safe in the above code because the var cow declaration inside the if block applies to the entire function. It means that cow is a local variable for the entire function.

To satisfy your morbid bovine curiosities, here is the version that does turn cow into glue.



var cow = "purple"; // just a random cow
 
var f = function (x) {
    var r = 0;
    cow = "glue";
    if (x > 3) {
        r = 7;
    }
    return r;
};
 
var z = f(2); // poor cow
Because of this surprising behavior, when you write functions you should always declare all your variables right at the start so you don't get confused. Here's an example that declares a few variables the right way.

Definir una función llamada llamarFunc que reciba un argumento, una función f. Debe retornar un array con los valores f(0), f(0), f(1), f(1). Solo se puede llamar a f dos veces.

function llamarFunc (f) {
    var f0, f1;
    f0 = f(0);
    f1 = f(1);
    return [f0,f0,f1,f1];
}

Dentro de una función se puede definir y usar otra función. El siguiente ejemplo muestra una función auxiliar para simplificar un cálculo complicado.

var complicado = function (x) {
    var f = function (y) {
        return y * 3 + 1;
    };
    return f(f(x));
};
var y = complicado(2);
// Ahora y es 22


#Objects

```var hero = {
  breed: 'Turtle',
  occupation: 'Ninja'
  talk: function(){
    alert('Woof, woof!');
  } 
};
```

**Para acceder al objeto:**

dog.name o dog["name"]//diferencia [accede siempre al contenido]

**Para añadir un campo**

var mypropertyname = "location";
dog.[mypropertyname] = "barcelona"; // agrgamos el campo location -> dog.location = "barcelona"
dog.spicy = "pitbull" // agrgamos el campo spicy

objetos dentro de un objeto
var book = {
  name: 'Catch-22',
  published: 1961,
  author: {
    firstname: 'Joseph',
    lastname: 'Heller'
  }
};

book.author.firstname // accedo a este campo
book['author']['lastname']
book.author['lastname']

var propnames = ["firstname","lastname"]
book.author[propnames[0], propnames[1]]

--------
var myarray = [];
myarray.length = 10; //10xundefined, aun no puedo hacer map pq es undefined lo tengo que rellenar
myarray.fill(3); // tengo las dias casillas con valor 3 y puedo utilizar el map
---------------

```var namesStudents = ["paco", "pepe", "juan", "maria"]
var o = { students : {} };
var currentProp = "";

for (var i=0; i<namesStudents.length; i++) {
  currentProp = namesStudents[i];
  o.students[currentProp] = ["maths", "physics"]
}

console.log(o) // Me crea un objeto con los campos "paco", "pepe", "juan", "maria" y en cada uno hay dos strings "maths", "physics"


```



```var book = {
  name: 'Catch-22',
  published: 1961,
  author: {
    firstname: 'Joseph',
    lastname: 'Heller'
  }
};

var propNames = ["firstname", "lastname"]
var currentProp = "";

for ( var prop in book.author ) {
  console.log (prop + " => " + book.author[prop])
}
```


**We can define an empty object and then add (and remove) its properties and methods**

``` var hero = {};
 typeof hero.breed
"undefined"
 hero.breed = 'turtle';
 hero.name = 'Leonardo';
 hero.sayName = function() {return hero.name;};
 hero.sayName();
"Leonardo"
 delete hero.name;
true
 hero.sayName();
reference to undefined property hero.name
```

**When we are inside of a method, the special keyword this points to the object that owns the method ( “this object” )**

```var hero = {
  name: 'Rafaelo',
  sayName: function() {
    return this.name;
  }
}
 hero.sayName();
"Rafaelo"
```

#Constructor Functions 3 formas: literal, funcion constructora, funcion que devuelve un objeto, las funciones son objetos y los arrays tambien, todo lo que no son las variables primitivas.

**Another way of creating objects is by using constructor functions To create objects w/ these functions we have to use the operator new The advantage these constructor functions have is that they accept parameters for the creation of the objects**

```function Hero(name) {
  this.name = name;
  this.occupation = 'Ninja';
  this.whoAreYou = function() {
    return "I'm " + this.name + " and I'm a " + this.occupation;
  }
}

var h1 = new Hero('Michelangelo');
var h2 = new Hero('Donatello');
h1.whoAreYou();
"I'm Michelangelo and I'm a Ninja"
h2.whoAreYou();
"I'm Donatello and I'm a Ninja"
```

All the javascript environments have a global object and all the global variables are properties of this global object In the browser this global object is called window

So, we can access a global variable a:

As a variable a
As a property of the global object: window[‘a’] or window.a

Si yo declaro una variable global pasa a formar parte del objeto global window:
var a= 5; // variable global
puedo hacer
window.a;
5


If we declare a constructor function and we call it without new

It will return undefined
All the properties are declared with this will become properties of window
>>> function Hero(name) { this.name = name; }
>>> var h = Hero('Leonardo');
>>> typeof h
"undefined"
>>> typeof h.name
Uncaught TypeError: Cannot read property 'name' of undefined(…)

>>> name
"Leonardo"
>>> window.name
"Leonardo"

>>> var h2 = new Hero('Michelangelo');
>>> typeof h2
"object"
>>> h2.name
"Michelangelo"

With the operator instanceof we can check if an object was created by a specific constructor function

>>> function Hero(){}
>>> var h = new Hero();
>>> var o = {};
>>> h instanceof Hero;
true
>>> h instanceof Object;
false
>>> o instanceof Object;
true


**Another way of creating an object is by using a function that returns an object**

```function factory(name) {
  return {
    name: name
  };
}
var o = factory('one');
o.name
"one"
o.constructor
Object()
```

**We can use constructor functions and return objects different than this**

```function C() { this.a = 1; }
var c = new C();
c.a
1
function C2() { this.a = 1; return {b: 2}; }
var c2 = new C2();
typeof c2.a
"undefined"
c2.b
2
```

new will always return an object, that's why if the constructor function returns something different than an object, the call to that function with new will continue returnin the proper this

#3 ways of creating objects 

**LITERAL**

```var student = {
   name: "juanma",
   age: 40
}
```


**Funcion que devuelve un objeto**

```function getStudent( myName, myAge ) {
  return {
     name: myName,
     age: myAge
  } 
}

var student  = getStudent("juanma", 40);
```


**Funcion constructora**

```function Student( myName, myAge ) {
  this.name = myName;
  this.age = myAge;
}

var student  = new Student("juanma", 40);
```

student.prototype.sayhi = function(){//al prototype solo se puede acceder desde funciones
  returm "hi" + this.name + "you are" + this.age + "years old";
}

function Person(gender) {
    this.gender = gender;
    console.log (this.gender + ' instantiated');
  }

  var person1 = new Person('Male');
  var person2 = new Person('Female');

  >>> person1.gender === 'Male'
  true
  >>> person2.gender === 'Female'
  true

  >>> Person.prototype.type = 'Human being';

  >>> person1.type === 'Human being'
  true
  >>> person2.type === 'Human being'
  true

  person1.type = 'Super Hero';

  >>> person1.type === 'Super Hero'
  true
  >>> person2.type === 'Human being'
  true


#Copying Objects

When we copy an object or we pass it as a parameter of a function, we're really passing a reference to that object. If we do a change to this reference, we will also modify the original object

```var original = { howmany: 1 };
var copy = original;
copy.howmany
1
copy.howmany = 100;
100
original.howmany
100

var nullify = function(o) { o.howmany = 0; }
nullify(copy);
original.howmany
0
```


**Comparing Objects**

When we compare objects we will only obtain true if we compare 2 references to the same object

```var fido = { breed: 'dog' };
var benji = { breed: 'dog' };
benji === fido
false
benji == fido
false
var mydog = benji;
mydog === benji
true
mydog === fido
false
```

------


Ex:
var mathy = function(x) {
    return function (y) {
        return function (z) {
            return (x / y) - z;
        }
    }
}
¿Cómo hariamos la operación (4 / 3) - 2 con este código en una linea?

mathy(4)(3)(2);

otro ejemplo

function saySomething(msg) { 
  return function(name) {
    return msg + " " + name;
  }
}

saySomething("hola")("juanma") // "hola juanma"

#Higher Order Functions
Funciones que reciben funciones

Higher Order Functions are those functions that accept other functions as parameters or those that return functions(or both). They are the functions that treat other functions as values (enter or exit)

#Prototypes que les vamos a pasar una funcion

#forEach()

El método forEach() ejecuta la función indicada una vez por cada elemento del array.

array.forEach(callback[, thisArg])

Parámetros

callback
Función a ejecutar por cada elemento, que recibe tres argumentos:

  currentValue
  El elemento actual siendo procesado en el array.

  index
  El índice del elemento actual siendo procesado en el array.

  array
  El arreglo en el que forEach esta siendo aplicado.

thisArg
Opcional. Valor que se usará como this cuando se ejecute el callback.


```function logArrayElements(element, index, array) {
  console.log('a[' + index + '] = ' + element);
}
```
// Note elision, there is no member at 2 so it isn't visited
`[2, 5, , 9].forEach(logArrayElements);`//forEach hace el bucle la funcion de dentro hace lo que tu quieras hacer dentro del bucle
// logs:
// a[0] = 2
// a[1] = 5
// a[3] = 9
[]

```var names = ["Ben", "Jafar", "Matt", "Priya", "Brian"];

names.forEach(function(name) { /* element, index, array */
  console.log(name);
});
```

password.forEach( function( char ) { //le pasamos la variable char que es la posicion del array que va haciendo el bucle, for each puede pasar element, index, array, usamos el parametro element que es el contenido del array en cada vuelta del bucle array[0] array[1] array[2] ...., char son todos los elementos del array password 
    if ( (config.special).includes(char) ) { // true || false
      // the password contains at least one special char
    }
  })

Ejemplo:

var myObject = { a: 2, b: 3 }
undefined
var myAnotherObject = myObject
undefined
function nullify( o ) {
  for (var prop in o) {
    delete o[prop]
  }
}
undefined
var a = { a: 3, b: 5}
undefined
delete a.a
true
a
Object {b: 5}b: 5__proto__: Object
var myArray = [2,4,5,2]
undefined
myArray
[2, 4, 5, 2]
delete myArray[2]
true
myArray
[2, 4, undefined × 1, 2]
nullify(myArray)
undefined
myArray


**forEach hace el bucle y la funcion define que hacemos dentro del bucle**

#map()

map() returns a new array with the result of calling a function provided as an argument over every element of the array, hace el bucle y te de vuelve un array

arr.map(callback[, thisArg])
function double(element /*, index, array*/ ) {
  //console.log('a[' + index + '] = ' + element);
  return element * 2;
}

// Note elision, there is no member at 2 so it isn't visited
>>> [2, 5, 3, 9].map(double);
[4, 10, 6, 18]


  ```var myarray=[];
  myarray.length = 100;
  myarray.fill(0);

  var fullarray=myarray.map(function(elem,index){
    return elem=index;
  }
  ```

```function double(x) { return x*2; };
[1,2,3,4,5].map(double); // => [2,4,6,8,10]

function sum(total, item) { return total + item; };
[15, 30, 20].reduce(reducer, 0); // => 65
```

#filter()

filter() returns a new array with those elements that pass the test (return true when applying the function on them) in the function passed as a paramenter

arr.filter(callback[, thisArg])
function isMoreThan5(element /*, index, array */) {
  //console.log('a[' + index + '] = ' + element);
  return element >= 5;
}

>>> var groupMoreThan5 = [2, 5, 3, 9].filter(isMoreThan5);
>>> groupMoreThan5
[5, 9]


#every()

every() return true if ALL the elements of the array pass the test provided as a parameter (they all return true when we apply the function on them)

arr.every(callback[, thisArg])
function isMoreThan5(element /*, index, array */) {
  //console.log('a[' + index + '] = ' + element);
  return element >= 5;
}

>>> console.log ( [2, 5, 3, 9].every(isMoreThan5) )
false
>>> console.log ( [22, 5, 33, 9].every(isMoreThan5) )
true


#some()

some() return true if SOME element of the array pass the provided test as a parameter (one or more return true when we apply the function on them)

arr.some(callback[, thisArg])
function isMoreThan5(element /*, index, array */) {
  //console.log('a[' + index + '] = ' + element);
  return element >= 5;
}

>>> console.log ( [2, 5, 3, 9].some(isMoreThan5) )
true
>>> console.log ( [1, 2, 3, 4].some(isMoreThan5) )
false


#reduce()

reduce() applies a function recursively over an accumulator and over every item if the array (from left to right) until getting a unique value

arr.reduce(callback[, initialValue])
function sumElements(acc, current /*, index, array */) {
  //console.log(acc + ' | ' + current + ' | ' + index + ' | ' + array);
  return acc + current;
};

// Note elision, there is no member at 2 so it isn't visited
>>> [2, 5, 3, 9].reduce(sumElements);
19
var flattened = [[0, 1], [2, 3], [4, 5]].reduce(function(a, b) {
  return a.concat(b);
}, []);
// flattened is [0, 1, 2, 3, 4, 5]


#formas diferentes de devolver con un return

// No, but you could return an array containing your values:

// var newCodes = function() {
//     var dCodes = fg.codecsCodes.rs;
//     var dCodes2 = fg.codecsCodes2.rs;
//     return [dCodes, dCodes2];
// };
// Then you can access them like so:

// var codes = newCodes();
// var dCodes = codes[0];
// var dCodes2 = codes[1];
// If you want to put "labels" on each of the returned values (easier to maintain), you can return an object:

// var newCodes = function() {
//     var dCodes = fg.codecsCodes.rs;
//     var dCodes2 = fg.codecsCodes2.rs;
//     return {
//         dCodes: dCodes,
//         dCodes2: dCodes2
//     };
// };
// And to access them:

// var codes = newCodes();
// var dCodes = codes.dCodes;
// var dCodes2 = code











Tambien pasa con los arrays cuando se pasan por funciones

var myArray = [2,6,3]

function modifyArray( someArray ) {
  someArray.push(23);
  return someArray;
}

var anotherArray = modifyArray(myArray);
undefined
anotherArray
[2, 6, 3, 23]
myArray
[2, 6, 3, 23]

Con map no pasa pq nos devuelve una copia que es nueva