# Using Regex in JS

```javascript
/* CREATING A REGEX IN JS */
const regex1=/hello/ig;//ig -> case insensitive, global
const regex2= new RegExp('hello','ig');
const regex3=new RegExp(/hello/,'ig');
const regex4=new RegExp(/hello/ig);

const testString='Hello world, HELLO again!';
console.log(regex1.test(testString));//true
console.log(testString.match(regex1));//['Hello','HELLO']
```
***

```javascript
/* MATCH A SINGLE CHAR */
const regex=/hu./;//matches hu_

/* MATCH A SET OF CHARS */
const regex=/b[uia]/;//matches 'bug','big','bag'

/* MATCH A RANGE OF CHARS */
const regex=/[a-z]/;//matches any char a through z
const regex=/[2-6]/;//matches 2,3,4,5,6
const regex=/[1-5a-m]/;

/* NEGATING SELECTION */
const regex=/[^0-9a-m]/;//matches everything except numbers and a-m alphabets

/* MATCH A SEQUENCE 1 OR MORE TIME */
const regex=/s+/;//matches s,ss,sss...

/* MATCH A SEQUENCE OCCURING 0 OR MORE TIMES */
const regex=/go*/;//matches g,go,goo,gooo,...

/* 
LAZY MATHCING -> FINDS SMALLEST PATTERN THAT MATCHES THE REGEX
GREEDY MATCHING -> FINDS THE LARGEST PATTERN THAT MATCHES THE REGEX (DEFAULT BEHAVIOUR) 
*/
const testString='<h1>Hello world</h1>';
const regex=/<.*?>/;//? -> do lazy matching, Matches '<h1>',</h1>; Greedy would match to '<h1>Hello world</h1>' 

/* MATCHING BEGINNING AND END STRING PATTERNS */
const regex=/^He/;
const regex=/ld$/;

/* MATCHING ALL LETTERS AND NUMBERS */
const regex=/\w/;//matches a-z,A-Z,0-9 and _
const regex=/\W/;//matches /[^\w]/

/* MATCHING ALL NUMBERS */
const regex=/\d/;//matches 0-9
const regex=/\D/;//mathes /[^\d]/

/* QUANTITIY SPECIFIERS -> MATCHING NUMBER OF CHARS */
const regex=/[a-z]{2,}/;//matches occurence of a-z 2<->infinite times
const regex=/a{4}/;//matches 'aaaa'

/* MATCHING WHITESPACE CHAR */
const regex=/\s/;
const regex=/\S/;//matches all non whitespace chars

/* MATCH 0 OR 1 OCCURENCE */
const regex=/favou?rite/;//matches favourite and favourite

/* LOOKAHEADS */
const positiveLARegex=/q(?=u)/;//returns true for any string starting with 'q' and having a 'u' anywhere in it
const negativeLARegex=/q(?!u)/;//returns true for any string starting with 'q' and NOT having a 'u' anywhere in it

/* CAPTURE GROUPS */
const regex=/(/w+)\s\1/
```
