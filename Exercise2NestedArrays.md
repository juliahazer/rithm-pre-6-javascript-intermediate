# Rithm - Nested Arrays Exercises

## Part I



```javascript
rotate([1,2,3], 1) // [3,1,2]
rotate([1,2,3], 2) // [2,3,1]
rotate([1,2,3], 3) // [1,2,3]
```

* Write a function called rotate which takes an array and a number, and moves each element however many spaces the number is to the right. For the value at the end of the array, rotate should move it back to the beginning.


```javascript
var rotate = (arr, num) => {
	var amount = num % arr.length;
	for (var i = 0; i < amout; i++){
  		arr.unshift(arr.pop());
	} 
	return arr;
}

console.log(rotate([1,2,3], 3));
```

## Part II.

```javascript
makeXOGrid(1,4) 

/*/
[["X","O","X","O"]]
/*/

makeXOGrid(3,2) 

/*/
[["X","O"],["X","O"],["X","O"]]
/*/

makeXOGrid(3,3) 
/*/
[["X","O","X"],["O","X","O"],["X","O","X"]]
/*/
```

* Write a function called makeXOGrid which takes in two parameters, rows and columns, and returns an array of arrays with the number of values in each subarray equal to the columns parameter and the number of subarrays equal to the rows parameter. The values in the sub-arrays should switch between "X" and "O".

```javascript

makeXOGrid = (row,col) => {
  var obj = {
    "true": 'X',
    "false": 'O'
  };
  var bol = true;
  var grid = [];
  for (var i = 0; i < row; i++){
    var rowArr = [];
    for (var j = 0; j < col; j++){
      rowArr.push(obj[bol.toString()]);
      bol = !bol;
    }
    grid.push(rowArr);
  }
  return grid;
}

console.log(makeXOGrid(3,2));

```