# Javascript Interview Questions

> Q1)Difference between Var vs Let vs const
> 
* All the three are used to declare varaibles
* In let and Var we can reassign values whereas in const its not possible
```javascript
function add(){
  let a=0;
  var b=9;
  const c=90;
  //c=88 //Error cannot reassign value to const variable
  a=100;
  b=90
  console.log(a,b,c);
}
add();
```
* If we create an object using const then we can add new property to object
but directly assigning value to const is not possible
```javascript
function add(){
  const check={
    "name":"zeeshan",
    "age":25,
  }
  check.address="baramulla jammu and kashmir"
  console.log(check)
}
add();

Output:
{ name: 'zeeshan', age: 25, address: 'baramulla jammu and kashmir' }
```
* const and Let have block scope and var have function scope
```javascript
function add(){
  if(1===1)
  {
    var a=12;
    const b=13;
    let c=14;
    console.log(a,b,c)  //output 12 13 14
  }
      console.log(a) //outpput 12
      console.log(b) //error b is not defined
     console.log(c) //Error c is not defined
}
add();
```
Examples:
```javascript
function add(){
  var a="global"
  function sub(){
      var a="local"
        console.log(a)
  }
  sub();
  console.log(a)
}
add();

Output:

local
global
```
Example 2:
```javascript
function add(){
  var a="global"
   if(1){
      var a="local"
        console.log(a)
  }
  console.log(a)
}
add();

Output:

local
local
```
Example of let 
```javascript
function add(){
  let a="global"
   if(1){
      let a="local"
        console.log(a)
  }
  console.log(a)
}
add();

Output:

local
global
```
* var can be re-declared but let and const cannot
```javascript
function add(){
  var a=20;
   var a=60;
   console.log(a) //output 60
   -----------------------------
   let a=20;
   let a=60;
  console.log(a) //SyntaxError: Identifier 'a' has already been declared
  -------------------------------------
   const a=20;
   const a=60;
   console.log(a) //SyntaxError: Identifier 'a' has already been declared
  
}
add();
```
* var allows to access variables before initialization but Let can't

```javascript
function add(){
   console.log(a) //output undefined
   var a=20;
  //------------------
  console.log(a) //Error Cannot access 'a' before initialization
  let a=20;
  
}
add();
```
> Q2):What is Execution Context?
> 
> Everything in javaScript happens inside an Execution Context.
> JavaScript is synchronous(*executes one command at a time in a specific order*) single threaded language

<table>
<thead>
	Execution Context
</thead>
<tbody>
	<tr>
		<th>Memory component/Variable Environment</th>
		<th style="text-align: right">Code component/Thread of Execution</th>
	</tr>
	<tr>
		<td>Memory component variables and functions in a key value pairs</td>
		<td style="text-align: right">in Code component the whole js code is executed line by line </td>
	</tr>
	<tr>
		<td> key:value</br>
		    a:10;
		    add:()=:{}</td>
		<td style="text-align: right">in Code component the whole js code is executed line by line </td>
	</tr>
</tbody>
</table>



