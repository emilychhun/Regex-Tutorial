# Regex Tutorial
Regular expressions, or regex for short, are one of the most powerful and applicable techniques in programming. Users can use regular expressions to searchspecifies a search pattern such as string searching algorithms for find and replace operations on strings or for input. They can be used in nearly every language, and they allow us to validate user input, perform search tasks, and even test code.  For this challenge, i wii use this regex to varyfing an email containing lettes, numbers, characters etc. It is important because some sites require you to have a requirement to meet in order to login, also validate the user login in.

## Summary
Everyone must have filled an online form at some stage, a form usually asks for information related to name, phone no, address, credit-card no etc.  In order to validate an user login in or an user they have to meet the matching criteria for an information it can contain letters, numbers, special characters and a domain name. In case you didn't provide information in the format specified by the form field or leave it empty, the message will appear and form cannot be submitted until you get it right.  This is done using a Javascript program on the client side, the Javascript program uses a regular expression pattern to test the input of each form field. For example, the following regular expression can be used to verify that user input is a valid email address:/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/.



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components

### Anchors
In regex, anchors are not used to match characters. Rather they match a position i.e. before, after, or between characters. To match start and end of line, we use following anchors: 1. Caret (^) matches the position before the first character in the string. 2. Dollar ($) matches the position right after the last character in the string. This is an anchors:  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ in this case it will be the "^" symbol starting before the regex is matching the begining of the string and the "$" which matching the end of the string the regex pattern is applied to. 

### Quantifiers
  Quantifiers are used to quantify how many times a part of your regular expression should be repeated.  Every time you want to repeat something in a regex (an individual character, a character class or a sub-expression) you can write a quantifier after it to specify how many times it should be repeated.  The following list shows some examples of the most common quantifiers: ?, *, +, {N}, {,N}, {N,}, {N,M}. For example, the regular expression /\d{4}/ matches a four-digit number. It is the same as /\d\d\d\d/.
  A quantifire can be greedy or lazy that is explained below.

* `a*a+a?`	-0 or more, 1 or more, 0 or 1
    * "+" Matches 1 or more of the preceding token.
    * "*" Matches 0 or more of the preceding token.
    * "?" Matches 0 or 1 of the preceding token, effectively making it optional.
    * "?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.

* `a{5}a{2,}`	 -Looks for exactly five, two or more
* `{2,6}`  	    -forces the input of characters between two & six characters long.
* `a+?a{2,}?`	 -match as few as possible
* `ab|cd`	    -match ab or cd

### OR Operator

* `|` Acts like a boolean OR. Matches the expression before or after the |.
It can operate within a group, or on a whole expression. The patterns will be tested in order. Just as in java will match either set of characters. It will look for this OR that.

### Character Classes
Character classes allows you to match  any symbol from a certain character set, and a character set is also called a character class. The best example to describe this is using a phone number being (805) 123-4567 but say a user doesnt type the "()" nor the "-" so you want to be able to match the phone. In my second group string ([\da-z\.-]+) we want to match any decimal digit from 0-9 followed by the character a-z to meet the email requirement, and last by period or hyphen.

### Flags
Flags are optional parameters that we can add to explain expression to make it search in a differnt way. Meaning "i" can ignore casing, "g" serves to searching to find all matches for a given expression inside a string, instead of stopping at the first match, "s" dotall makes the wild character "." match new lines aswell, "m" makes ^ and $ match the begininng and ending of every single line instead of the begining or ending of a string, "y" makes the expression start its searching from the index indicated in its last index property, and lastly "u" makes the expression assume individual characters as code points, not code units, and match 32 bit characters as well.


### Grouping and Capturing
Grouping use the "()" symbol they are used to create blocks of pattern, so you can apply repetitions or other modifiers to them. For my exmaple we have 3 grouping 1.) ^([a-z0-9_\.-]+)    2.) @([\da-z\.-]+)\.  3.)([a-z\.]{2,6})$ For group one we can see that its grouping multiple tokens together and creating a capture group for extracting a substring or using a backreference. Next its capturing a-z range, 0-9 range, - character then it escapes  the character using \. and again another - character, the same will apply for geroup two and three.

### Bracket Expressions
Bracket expressions are special characters that match one character out of a set of characters, just like regular character classes. it can match any charactr in the set thats inside if the [] brackets in my example its matcching a-z lowercase and range 0-9, _ and aswell as - character and the same will apply for the brackets in group two and three. 


### Greedy and Lazy Match
A greedy quantifier always attempts to repeat the sub-pattern as many times as possible before exploring shorter matches by backtracking. And a lazy quantifier always attempt to repeat the sub-pattern as few times as possible, before exploring longer matches by expansion. Exmaple of them in my code is the + symbol thats matching the previous token between one and unlimited times, as many times possible giving back as needed (greedy).


## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)


https://github.com/emilychhun/Regex-Tutorial
https://github.com/emilychhun
