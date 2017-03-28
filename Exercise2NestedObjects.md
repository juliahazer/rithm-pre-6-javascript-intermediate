# Rithm - Nested Objects Exercises

## Part I



```javascript
var nestedData = {
    innerData: {
    order: ["first", "second", "third"],
    snacks: ["chips", "fruit", "crackers"],
    numberData: {
        primeNumbers: [2,3,5,7,11],
        fibonnaci: [1,1,2,3,5,8,13]
    },
    addSnack: function(snack){
        this.snacks.push(snack);
        return this;
    }
  }
}
```

* Using a for loop, console.log all of the numbers in the primeNumbers array.
* Using a for loop, console.log all of the even Fibonnaci numbers.
* Console.log the value "second" inside the order array.
* Invoke the addSnack function and add the snack "chocolate".
* Inside of the addSnack function there is a special keyword called this. What does the word this refer to inside the addSnack function?

```javascript
var prime = nestedData.innerData.numberData.primeNumbers;
for (var i = 0; i < prime.length; i++){
  console.log(prime[i]);
}

var fib = nestedData.innerData.numberData.fibonnaci;

fib.filter(function(el){
  return el % 2 === 0;
}).forEach(function(el){
	console.log(el)
});

console.log(nestedData.innerData.order[1]);

nestedData.innerData.addSnack('chocolate');

//this refers to the innerData obj
```

## Part II.

```javascript
var nestedObject = {
  speakers: [{name:"Elie"},{name:"Tim"},{name:"Matt"}],
  data: {
    continents: {
      europe: {
        countries: {
          switzerland: {
            capital: "Bern",
            population: 8000000
          }
        }
      }
    },
    languages: {
      spanish: {
          hello: "Hola"
      },
      french: {
          hello: "Bonjour"
      }
    }
  }
}
```

* Write a function addSpeaker to add a speaker to the array of speakers. The speaker you add must be an object with a key of name and a value of whatever you'd like.

* Write a function addLanguage that adds a language to the languages object. The language object you add should have a key with the name of the language and the value of another object with a key of "hello" and a value of however you spell "hello" in the language you add.

* Write a function addCountry that adds a European country to the countries object (inside of the continents object, inside of the countries object). The country you add should be an object with the key as name of the country and the value as an object with the keys of "capital" and "population" and their respective values.

```javascript

var addSpeaker = (speakerName) => {
  nestedObject.speakers.push({
    name: speakerName
  });
}

addSpeaker("Julia");

var addLanguage = (nameLang, helloText) => {
  nestedObject.data.languages[nameLang] = {
    hello: helloText
  }
}

addLanguage('english', "Hi");

var addCountry = (country,cap,pop) => {
  	nestedObject.data.continents.europe.countries[country] = {
    	capital: cap,
    	population: pop
  };
}

addCountry("france", "Paris", 100000);

console.log(nestedObject);

```