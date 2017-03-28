# Rithm - Debugging Exercises

## Part I

* throw keyword: allows you to throw an error/exception of your choice
* finally keyword: last condition of try/catch - code runs regardless of if error or not
* ReferenceError - variable never declared; TypeError - occurs when JavaScript is unable to perform a certain operation on a data type (e.g., try to run a variable as function not a function or access sub properties of object undefined)
* Snippets - go to Sources tab
* Exception: error that occurs in your program - caught exceptions are errors that are evaluated in a try/catch block
* Catch errors using a try /catch block

```javascript
	try {
	    console.log(test);
	}
	catch(e){
	    console.log(“Test is undefined: “ + e);
	}
```

1. ReferenceError (need to add var keyword)
2. TypeError (define the function displayInfo)
3. TypeError (try to assign a property of foo on undefined)
4. ReferenceError (define thing in global scope)

## Part II.

1. i < 5 (will never run)
2. num % 2 === 0 (don’t want assignment in condition)
3. add semi-colons!
4. evenNumbers.push(numbers[i]); and numbers[i]%2 === 0; and return at very end