# Regex Tutorial
Regex is short for regular expression, it is a sequence of characters that specifies a search pattern such as string searching algorithms for find and replace operations on strings or for input. The piece or regex i will be using will be for varyfing an email containing lettes, numbers, characters etc. It is important because some sites require you to have a requirement to meet in order to login, also validate the user login in.

## Summary
In order to validate an user login in or an user they have to meet the matching criteria for an email it can contain letters, numbers, special characters and a domain name. This will not only verify a returning user but allows the correct user in to the right account, there can be many Alex R in the workld but creating a unique email can help determin which Alex R is loggin in. As mentioned it will ensure email address contains only valid characters, verifies presense of a single character, and that a single period character separates the domain and the domain suffix. ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$



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
Anchors do not match any character, instead they match a position before, after, or between characters. In this case Anchors are at the start of the regex /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ in this case it will be the "^" symbol starting before the regex is matching the begining of the string and the "$" which matching the end of the string the regex pattern is applied to. 

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. An example of that would be "+" symbol matching min of 1 and a max of inifinity in the first group of string and aswell in the second group of strings. In my exmaple of string its matching/looking for in the first group the accepted criteria of numbers a-z lower case,  numbers 0-9, "underscore _" , ". period", and "- hyphen" allowed. Also {2,6}


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
