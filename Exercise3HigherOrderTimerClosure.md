# Rithm - Higher Order Functions, Timers, and Closures Exercises

### countdown function
```javascript

var countdown = (num) => {
  var count = setInterval(function(){
    num--;
    if (num === 0){
      clearInterval(count);
      console.log("DONE!");
    }
    else {
      console.log(num);
    }
  },1000);
}

countdown(4);

```

### randomGame function
```javascript

var randomGame = () => {
  var counter = 0;
  var num = setInterval(function(){
    var randomNum = Math.random();
    console.log(randomNum);
    counter++;
    if (randomNum > 0.75){
      clearInterval(num);
      console.log(counter);
    }
  },1000);
}

randomGame();

```

### isEven function
```javascript
var isEven = (num) => {
  return num % 2 === 0;
}

```

### isOdd function
```javascript
var isOdd = (num) => {
  return num % 2 !== 0;
}
```

### isPrime function
```javascript
var isPrime = (num) => {
  for (var i = num-1; i >=2; i--){
    if (num % i === 0){
      return false;
    }
  }
  return true;
}

```

### numberFact function
```javascript
var numberFact = (num, cb) => {
  return cb(num);
}

```

### find function
```javascript
function find(arr, cb){
  for (var i = 0; i < arr.length; i++){
    if (cb(arr[i])){
      return arr[i];
    }
  }
  return undefined;
}

console.log(find([8,11,4,27], function(val){return val === 5}));

```

### findIndex function
```javascript
function findIndex(arr, cb){
  for (var i = 0; i < arr.length; i++){
    if (cb(arr[i])){
      return i;
    }
  } 
  return undefined;
}

console.log(findIndex([8,11,4,27], function(val){return val >= 10}));
console.log(findIndex([8,11,4,27], function(val){return val === 7}));

```

### specialMultiply function
```javascript
function specialMultiply(a,b){
  if (arguments.length === 1){
    return function(b){
      return a * b;
    }
  }
  return a*b;
}

console.log(specialMultiply(3,4)); // 12
console.log(specialMultiply(3)(4)); // 12
console.log(specialMultiply(3)); // returns a function 

```

