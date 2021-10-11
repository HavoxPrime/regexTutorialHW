# Regex Tutorial

    On your daily formidable journey in computer programming, while wading through blocks of various computer language you may have encountered code with an appearnce of `/(?:\d{3}|\(\d{3}\))([-\/\.])\d{3}\1\d{4}/`.  This type of computer 'hyroglyph' has a specific meaning and can be quite useful when used properly.  Although looking like digitial scribble, this type of code is refered to as a Regular Expression (Regex).  Regular expressions are patterns that are designed to sync up with specific character combinations in string, the primitive data type.  Regex is regularly enlisted to help parse user input and make certain that is in a certain format depending on the input's necessary parameters.  Regex is also very helpful in searching documents and files for specific sections of code that need to be located.

## Summary

     This tutorial will dive into the Regex Email expression of `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,5})$/`.  This expression is able to match email address formats needed for verification.  The formatting is what we have come to expect of all email address; examples of this format would be first.lastName123@email.com, anyword@domain.com, and so on.  The following sections of this piece will examine the various compents of a Regular Expression and how they are used.

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

    An anchor in Regex does not match any characters entered into the input field by the user.  Anchors are a group of tokens used in Regex to match the position of a character, either what is before, after or in between.  According to the website[Rex Egg](http://www.rexegg.com/regex-anchors.html), 'Anchors assert that the engine's current position in the string matches a well-determined location: for instance, the beginning of the string, or the end of a line.' These two instances are the exact anchors we will be examing in this tutorial. The two anchors used in our email example are `^` (beginning of the string) and `$` (end of the line).  The `^` informs the processing engine that we are looking to find a complex pattern at that specific location.  The `$` lets us signify that we are looking for a specific matched pattern at the end of our string.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,5})$/`

### Quantifiers

    Quantifiers in Regular Expressions are used to indicate to the engine the number of characters or expressions to match or should be repeated. "Quantifiers match a number of instances of a characher, group, or character class in a string,' according to [JavascriptTutorial.net](https://www.javascripttutorial.net/regular-expression-quantifiers/).  There are few notations that specify a quantifier in Regex.  Quanitifiers prove a vital part of our search return gather and below we have a chart of the quantifiers from the JavascriptTutorial.net webpage.  Please note that the `n` is refering to a numerical value, 'how many of something', and the `m` is refering to the range.

Quantifier: | Description: \* | Match zero or more times. + | Match one or more times.
? | Match zero or one time.
{ n } | Match exactly n times.
{ n ,} | Match at least n times.
{ n , m } | Match from n to m times.

The example of our email Regex (`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,5})$/`) uses the `+` symoble twicem where we are able to match all alphanumeric characters one or more times and our end of the email {2,5} is parcing everything that comes after our domain name. We do not want any numeric characters after out `.` so we enlist the {}. We are looking for at least 2 alphabet characters and up to 5 characters to end out email. Anything six or more, or of just one, would not pass our validation.

### Grouping Constructs

    There are times where a Regex expression is made of multiple subexpressions.  In the instance of a username there is typically only one expression since there are not 'literal characters' that you are parsing the input for.  The user is able to create their name as they see fit.  However in out email instance, we have a much more rigid design.  We will be searching for the divided 'grouping contruct' subexpressions that are divided by the literal charachter `@` and the literal character `.`(example user`@`email`.`com).  Emails have three subexpressions based on this design, `([a-z0-9_\.-]+)`, `([\da-z\.-]+)`, and `([a-z\.]{2,5})`, respectively.

### Bracket Expressions

A Bracket Expression is a list of characters enclosed within a set of square brackets, `[` and `]` respectively. If searching for a specific letter or a specific number you would place that character withing a `[]` square set of brackerts. You may use a hyphen inside of character class to indicate a range. A character class of `[0-9]` would request a range of any integer between the number zero and the number nine (0, 1, 2, 3, ... 9). Character Classes are one of the most prolific features of regular expressions. Using Character Classes helps a user find misspelled words easily and help find an indentifier in a programming language. Our example (`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,5})$/`) has three sets of `[]`. Our first is for our user's name to their email looking for any combination of alphanumeric characters, `[a-z0-9_\.-]`. The second would be after out `@` symbol ([\da-z\.-]) and the third is after our `.` ([a-z\.]). The last two set up the parameters for any domain name we would be expecting.

### Character Classes

    Character Classes are a special notation used in Regex that match any symbol from a certain set.    The most common used are `\d` (signifing 'digit'), `\s` (standing for 'space'), `\w` (representing 'word").  We are breaking down the character into these classes inorder to expedite our search and narrow the results.  When looking for an entire phone number, for example, we would use the `\d` to try to pullin a collection of digits nested together.  In contrast, there is the Inverse Class.  By capitalizing the letter (`\D`, '\S', `\W`) we would search for all other characters than the ones notated.  If we wanted to find anything besides digits, we would use the `\D` tag.  Therefore we must always be careful of our syntax, especially capitalization.

### The OR Operator

    Although not present in our email validation, the OR Operator is still a vital part of Regular Expression.  Signified by the character `|`, also know as 'pipe'.  The Or Operator tells the Regex engine to match a literal, specific character or group of characters that are located on either of its sides.  The example of `a|b` corresponds to either a OR b to be found.

### Flags

    Flags are another optional parameter that can be added to an expression to make the engine search in an expected advanced way.  The email expression does not utilize any flags in its design however, they are still important to note.  The six main flags are `g` (global search), `i` (case-insensitive search), `m` (multi-line search),  `s` (allows . to match newline characters), `d` (generate indicies for substring matches), and `u` ('unicode', treat a pattern as a sequence of unicode code points).  These flags are denoted at the end of a pattern and are preceded by a `\`, forward slash.

## Author

I am new to coding taking a coding bootcamp to help me get started.
https://github.com/HavoxPrime
