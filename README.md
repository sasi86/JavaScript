# JavaScript
https://developer.mozilla.org/en-US/docs/Web/JavaScript
https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics

Js
1. LightWeight - easy to implement
2. Interpreted -  No Compilation
3. Object Oriented 
4. First class function - Functions as value
5.Scripting Language

Why Js?
To Rich Web Dev
  . Native JS
  . Framework
  . Angular JS, React JS, Ember
Server Side
 . Node Js

ECMA Script - Spec for Javascript
latest ECMA script ES6

Variable
--------
No Typed Variable
var myVariable;

Type:
String
Number
Boolean
Array ex: var myVar = [10,'Sasi',true]
undefined (absence of value)
Object ,null (special value indicated for non value) Middle Name Example

Mix and Match: //Loose Typing
var a =10;
a='Hello'

Decleration(declare variable) and Definition(assign Value)

OPERATOR
--------

typeof - gives dataType
=
== 



if Condition

Values of all types have an associated boolean value

False Conditions
if(0) console.log('hi'); else console.log('Hello'); //Hello
if("") console.log('hi'); else console.log('Hello'); //Hello
if(null) console.log('hi'); else console.log('Hello'); //Hello
if(undefined) console.log('hi'); else console.log('Hello'); //Hello

True Conditions
if(1) console.log('hi'); else console.log('Hello'); //Hi
if("a") console.log('hi'); else console.log('Hello'); //Hi


Objects
-------

JS objects are not class based objects. Object Consist of property  and functions. Consider them as MAP with [k,v]

Ex: var myObj = {} // Creation Objects

Adding property

myObj.prop = 'Hello';
myObj.prop1 = 1;
myObj.1 = 1;

Reading propety from Obj

Dot Notation

console.log(myObj.prop);
console.log(myObj['prop']);
console.log(myObj.1);//error

square bracket Notation - use this when key is reserved word and dynamic [optimization is less compared to Dot Notation]

console.log(myObj['prop']);
console.log(myObj['1']);
var propName = 'prop';
console.log(myObj[propName]);


#Nested Objects

var myObj = {
  prop1 : 1,
  prop2 : true,
  prop3 : 'hello',
  prop4 : {
    innerProp1 : 'innerProp'
  }
};
myObj.prop4.newInnerProp = 'new inner prop';
console.log(myObj.prop4.innerProp1);
console.log(myObj.prop4['innerProp1']); // min and match
console.log(myObj.prop4.newInnerProp);

1. How === works with Object?
2. How undefined and null works with Object?
3. Can I assign undefined to variable decalred?


#Remove Object Property

delete myObj.prop1


#Arrays


var myArr = [1,2,3]

Access array - index zero based

console.log(myArr[0]);// 1

Add data to array

myArr[3] = 4;
console.log(myArr[3]);// 4

Find the length of an array
console.log(myArr.length) //4 

Note : Array internally is a JS Object. See the console.log(myArr); Just like JS Object we can have nested Arrays. Even you can use myArr["0"] just like Objects.

myArr[400] = "Hi"
console.log(myArr.length) //401 coz not the count of the element present. lenght is maxIndex + 1

myArr["newProp"] = "new prop";
console.log(myArr); // will it work?, Yes it works at Arrays are object Note: treat Arrays as arrays not as Objects


#Wrapper Objects

var myObj = "Hello";

console.log(myObj.length) // 5. How is this possible myObj typeOf is string. but we use dot notation like a object. it uses a wrapper Object(String) for fraction of second and convert it back to primitive

Number | Boolean
----------------
String | Symbol


#Functions
 -Function Delaraction
 function greet(){
    console.log('Hello')
 }

 . Syntax
 . Arguments - passing arguments are optional
 
 function greet(fName,lName){
  return 'Hello' + fName + lName;
 }
 
 console.log(greet('Sasi')); Guess What?
 
 . return Statment - 
 
 Example
 
 function greet(){
  return 'Hello';
 }
 
 console.log(greet());
 
 function greet(){
  return;
 }
 
 console.log(greet()); Guess What?
 
 #Function Expression - function itself is an value in JavaScript

var f = function greet(){
  console.log('Hello');
}
f(); // Hello;

1. what Happens to the below example
var f = function greet(){
  return function(){
    return 'Hello';
  }
}

console.log(f()());

2. What are the ways in which you can create an function?
  - Function Delaraction - Function Expression

#Anonymous Function Expression
var f = function(){
  console.log('Hello');
}
f(); // Hello;

#Function As Arugument

Ex1:
var print = function(){
  console.log('Hello');
}

var executor = function(fn){
  fn();
}
executor(print); // Hello;

Ex2:
var print = function(name){
  console.log('Hello '+name);
}

var executor = function(fn,name){
  fn(name);
}
executor(print,'Sasi'); // Hello;

#Function inside Object

Ex:
var myObj = {
  prop1 : 1
}

myObj.myFn = function(){
  console.log('new function');
}

myObj.myFn(); //prints new function

#this Keyword in functions
var person = {
  fname : 'Sasi',
  lname : 'Kumar',
  getFullName : function(){
    return person.fname + " " + person.lname;
  }
};

console.log(person.getFullName()); // output??

var person2 = person;

console.log(person2.getFullName()); // output??

person = {}

console.log(person2.getFullName()); // output??

Excercise

var person = {
  fname : 'Sasi',
  lname : 'Kumar',
  getFullName : function(){
    return person.fname + " " + person.lname;
  },
  address : {
    street: '12123 st',
    city : 'Chennai',
    state : 'TN'
  },
  isFromState : //Write a function that says if the person is from the state we are passing
};

console.log(person.isFromState('TN'));

#Default function arguments -- get 2 args for free arguments,this

var add = function(a,b){
  console.log(arguments)
  console.log(a+b)
}

add(10,20,30);
