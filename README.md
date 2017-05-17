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
  
  `console.log(/abc/.test("abcde"));`
  
     `//true`
     
  `console.log(/abc/.test("abxzy"));`
  
     `//false`
     
A regular expression containing only letters represents that sequence of letters. If *abc* occures **anywhere** within 
the string, it will return true.
