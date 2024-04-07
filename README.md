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
