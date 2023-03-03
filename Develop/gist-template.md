# RegEx for email verification

Regex is a truncated monicker for the term "regular expression" which is an opbjec used in programming languages that can detect patterns in strings. This project tutorial will explain a basic REgex implementation for validating email in JavaScript.

## Summary

This project tutorial will tackle the Regex object syntax as well as Regex methods. WE will be examining email formats in Javascript as they are commonly recognized patterns in strings, constituted by a triune combination of characters called the prefix, the "@," and the domain as illustrated in the following example:

spicytacos77@gmail.com

## Table of Contents

- [Elements](#elements)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Author](#author)
- [References and Attributions](#references-and-attributions)

## Regex Elements

A Regex is an object composed of constraints to be imposed on a string that makes that string conform to a pattern that is easily searched.

A Regex can be defined in JavaScript by using "const" or "let," then defining the expression:

const reg_email = /^\w+([\.-]?\w+)\*@\w+([\.-]?\w+)\_(\.\w{2,3})+$/ ;

let reg*email = new RegExp(' ^\w+([\.-]?\w+)*@\w+([\.-]?\w+)\_(\.\w{2,3})+$ ');

We can tehn test for a conforming method by the following:

let validEmail = reg_email.test(input_email);

Here validEmail is TRUE when the input_email string conforms to the expected rule we establisehd with the RegEx.

### Anchors

Anchors within a RegEx define the start and end points for the string pattern. "^" defines the beginning and "$" defines the end.

### Quantifiers

Quantifiers within a RegEx define the range of characters in the string that will be matched. Quantifiers include \*, +, ?, and {num1,num2}.

The \* Quantifier is a "wildcard" that allows any number of characters to be matched.
The + Quantifier matches against one or more characters.
The ? Quantifier matches the expression 0 or 1 times.
The {num1.num2} Qualifier defines a range for the length of instances between number1 and number2.

### Character Classes

Character classes establish the character type or character that is being searched:

. : Looks for any character except a newline

\w, \d, \s : Looks for a word character (alphanumeric or underscore) regardless of case, a digit 0-9 , and whitespace respectively. _infra_ 2.

\W, \D, \S : the negation of \w, \d, \s

[abc] : includes a letter which is a,b, or c

[0-9] : A digit between 0 and 9.

[.-] : includes any letter or hyphen.

### Grouping

Grouping constructs are used to define sub-expressions within the regular expression. The sub-expression in the example is between the "(" and or the "[","]" brackets. () collect sub-expressions and [] are used to find a range of characters using hyphens, e.g. [.-] for a period and a hyphen. The example reg_email contains three grouping constructs and two nested sub-expressions.

/^ \w+ ([.-]? \w+ ) _@ \w+ ( [ .- ]
? \w+ ) _ ( \. \w{2,3} ) +$/

### Bracket Expressions

Bracked expressions in this email validation includes character sets of [a-z0-9_\.-] that matches any letter a-z and is case senstive, matches character 0-9 and matches the characters "\_" , "-" , and "."; [\da-z\.-], which matches a single digit from 0-9, any character a-z and is case senstive, and the characters "." and "-".; [a-z\.] matches any character a-z and is case senstive and matches the character ".".

### Greedy and Lazy Match

GReedy matches match as much as possible and is written as <.+ This plus is greedy in that it matches the preceding character, the dot, and will match everything across the string until the end.

Lazy quantifiers help reign-in the greedy + by placing the ? after it as <.+? this causes the enging to backtrack and expand its search.

### Back-references

Backreferences match the same text as previously matched by a capturing group. _infra_ 1.

### Look-ahead and Look-behind

Look-ahead, e.g. (?=foo) asserts that what immediately _follows_ the current position in the string is _foo_.
Look-behind, e.g. (?<=foo) asserts that what immediately _precedes_ the current position in the string is _foo_.

## Author

Jeremiah Chesley, Et.al.

## References and Attributions

(1) Regular-expressions.info, https://www.regular-expressions.info/backref.html
(2) REgular Expressions (Regex), https://www3.ntu.edu.sg/home/ehchua/programming/howto/Regexe.html
(3) MDN Web Docs - Regular Expressions, https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
