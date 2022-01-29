# Regex_Tutorial

This gist will give a tutorial on REGEX also known as regular expression.

## Summary

A Regex also known as regular expression defines a search pattern. There are different types expressions but I will be going over specifically an expression called "Matching an Email". The set of numbers, letters, and symbols below is what you call the Matching an Email expression. Essentially this expression validates that the user will be entering an email address whenever they are prompted. 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

The caret (^) anchor represents a string before the characters. Whereas the dollar sign ($) represents a string after the characters. The example above, you can see that there is a caret symbol before the expression and a dollar sign symbol after the expression. 

### Quantifiers

Quantifiers matches as many possible ways as possibles and they also set limitiations to the strings that can match your regular expression. Below include different types of quantifiers such as:

* (*) Matches the pattern zero or more times.
* (+) Matches the pattern one or more times.
* (?) Matches the pattern zero or one time.
* {}  Can provide three different ways to set limits for a match. 
  * { n } Matches the pattern ***exactly*** n numner of times.
  * ( n, } Matches the pattern at ***least*** n number of times.
  * {n, x } Matches the pattern from a ***minimum*** of n number of times to a ***maximum*** of x number of times.

For example, in our expression: `([a-z\.]{2,6})`
The strings inside the brackets indicates that this part of the email can include lowercase letters between a-z and/or the forward slash (\) and period (.). The two numbers inside the brackets indicates the there should be a minimum of 2 characters to a maximum of 6 characters. 

### Grouping Constructs

When grouping a certain section in the expression, you use (). These groupings are called subexpressions. In our expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, you can tell that the first group `([a-z0-9_\.-]+)` represents the username of an email address. You can tell that the @ symbol is not in the () because the @ symbol is mandatory and this allows the @ symbol to unaffected. This part of the expression `([\da-z\.-]+)` represents the domain name of the email and lastly, this part of the expression `([a-z\.]{2,6})` represents the domain. 

### Bracket Expressions

Any characters inside a bracket [] determines the range of characters that are need to match. For example, when you see a set of characters [a - z] in an expression, it makes anything characters between a to z, or when you see [1 - 9] means any characters between 1 to 9. For example, part of our expression includes `([a-z\.]{2,6})`. This is indicating that we can use any characters between a to z but also the forward slash (\) and period symbol(.). 

### Character Classes

Character classes defines a set of characters which any one of them can occur in an input of strings to fulfill a match. In this case, our expression `([\da-z\.-]+)` has the \d which means to match any single digit and since this subexpression has a + quantifiers, its indicating to match and single digit one or more times. 

### The OR Operator

The OR operator uses | which allows us to group characters within the subexpression. The expression we are using right now does not have OR Operator.

### Flags

Flags are often placed at the end of the expression after the second slash and adds additional functionality or limits for the regular expression. There are a total of six flags but below are three of the most common flags.

* Global Search (g): The regex should be tested against all possible matches in the string.
* Case Insensitive Search (i): The case should be ignored while attempting a match in a string.
* Multi-line Search (m): A multi-line input should be treated as multiple lines.

### Character Escapes

A Character escape is discribed as the backslash symbol in the expression. This is used when a character is being interpreted incorrectly. For example, we now know that a { is used to start a new quantifier but if you add a /{, this means that the expression is looking for a curly brace symbol instead. For example: 

`)\.(` the (.) means to match any character except the newline character. However, because there is a /. it means that the expression is looking for the actual period symbol. 

## Author

Chona Castillo

* [Github][github-chona]
* [GitHub Gist][github-gist]



[github-chona]: https://github.com/ChonaC
[github-gist]: https://gist.github.com/ChonaC/0a1fc3bc2e13dfc26b2efe9a8190edb7/edit