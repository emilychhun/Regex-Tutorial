# Regex Tutorial
Regular expressions, or regex for short, are one of the most powerful and applicable techniques in programming. Users can use regular expressions to search specifies a search pattern such as string searching algorithms for find and replace operations on strings or for input. They can be used in nearly every language, and they allow us to validate user input, perform search tasks, and even test code.  For this challenge, i wii use this regex to varyfing an email containing lettes, numbers, characters etc. It is important because some sites require you to have a requirement to meet in order to login, also validate the user login in.

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
  With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. Simply place the characters you want to match between square brackets. If you want to match an a or an e, use [ae]. You could use this in gr[ae]y to match either gray or grey. A character class matches only a single character. gr[ae]y does not match graay, graey or any such thing. The order of the characters inside a character class does not matter. The results are identical.
The following are additional examples of character classes that are not found in our example:
* A negated set contains a caret first thing within the square brackets `[^ABC]` and matches any character that is not in the set.
* A `.` will match any character except line breaks. The `.` in our example actually refer to actually periods, and are not a character class.
* Match any `[/s/S]` will match any character.
* Word `/w` will match any word.
* Not word `/W` will match any character that is not a word.
* Digit `/d` matches any number.
* Not digit `/D` will match any character that is not a number.
* Whitespace `\s` will match any character that leaves whitespace (spaces, tabs, line breaks, etc.).
* Not whitespace `\S` will match any character that is not a whitespace character.

### Flags
  Flags are optional parameters that we can add to explain expression to make it search in a differnt way. Meaning "i" can ignore casing, "g" serves to searching to find all matches for a given expression inside a string, instead of stopping at the first match, "s" dotall makes the wild character "." match new lines aswell, "m" makes ^ and $ match the begininng and ending of every single line instead of the begining or ending of a string, "y" makes the expression start its searching from the index indicated in its last index property, and lastly "u" makes the expression assume individual characters as code points, not code units, and match 32 bit characters as well.


### Grouping and Capturing
   Grouping constructs delineate the subexpressions of a regular expression and capture the substrings of an input string. You can use grouping constructs to do the following:  1. Match a subexpression that is repeated in the input string. 2. Apply a quantifier to a subexpression that has multiple regular expression language elements. For more information about quantifiers, see Quantifiers. 3. Include a subexpression in the string that is returned by the Regex.Replace and Match.Result methods. 4. Retrieve individual subexpressions from the Match.Groups property and process them separately from the matched text as a whole. 

  You can access captured groups in four ways: A. By using the backreference construct within the regular expression. The matched subexpression is referenced in the same regular expression by using the syntax \number, where number is the ordinal number of the captured subexpression. B. By using the named backreference construct within the regular expression. The matched subexpression is referenced in the same regular expression by using the syntax \k<name>, where name is the name of a capturing group, or \k<number>, where number is the ordinal number of a capturing group. A capturing group has a default name that is identical to its ordinal number. For more information, see Named matched subexpressions later in this topic. C. By using the $number replacement sequence in a Regex.Replace or Match.Result method call, where number is the ordinal number of the captured subexpression. D. Programmatically, by using the GroupCollection object returned by the Match.Groups property. The member at position zero in the collection represents the entire regular expression match. Each subsequent member represents a matched subexpression. For more information, see the Grouping Constructs and Regular Expression Objects section.

### Bracket Expressions
  A bracket expression is a list of characters enclosed by ‘[’ and ‘]’. It matches any single character in that list. If the first character of the list is the caret ‘^’, then it matches any character not in the list, and it is unspecified whether it matches an encoding error. For example, the regular expression ‘[0123456789]’ matches any single digit, whereas ‘[^()]’ matches any single character that is not an opening or closing parenthesis, and might or might not match an encoding error.  Within a bracket expression, a range expression consists of two characters separated by a hyphen. It matches any single character that sorts between the two characters, inclusive. In the default C locale, the sorting sequence is the native character order; for example, ‘[a-d]’ is equivalent to ‘[abcd]’. In other locales, the sorting sequence is not specified, and ‘[a-d]’ might be equivalent to ‘[abcd]’ or to ‘[aBbCcDd]’, or it might fail to match any character, or the set of characters that it matches might even be erratic. To obtain the traditional interpretation of bracket expressions, you can use the ‘C’ locale by setting the LC_ALL environment variable to the value ‘C’.

## Author

 Find me on GitHub: [emilychhun](https://github.com/emilychhun)
 <br />

  Email me with any questions: emily_chhun23@yahoo.com
  <br />
  
  Repo Link: [repo-link](https://github.com/emilychhun/Regex-Tutorial)
  <br />
 
 Link Gist: [Link-Gist](https://gist.github.com/emilychhun/f07331ac54644f285cd80c9e0fb4f41f)
 <br />


