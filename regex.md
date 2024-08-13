## Summary

This is a brief tutorial on the use and functionality of Regex. The sequence of matching an email(/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/) will be used to demonstrate how Regex works and operates. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

/`^`([a-z0-9_\.-]+)@([\da-z\.-]+).([a-z\.]{2,6})`$`/

Anchors (`^`, `$`) act as starting and ending points for a specified string. the carrot `^` tells a program where to start, and the dollar sign `$` signals where to end. Not to be confused, these two symbols are not used to signify matches of any characters. In essence, they are mere guide points.

### Quantifiers

/^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`).([a-z\.]`{2,6}`)$/

Quantifiers set limits for what a string can and cannot contain. They set guidelines or rules that a user is forced to follow. Such examples are included in the email sequence-

`+`: this signifies that the string provided must match at least one of the characters given in the sequence. Both `+`'s are requiring the user to pick from `[a-z0-9_\.-]` and `[\da-z\.-]` sequence at least once.  the `{2, 6}` are bracket quantifiers which set a range for the number of times a user can pick from the selected bracket `[a-z\.]`, where the user selection needs to choose at least 2 characters, but no more than 6. 

### OR Operator

OR operators are marked with an `|`. a popular way this OR operator is used is in date regex, such as: <br>
`^(0[1-9]|1[012])[-/.](0[1-9]|[12][0-9]|3[01])[-/.][0-9]{4}$`

the first group `^(0[1-9]|1[012])` demonstrates the user can pick a month starting with 0 or"(`|`)" 1, followed by the sequenced numbers that follow. This operator sets up the regex for controlled alternates. 

### Character Classes

Character classes are shortcuts to sets of codes one would want to include in their regex. They are usually identified by a backslash`\` followed by a single character. some common character classes include :

\d: This class is short for "digit" which has the same meaning as [0-9] <br>
\b: "word boundary": this class is followed by a specific string. For example: `\bsand` will locate `sandwich` but not `quicksand`. <br>
\w: "[a-zA-Z0-9_]": Somewhat of a universal regex class that covers the most common characters used

### Flags

Flags are used to make changes to the default behavior on how a Regex searches a string. For JavaScript regex, two common flags include:

`i`: (ignore casing): this allows the user to search regex without care of character casing. `Go` and `go` will be included in the search

`g`: (global): this is generally the default setting, searches for anything and everything related to the Regex.

`s`: (dott all): This creates a `.` dot character to match everything. Somewhat of a new addition to JavaScript's regular expressions.

`m`: (multiline): This acts as a more concise anchor similar to the normal `^``$`. If there are multiple strings in Regex, the `m` flag will signal regex to search for additional strings. 

### Grouping and Capturing

Grouping or capturing groups allows one to combine selected characters or strings into a single unit. In the email example, grouping is seen in `([\da-z\.-]+)`, in which the character specifications are included within the brackets. This creates a group or a capture that is unique to the string provided. In addition to the capture, each group will be stored into the program's memory. This also allows one to both specify search parameters for a specific line of a string. 

### Bracket Expressions

A bracket expression represents the specific characters that one wishes to match in Regex. Within a set of `[``]`, a bracket expression can allow input to include specific characters or specific ranges of inputs, such as 0-9, or a-z. 

### Greedy and Lazy Match

Regex in general is considered "greedy", in terms that quantifiers will attempt to match any occurrences of an input as possible. If one was to include the quantifier of `*` to an expression, the results will attempt get as much of a match as it possibly can. This can include partials, single characters, full list of strings, etc. On the opposite side, if one were to add a `?` to their Regex expression, the 'lazy' regex will attempt to find the least amount of matches as possible.  

### Boundaries

Boundaries can be used to capture specific instances or changes within a designated string. They are used with the `\b`. One common use for them is to search for whole words. one such example would be the implementation of `\bcat\b` in which the search will be able to find "The `cat` is cool" but will not return "`cat`ch a train"

### Back-references

Back-references are references to previously created/captured groups. It is a way to reuse previous tags or lines of texts.  Back-references are specified with backslash and a single digit :ex `\1`, which is also how they are called again in another string. One example includes: 

`([abc])\1` using `\1` will match the same text that was matched by the first capturing group

### Look-ahead and Look-behind

look behind `?<=` means to look after a specified sentence. If an expression would were to have `(?<=The Cat is).*` in a text containing `The Cat is Fuzzy`, the results will highlight the word `Fuzzy` since it is 'behind' the specified string. The opposite use can be included with the look-ahead, which will look for specified characters in front of a selected string. 

## Author

Masoud Abdi
Github: https://github.com/masoudwebprogrammer/regex