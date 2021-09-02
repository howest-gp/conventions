# JavaScript codeerstandaarden en naamgevingsconventies

## 1. Gebruik van `var`, `let` en `const` zoals hieronder beschreven.
De scope van een variabele kan **lokaal** of **globaal** zijn. Globale variabelen kunnen op willekeurige plaatsen in het programma worden aangeroepen. Lokale variabelen worden in een functie of een codeblok gedeclareerd. Hun bereik beperkt zich tot deze functie of
codeblok.

Voor de duidelijkheid maken we de volgende afspraken:
* `var` gebruiken we enkel voor variabelen die globaal gebruikt worden, doorheen gans je script dus.
 * `let` gebruiken we enkel voor variabelen die binnen een bepaalde function of code block (if, lus …) gebruikt wordt
* `const` behouden we voor waarden die nooit gewijzigd worden

|| `var` | `let` | `const` |
|---|---|---|---|
|gedeclareerd **buiten** een function| globaal | globaal | globaal |
|gedeclareerd **buiten** een code block `{ ... }` | globaal | globaal | globaal |
|gedeclareerd **binnen** een code block `{ ... }`| globaal | lokaal | lokaal |
|gedeclareerd **binnen** een function| lokaal | lokaal | lokaal |

## 2. Gebruik de Hongaarse notatie wanneer de variabelen HTML-elementen bevatten.
```javascript
//correct
var btnSubmit;
btnSubmit = document.getElementById("submit");

//fout
var submit;
submit = document.getElementById("submit");

```
> **Waarom?**
>
> Dit verhoogt de leesbaarheid van je code door duidelijk te maken dat de variabele verband houdt met de GUI.

## 3. Werk in strict mode.
Noteer steeds op de eerste lijn van je JavaScript-file dat in je in strict mode wil werken.

```javascript
"use strict"

var definedVariale;

definedVariable = "this works";
undefinedVariable = "No var, let or const keyword used. Normally this would be allowed, but not in strict mode.";
```

> **Waarom?**
>
> Werken in strict mode verlaagt de kans op fouten. Wanneer een niet-gedeclareerde variabele wordt aangesproken in niet-strict mode, dan wordt er een `var`-variabele aangemaakt. Dit kan het debuggen soms onnodig vermoeilijken bij, bijvoorbeeld, tikfouten.

## 4. Declareer variabelen zo veel mogelijk aan het begin van hun scope.

```javascript
//correct
function printStudentInfo() {
  let teacherName;
  let studentName;
  let divTitle;

  teacherName = "Maxim";
  studentName = "Bart";
  divTitle = document.getElementbyId("title");
  
  
  divTitle.innerText = studentName + " volgt les bij " + teacherName;
}

// ... eventueel ook correct
function printStudentInfo() {
  let teacherName = "Maxim";
  let studentName = "Bart";
  let divTitle = document.getElementbyId("title");
  
  divTitle.innerText = studentName + " volgt les bij " + teacherName;
}

//fout
function printStudentInfo() {
  let teacherName;
  teacherName = "Maxim";
  let divTitle = document.getElementbyId("title");
  let studentName;
  studentName = "Bart";
  divTitle.innerText = studentName + " volgt les bij " + teacherName;
}
```

> **Waarom?**
>
> Dit verhoogt de leesbaarheid.

## 5. Gebruik expanded syntax.
* elke lijn JavaScript-code begint op een nieuwe lijn
* De openingsaccolade (`{`) van een block begint op dezelfde lijn van het statement in kwestie
* de sluitende accolade (`}`) begint op een nieuwe lijn

```javascript
//correct
function myFunc() {
  console.log('Hello!');
};

//fout
function myFunc() { console.log('Hello!'); };
```

> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid van je code.

## 6. Beperkte de lengte van een lijn tot +- 80 karakters en splits ze op indien nodig.
```javascript
//correct 
let tommyCat = 'Said Tommy the Cat as he reeled back to clear whatever foreign '
+ 'matter may have nestled its way into his mighty throat. Many a fat alley rat '
+ 'had met its demise while staring point blank down the cavernous barrel of '
+ 'this awesome prowling machine.';

//ook correct (met template literal)
let tommyCat = `Said Tommy the Cat as he reeled back to clear whatever foreign matter may have nestled its way into his mighty throat. Many a fat alley rat had met its demise while staring point blank down the cavernous barrel of this awesome prowling machine.`;

//fout
let tommyCat = 'Said Tommy the Cat as he reeled back to clear whatever foreign matter may have nestled its way into his mighty throat. Many a fat alley rat had met its demise while staring point blank down the cavernous barrel of this awesome prowling machine.';

```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid. Bij meer dan 80 karakters bestaat de kans dat je horizontaal moet beginnen scrollen.

## 7. Gebruik spaties tussen operators, operanden, parameters, enzovoort.
```javascript
//correct
if(dayOfWeek === 7 && weather === 'sunny') {
  goOnTrip('beach', 'car', ['ice cream', 'bucket and spade', 'beach towel']);
}

//fout
if(dayOfWeek===7&&weather==='sunny'){
  goOnTrip('beach','car',['ice cream','bucket and spade','beach towel']);
}
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid van je code.

## 8. Elk statement eindigt met een `;`.
```javascript
//correct
alert("Hello world!");

//fout
alert("Hello world!")

```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid van je code. Door een ; te noteren expliciteer je namelijk waar het statement eindigt.

## 9. Er komt géén spatie voor keywords van controlestructuren, functies of lusstructuren, maar wel erna.
```javascript
//correct
if(credits > 10) {
  
}

function myFunction() {

}

//fout
if (credits > 10){
  
}

function myFunction(){
  
}
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid van je code.

## 10. Commentaren komen boven de code in kwestie.
```javascript
//correct
function myFunc() {
  // Output the string 'Hello' to the browser's JS console
  console.log('Hello');
  // Create a new paragraph, fill it with content, and append it to the <body>
  let para = document.createElement('p');
  para.textContent = 'My new paragraph';
  document.body.appendChild(para);
}
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid van je code.

## 11. Gebruik betekenisvolle namen in lowerCamelCase voor variabelen.
```javascript
//correct
let playerScore = 0;

let speed = distance / time;

//fout
let thisIsaveryLONGVariableThatRecordsPlayerscore345654 = 0;

let s = d/t;
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid van je code.

> **Opmerking**
>
> Het is wel toegelaten om variabelenamen zoals `i`, `j`, ... te gebruiken in lussen.

## 12. Gebruik betekenisvolle namen lowerCamelCase voor functies.
```javascript
//correct
function sayHello() {
  alert('Hello!');
};

//fout
function SayHello() {
  alert('Hello!');
};

function notVeryObviousName() {
  alert('Hello!');
};
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.

## 13. Gebruik `let` wanneer een variabele een nieuwe waarde zal toegewezen krijgen. 
```javascript
//correct
let myAge = 40;
myAge++;
console.log('Happy birthday!');
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.

## 14. Gebruik `const` wanneer de variabele niet zal wijzigen.
```javascript
//correct
const myName = 'Chris';
console.log(myName);

//zal een error opgooien
const myAge = '40';
myAge++;
console.log('Happy birthday!');
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.

## 15. Schrijf de ternary operators op één lijn.
```javascript
//correct
let status = (age >= 18) ? 'adult' : 'minor';

//fout
let status = (age >= 18)
  ? 'adult'
  : 'minor';
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.

## 16. Verkies strikte vergelijkingsoperator.
```javascript
//liever dit ...
name === 'Chris';
age !== 25;

//... dan dit
name == 'Chris';
age != 25;

```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie. Bovendien verlaagt dit problemen bij vergelijkingen waar geen rekening gehouden wordt met het datatype, vgl..: <br> `"14" == 14` evalueert naar `true`, maar `"14" === 14` evalueert naar `false`.

## 17. Verkies shortcuts voor booleaanse tests.
```javascript
//verkies dit ...
if(!isAdult) {

}

//... in plaats van dit ...
if(isAdult === false) {

}

```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.

## 18. Verkies template literals in plaats van string literals.
```javascript
//verkies dit ...
let myName = 'Chris';
console.log(`Hi! I'm ${myName}!`);

//... in plaats van dit ...
let myName = 'Chris';
console.log('Hi! I\'m' + myName + '!');
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.

## 19. Gebruik `.textContent` in plaats van `.innerHTML`.
```javascript
//correct
let text = 'Hello to all you good people';
const para = document.createElement('p');
para.textContent = text;

//fout
let text = 'Hello to all you good people';
const para = document.createElement('p');
para.innerHTML = text;
```
> **Waarom?**
>
> `.textContent` is efficiënter en minder vatbaar voor fouten dan `.innerHTML`. Bovendien kan `.textContent` een [XSS-aanval](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting) voorkomen.

## 20. Geef een switch-statement altijd een `default` case ook al lijkt die overbodig.
```javascript
//correct
let expr = 'Papayas';
switch(expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Papayas':
    console.log('Papayas are $2.79 a pound.');
    break;
  default:
    console.log('Sorry, we are out of ' + expr + '.');
}

//fout
let expr = 'Papayas';
switch(expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Papayas':
    console.log('Papayas are $2.79 a pound.');
    break;
}

```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verlaagt de kans op fouten.

## 21. Verkies het declareren van een functie boven een functie-expressie.
```javascript
//verkies dit ...
function sum(a, b) {
  return a + b;
}

//... boven dit
let sum = function(a, b) {
  return a + b;
}
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.

## 22. Gebruik literals in plaats van constructors voor het maken van objecten of arrays.
```javascript
//correct
let myObject = {};
let myArray = [];

//fout
let myObject = new Object();
let myArray = new Array(length);

```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie.

## 23. Verkies de `.push` methode om elementen toe te voegen aan een array.
```javascript
//correct
const pets = [];
pets.push('cat');

//fout
const pets = [];
pets[pets.length] = 'cat';

```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.


# Referenties
* https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Code_guidelines/JavaScript
* https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Code_guidelines/General




