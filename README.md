###  JavaScript Variables

기본적으로 java의 변수와 비슷하다

```javascript
var person = "John Doe", carName = "Volvo", price = 200; //comma를 이용해 한줄에 여려 변수 선언 가능

var temp; //기본적으로 변수만 선언할 경우 value는 undefined이다


var carName = "Volvo";
var carName;  //같은 이름으로 변수를 다시 선언해도 값을 잃지 않는다.



```



##### JavaScript Dollar Sign $ , Underscore _

```javascript
//$도 일반적인 문자처럼 인식한다
var $$$ = "Hello World";
var $ = 2;
var $myMoney = 5;
//_도 일반적인 문자처럼 인식한다
var _lastName = "Johnson";
var _x = 2;
var _100 = 5;
```



##### Global Scope

함수 외부에 전역변수로 선언된 변수는 함수 내부에서도 사용 할 수 있는 전역변수가 된다.

```javascript
var carName = "Volvo";
// code here can use carName
function myFunction() {
  // code here can also use carName
}
```



##### Function Scope

 함수 내에 var 변수를 선언하게 되면 해당 블록내에서만 사용 할 수 있는 지역변수가 된다.

```javascript
// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```



##### Redeclaring Variables

전역변수를 지역변수에서 같은 이름으로 선언하고 값을 수정하면 전역변수의 값도 바뀐다

```javascript
var x = 10;
// Here x is 10
{
  var x = 2;
  // Here x is 2
}
// Here x is 2
```

전역변수와 같은 이름으로 let변수를 지역변수로 선언하고 수정해도 전역변수에는 영향을 받지 않는다.

```javascript
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10
```



##### Loop Scope

반복문에서의 var

```javascript
var i = 5;
for (var i = 0; i < 10; i++) {
  // some statements
}
// Here i is 10
```

반복문에서의 let

```javascript
let i = 5;
for (let i = 0; i < 10; i++) {
  // some statements
}
// Here i is 5
```



##### Global Variables in HTML

```javascript
var carName = "Volvo";
// code here can use window.carName
let carName = "Volvo";
// code here cannot use window.carName
```



##### Redeclaring

let이나 var가 변수로 선언되고 이후에 같은 이름으로 선언되는 경우 불가능하다

```javascript
var x = 2;       // Allowed
let x = 3;       // Not allowed

{
  var x = 4;   // Allowed
  let x = 5   // Not allowed
}
```

```javascript
let x = 2;       // Allowed
var x = 3;       // Not allowed

{
  let x = 4;   // Allowed
  var x = 5;   // Not allowed
}
```



let의 경우는 같은 Scope내에서는 재선언이 불가능하다!

```javascript
let x = 2;       // Allowed
let x = 3;       // Not allowed

{
  let x = 4;   // Allowed
  let x = 5;   // Not allowed
}
```

let은 다른 Scope에서는 재선언이 가능!!

```javascript
let x = 2;       // Allowed

{
  let x = 3;   // Allowed
}

{
  let x = 4;   // Allowed
}

```



##### Hoisting

var의 경우는 해당변수의 선언을 나중에 하는것이 가능하지만 let은 불가능하다

```javascript
carName = "Volvo";// 변수를 선언하지 않고 미리 값을 지정
alert(carName);// 해당 변수를 사용
var carName;//이후에 해당 변수의 선언
```

------



### String

```javascript
var carName1 = "Volvo XC60";  // Double quotes와 Single quotes를 사용하여 문자열을 저장
var carName2 = 'Volvo XC60';  
var answer1 = "It's alright";
var answer2 = "He is called 'Johnny'";
var answer3 = 'He is called "Johnny"';
```

String Length

```javascript
var sln = txt.length; //문자열의 길이를 반환한다.
```

 Escape Character

```javascript
var x = "We are the so-called \"Vikings\" from the north.";
//",',\ 를 사용하기 위해서 백슬래시를 해당 문자 앞에 추가하여 사용한다.
```



![image-20210323185148805](C:\Users\jgh03\AppData\Roaming\Typora\typora-user-images\image-20210323185148805.png) 

Breaking Long Code Lines

```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly!";
document.getElementById("demo").innerHTML = "Hello \
Dolly!";     // 해당 방법은 권장되지 않는다
document.getElementById("demo").innerHTML = "Hello " +
"Dolly!";    // 이방법을 사용하길 권장한다
```



Strings Can be Objects

```javascript
var x = "John";
var y = new String("John");
// typeof x will return string
// typeof y will return object

// (x == y) is true because x and y have equal values
// (x === y) is false because x and y have different types (string and object)
```



### String Methods

**String Length**

문자열의 길이를 반환

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```



**indexOf()**

해당하는 문자가 시작하는 index를 반환

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate");
```



**lastIndexOf()**

해당하는 문자의 마지막 index를 반환

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate");
```

* indexOf()와 lastIndexOf() 둘다 해당 문자열을 검색하지 못하면 -1을 반환하게 된다



**search()**

해당하는 문자열이 시작하는 첫번째 index를 반환

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.search("locate");
```

* search() 는 2번째로 시작하는 값을 받을 수 없다
* indexOf()는 정규표현식을 사용 할 수 없다



**slice()**

문자열에서 시작점과 끝점을 


------
### Arrays



Array를 생성

```javascript
var array_name = [item1, item2, ...];     //권장되는 Array생성 방법
var cars = new Array(item1, item2,  ...); //가능은 하지만 권장되지 않는다
```

자바 코드와 마찬가지로 인덱스는 0부터 시작된다



Array의 이름으로 모든 요소에 접근이 가능하다

```javascript
var cars = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = cars;
```



Array를 Object형식으로 생성이 가능하다

```javascript
var person = ["John", "Doe", 46];
var person = {firstName:"John", lastName:"Doe", age:46}; //이런 형식으로도 사용이 가능하다

// 아래의 형식으로도 사용이 가능하다
myArray[0] = Date.now;
myArray[1] = myFunction;
myArray[2] = myCars;
```



Array의 속성

```
var x = cars.length;   // cars라는 Array의 요소의 갯수를 반환하여 준다
var y = cars.sort();   // Array를 정렬
```



Array의 요소를 반복문으로 출력

```javascript
var fruits, text, fLen, i;
fruits = ["Banana", "Orange", "Apple", "Mango"];
fLen = fruits.length;

text = "<ul>";
for (i = 0; i < fLen; i++) {
  text += "<li>" + fruits[i] + "</li>";
}
text += "</ul>";

/////// 다른 방법 For-each/////////////////////////

var fruits, text;
fruits = ["Banana", "Orange", "Apple", "Mango"];

text = "<ul>";
fruits.forEach(myFunction);
text += "</ul>";

function myFunction(value) {
  text += "<li>" + value + "</li>";
}
///////////// 다른 방법

<!DOCTYPE html>
<html>
<body>
<h2>JavaScript Arrays</h2>
<p id="demo"></p>
<script>
var fruits, text;
fruits = ["Banana", "Orange", "Apple", "Mango"];
text = "<ul>";
fruits.forEach(function(item, index, arr2){
    text += "<li>" + item + "</li>";
})
text += "</ul>";
document.getElementById("demo").innerHTML = text;
</script>
</body>
</html>

```



Array의 요소 추가

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Lemon");    // Array의 뒷 부분에 추가된다
///////
fruits[fruits.length] = "Lemon";    // 마지막 인덱스에 값을 추가할수도 있다
```



### Array Methods

.toString()

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();
```

.join()

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * ");
///////////
Result:
Banana * Orange * Apple * Mango
```



Popping & Pushing

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.pop();      // x는 망고가 되고 fruits배열에서 망고는 사라진다
/////////////////////////////////////////////////
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.push("Kiwi");   // x에는 추가된 이후 요소의 갯수가 들어가게 된다. 5
```

Shifting

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.shift();    // 왼쪽으로 한번 쉬프트되며 x에 바나나가 들어간다, 배열의 요소는 1개줄어듦
////////////////////////
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon");    // 오른쪽으로 쉬프트되며 배열에 레몬을 추가, fruits.unshift("Lemon")의 반환값은 추가된 이후 배열의 크기가 된다 5
```

delete

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0];   // 해당 인덱스의 값이 undefined가 된다 배열의 크기가 줄어드는건 아니다
```

Splicing an Array

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");
//첫번째 인자는 어느 인덱스에 추가할것인가
//두번째 인자는 첫번째 인덱스로부터 몇개의 요소를 제거할 것인가
//이후의 인자들은 추가될 요소
//return값은 제거된 요소들을 갖는다
```

Merging

```javascript
var myGirls = ["Cecilie", "Lone"];
var myBoys = ["Emil", "Tobias", "Linus"];
var myChildren = myGirls.concat(myBoys);   // myGirls와 myBoys를 병합한다, 여러개의 인자를 넣을수 있다.
```

- concat() 메소드는 새로운 배열을 반환하므로 기존의 배열에 영향을 주지 않는다.

Slicing an Array

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(3);// 해당 인덱스 이전의 값을 제외한 배열을 반환한다
/////////////////////////////////////////////
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1, 3); // 시작지점, 끝지점+1을 넣어서 사용한다 //"Orange", "Lemon"
```





