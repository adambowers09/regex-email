# Regex Email Breakdown

This breakdown will explain the fuction of the below expression:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
This verifies that the characters entered for an email are valid.

## Summary

A regular expression is a sequence of character that specifies a search pattern in text.  Such patterns are used by string-searching algorithims for "find" or "find and replace" operations on strings for input validation.  This technique was developed for theoretical computer science and formal language theory.

## Table of Contents

-[Anchors](#anchors)

-[Quantifies](#quantifies)

-[Character Classes](#character-classes)

-[Grouping and Capturing](#grouping-and-capturing)

-[Bracket Expressions](#bracket-expressions)

-[Greedy and Lazy Match](#greedy-and-lazy-match)

-[Back-references](#back-references)


## Regex Components

### Anchors

Anchors do not match characters but instead they match a position before or after characters.

*Anchors included in this regex:*

`^`, `$`
`/^([a-z0-9_\.-]+)` - the caret symbol at the biginning of the string means that the characters that are after must be at the beginning of the query.
`([a-z\.]{2,6})$/` - the dollar symbol at the end of the string means that the characters preceding it must be at the end of the string.

### Quantifiers

Quantifiers are inherently greedy and will match as many of a certain pattern as possible.  They specify how many instances of a character, group, or character class must be present in the input for a match to be found.  Quantifiers can be made lazy by adding a `?` symbol meaning it will match as few patterns as possible.

*Examples*
`?` - Match zero or one time.
`+` - Match one or more times.
`*` - Match zero or more times.
`{n}` - match exactly n times.
`{n,}` - match at least n times.
`{n,m}` - match fron n to m times.

*Quantifies included in this email regex*
- `*`, `+`, `{}`
-`{2,6})$` When using the {} syntax followed by the )$ character it means that the end of an email must contain at least 2 characters but no more than 6.
-`([a-z0-9_\.-]+)` & `([\da-z\.-]+)` after the `+` they must include the character shown after.

### Character Classes

Character classes are a set of characters that can occur in an input string to fill a match and are between an expression bracket.

*Examples*
- `\w` - Match any letters, digits, underscore.
- `\W` - Match any, but \w.
- `\s` - Match space symbols, tabs, newlines.
- `\S` - Match any, but \s.
- `\d` - Match any digit.
- `\D` - Match any non-digit.
- `.` - Matches any character except a newline \n.

*Character classes in this regex:*
`[\da-z\.-]` or `[0-9a-z\.-]` - The \d is referring to any digit and letters A through Z and a literal period or a dash.

### Grouping and Capturing

Capturing groups are used to break the string in a regex and is being applied to by placing an expression inside open and close parentheses which are used 3 times within this email regex.

1. `([a-z0-9_\.-]+)` 
2. `([\da-z\.-]+)` 
3. `([a-z\.]{2,6})`

### Bracket Expressions

Bracket expressions is a specific set of single characters inclosed in `[]`.

It can either match a list of expressions or a non matching list of expressions.  They can also consist of one or more expressions with characters, range expressions, classes, collating elements, collating symbols, or equivalence classes.

*Examples*
1. `[a-z0-9_\.-]` - This expression must contain lowercase letters A through Z or numbers 0 through 9, also can contain an underscore, period, or dash as well.
2. `[\da-z\.-]` - This expression must contain lowercase letters A - Z, `/d` is equal to 0 through 9 and also can contain a period or a dash.
3. `[a-z\.]` - This expression can only contain lowercase letters A through Z or a period.

### Greedy and Lazy Match

Greedy matches will consume as much as possible and will match the value determined as many possible times and ways it can.
Lazy matches will consume as little as possible with the first value found and consume no more.

*Examples of Greedy matches in this regex*
`([a-z0-9_\.-]+)@` - The `+` symbol here is a greedy match and is telling this group to be followed by the `@` symbol and the proceeding values as well.

*Example of Lazy mathes in this regex*
There are none in this regex.

*** Back-refences

Are used to match the same text previously match by a capturing group that helps in using previous parts of your pattern and ensuring that the two peices of a string match.

## Author

Adam Bowers
Github: adambower09


