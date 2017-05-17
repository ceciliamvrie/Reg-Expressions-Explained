# What Are Regular Expressions? 
Regular expressions might look terribly cryptic, but they prove to be very useful for processing 
strings of data. They form a seperate language that is part of Javascript as well as other programming
languages, and it is sort of required to get to know them if your hopes are matched to becoming a 
better programmer.

### Lets Create One
A regular expression is a type of object which can either be constructed by using the `RegExp` constructor
or written as a literal value by enclosing it with forward slash `/` characters. 

  `var re1 = new RegExp("abc");` or
  `var re2 = /abc/`

As you can see, both of these regular expression objects have the same **pattern** to them -meaning an 'a'
character followed by a 'b' and then a 'c' at the end. 

### Testing For Matches
It turns out that regular expressions have a pretty simple method called `test` where if you pass it a string, 
it will return a **Boolean** telling whether or not the string exists within the pattern in the expression.
  
  `console.log(/abc/.test("abcde"));
     //true`
     
  `console.log(/abc/.test("abdec"));
     //false`
     
A regular expression containing only letters represents that sequence of letters. If the sequence *abc* occures **anywhere** within the string, it will return true. Given that, even if those letters are still within the string, they must match 
that exact sequence or the test will return false. 

### Matching a Set of Characters
When we put an expression between two brackets, we make sure that part of the expression matches any character
in between that set of brackets, the sequence of the characters inside these brackets *doesn't matter*.
  
  `console.log([0, 1, 2, 3, 4, 5, 6, 7, 8, 9].test("dec 2nd, 1992"));
     //true`
     
  `console.log([0-9].test("dec 2nd, 1992"));
     //true`
     
Applying the `-` between the two digits accounts for every number between and **including** those digits.      
With that said, there are a number of common character groups that have their own shortcuts...

   - `\d` Any digit, or number
   - `\w` Any word character
   - `\s` Any whitespace character
   - `\D` Any character that is **NOT** a digit
   - `\W` Any character that is **NOT** a word character
   - `\S` Any non-whitespace character
   - `.` Any character except for newline
   
### Matching Groups of Elements 
You might know how to match single digits, but what if we want to match a group of numbers instead? 
When you put a `+` after something in a regular expression, it indicates that that element may be **repeated** 
more than once. 
  
  `console.log(/'\d+'/.test("'123'"));
     // → true`

   `console.log(/'\d+'/.test("''"));
     // → false`
     
There's a `*` character that you can use that has a similar meaning to the previous character, except it lets 
the pattern match to *zero* instead. 
Similarily, a `?` placed behind an element means that the pattern marked could be **optional**, or could
occur either *zero* or *more* times.

  `var neighbor = /neighbou?r/;
  console.log(neighbor.test("neighbor"));
    // → true
  console.log(/'\d*'/.test("''"));
    // → true`





     
   
