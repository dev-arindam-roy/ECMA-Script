# ECMA-Script
ECMA Script All

## ES6-2015

> **const, let, var**
```js
/*
Can not decleared more than one time
The value should be constant on page/script load
value can not be overwritten
*/
const num1 = 25;
console.log(num1);

/*
Can not decleared more than one time in same block/scope
value can over written
*/
let num2 = 25;
console.log(num2);
num2 = 30;
console.log(num2);

/*
There are no restriction
declared multiple times
overwrite multiple times
re-declared multiple times
no block/scope dependency
*/
var num3 = 40;
console.log(num3);
num3 = 45;
console.log(num3);
var num3 = 60;
console.log(num3);


/*
block/scope dependency example
*/
function fun1(num) {
  let value = 20;
  if (num == 30) {
    let value = 30 * 2;
    console.log(value);
  }
  if (num == 100) {
    let value = "Hello 100";
    console.log(value);
  }
  if (num == 1000) {
    let value = {
      name: 'Arindam',
      skill: 'JS'
    };
    console.log(value);
  }
  console.log(value);
}

fun1(20); //only: 20
fun1(30); //first: 60 second: 20

fun1(10); //only: 20
fun1(100); //first: "Hello 100" second: 20

fun1(25); //only: 20
fun1(1000); //first: [object Object] {name: "Arindam",skill: "JS"} second: 20
```
> **Arrow Function**
```js
/*
Normal/basic function
*/
function add (num1, num2) {
  return num1 + num2;
}
console.log(add(2, 6)); //8

/*
No parameter
No return
No braces
*/
const getValue1 = () => 25;
console.log(getValue1()); //25

/*
have 1 parameter
No return
No braces
*/
const getValue2 = (x) => x * 2;
console.log(getValue2(2)); //4

/*
have 2 parameters
No return
No braces
*/
const getValue3 = (x, y) => x + y;
console.log(getValue3(2, 4)); //6


/*
have 2 parameters
have return
have braces
if used braces then should use return
*/
const getValue4 = (x, y) => { return x * y };
console.log(getValue4(2, 4)); //8

const getValue5 = (p, t, r) =>  {
  return `Intarest is ${((p*t*r)/100)}`;
};
console.log(getValue5(1000, 5, 4.5)); //"Intarest is 225"

const getValue6 = (p, t, r) =>  {
  let intarest = (p*t*r)/100;
  let total = intarest + p;
  return `The total amount is ${total}`;
};
console.log(getValue6(1000, 5, 4.5)); //"The total amount is 1225"
```
> **Spread Operator**
```js
/*
Spread Operator merge in an single array
but not discard the same elements/items
Like below:
*/

let arr1 = ["php", "java", "node"];
let arr2 = ["mysql", "mongo", "firebase"];
let resArr1 = [...arr1, ...arr2];
console.log(resArr1);
/*
OUTPUT:
["php", "java", "node", "mysql", "mongo", "firebase"]
*/


let arr3 = ["php", "mysql", "next"];
let arr4 = ["mysql", "angular", "mongo"];
let arr5 = ["angular", "vue", "next"];
let resArr2 = [...arr3, ...arr3, ...arr5];
console.log(resArr2);
/*
OUTPUT:
["php", "mysql", "next", "php", "mysql", "next", "angular", "vue", "next"]
*/

let arr6 = [10, 25, 30, 50];
let arr7 = [30, 35, 40, 50];
let resArr3 = [...arr6, ...arr7];
console.log(resArr3);
/*
OUTPUT:
[10, 25, 30, 50, 30, 35, 40, 50]
*/

/*
To get unique values from the result array
use below code:
*/
let uniqueRes1 = [...new Set(resArr1)];
console.log(uniqueRes1);
//["php", "java", "node", "mysql", "mongo", "firebase"]

let uniqueRes2 = [...new Set(resArr2)];
console.log(uniqueRes2);
//["php", "mysql", "next", "angular", "vue"]

let uniqueRes3 = [...new Set(resArr3)];
console.log(uniqueRes3);
//[10, 25, 30, 50, 35, 40]

/*
Final unique array in asc sort 
*/
console.log(uniqueRes1.sort());
console.log(uniqueRes2.sort());
console.log(uniqueRes3.sort());

/*
Final unique array in desc sort 
*/
console.log(uniqueRes1.reverse());
console.log(uniqueRes2.reverse());
console.log(uniqueRes3.reverse());
```
```js
/*

Array to iterable into more arguments
*/
let arr1 = [20, 40, 10, 15, 25, 75, 60, 90];
console.log(Math.max(arr1)); //NaN
console.log(Math.max(...arr1)); //90

console.log(Math.min(arr1)); //NaN
console.log(Math.min(...arr1)); //10
```
> **For/of**
```js
let arr1 = [10, 90, 20, 60, 30, 50];
for (let item of arr1) {
  console.log(item);
}

let arr2 = ["php", "asp", "jsp", "laravel", "node", "react"];
for (let item of arr2) {
  console.log(item);
}

let obj1 = [
  {name:"User1", skill:"mode", exp:5},
  {name:"User2", skill:"mongo", exp:8},
  {name:"User3", skill:"react", exp:12},
  {name:"User4", skill:"angular", exp:6}
];

for (let item of obj1) {
  //console.log(item);
  console.log(item.name, item.exp);
}
```
> **How may wahy to print a javascript array**
```js
let arr = [10, 90, 20, 60, 30, 50];

/*TYPE - 1*/
for (let item of arr) {
  console.log(item);
}

/*TYPE - 2*/
for (let i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}

/*TYPE - 3*/
arr.forEach((value, index) => {
   console.log(`index-${index} - value:${value}`);
});

/*TYPE - 4*/
arr.map((value, index) => console.log(`index-${index} - value:${value}`) );

/*TYPE - 5*/
arr.filter((value, index) => console.log(`index-${index} - value:${value}`) );
```
