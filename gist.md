#What Is a Regex?
A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input. 
Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. These patterns are used with the exec() and test() methods of RegExp , and with the match() , matchAll() , replace() , replaceAll() , search() , and split() methods of String .

# Regex Tutorial - Dates

The purpose of this tutorial is to explain how the date regex expression works. I will break down each part of the date expression and describe what it does. 

## Summary

The regex expression I will be highlighing is dates. Please see [Regex Components](#regex-components) for the regex featured in this tutorial. 


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Character Escapes](#character-escapes)


## Regex Components

The following date range is from 1900–01–01 through 2099–12–31, as well as different options for regex formatting for date, month, and year. See below...

Validating dates in YYYY-MM-DD format:


^(19|20)\d\d[- /.](0[1–9]|1[012])[- /.](0[1–9]|[12][0–9]|3[01])$


Validating dates in MM/DD/YYYY format:

^(0[1–9]|1[012])[- /.](0[1–9]|[12][0–9]|3[01])[- /.](19|20)\d\d$

Validating dates in DD-MM-YYYY format:

^(0[1–9]|[12][0–9]|3[01])[- /.](0[1–9]|1[012])[- /.](19|20)\d\d

### Anchors

The use of anchors is to specify where the pattern should match (before, after, or both characters). We use the start-of-string character ^ at the start of the expression and the end-of-string character $ at the end of the expression. For example) 

/^\d{4}-(0[1-9]|1[0-2])-(0[1-9]|[12][0-9]|3[01])$/

^ = Matches the beginning of the string, $ = Matches the end of the string


### Quantifiers

The open and closed curly braces {} is used to begin and end a quantifier. For the date expression, this is commonly used for specifiying years. 

For example)

/\d{4}/

This means that a date should start with a 4 digit year from 0000-9999 by using the digit character \d. We specify that we want exactly 4 characters (no more and no less) by using {4}. On the other hand, if we want to accept 4-5 characters, we'll write it out as {4,5} instead. 

### Character Classes

The purpose of character classes is to distinguish kinds of characters, such as letters and digits. Square brackets are used to indicate this. In character classes for dates, we can set a range for single digits.

For example) 

/0[1-9]/

This example refers to the months with leading zeros - January (01) through September (09). The 0 in front means we want a literal match for the character 0, while the [1-9] in square brackets mean that we only want to accept a number between 1 and 9. 


### The OR Operator

The OR operator (|) is used in the date expression, as for example: 


(19|20)\d\d.


The | allows the first two digits of the year to be either 19 or 20. The parentheses () are mandatory when specifiying a year. The reason why parentheses are mandory is because it prevents the | in this example from splitting up the expression into two options. 

### Character Escapes

The backslash \ is used to escape a character. For example)

\d


##Author 
My github -->https://github.com/MiguelGarciaCastro
