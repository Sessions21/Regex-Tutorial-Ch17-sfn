#  Regex-Tutorial-Ch17-sfn
## by Scott Nichols

This tutorial is going to explain the use of regex to match a URL using the expression /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/. 

## Summary

A regular expression is a sequence of characters that defines a search pattern. This is commonly used to find patterns within a string, find/replace characters within a string or validate input. This tutortial will go walk through the components of a regex and how it applies to matching an email.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components
  /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
### Anchors
The anchors used in this regex expression for matching an URL are `^ `, which indicates the beginning of the string and `$`to indicate the ending of the string.

### Quantifiers
The Quantifiers in this regex includes the `?`, `+`, `*` and `{}` quantifiers. The `?` after the "s" in https tells us there can be either 1 or no "s" after the http.  The `?` after group 1 tells us "https://" may or may not be included. The final `?` tells us the end of the URL may or may not have another "/" at the end. The `+` tells us there can be a group of 1 or many combinations of digits, characters, "-" and "." in group 2.  The `*` quantifier instide group 4 parenthesis tells us there can be any number of combinations of digits, letters, ".", "-" or "/" in this group. The `*` outside the group 4  tells us there can be zero or more combinations of this group.  "The `{}` inside group 3 tells us this group can be 2 to 6 characters long for the ".com" label.

### Character Classes
The Character Classes used are `\d`, `\w`, and `[]`. Group 2 can contain any number of single digits 0-9 with the `\d` included in the brackets.  Group 4 can include any word characters with the `\w`. The last 3 groups contain `[]` which tells us there are any number and combinations of the characters within them.

### Grouping and Capturing
There are 4 groups.  Group 1 captures the "https" character goup that can be included at the beggining of the URL.  Group 2 captures the first section of URL after "https" that can be any length group of characters both single numeric characters, alphabetic characters and "." or "-".  The 3rd group captures the ".com" type structure of any URL.  The last group is what follows the ".com" and can either be part of the URL or not and can be any combination of "/", word characters, "." or "-".

### Bracket Expressions
The bracket expressions are part of group 2, 3, and 4.  As described above, these brackets are encolsed within each group and indicate each of the specified characters and character classes can be included any number of times and in any combintation as a group.

### Greedy and Lazy Match
There are only Greed quantifiers in this expression.  It includes quantifier {2,6} which restricts the character set to exactly 2 but up to 6 in length for that string.  The `+`, `.`, and `*` are also greedy quantifiers used in multiple groups and places in the expression. They restrict the group to be included or not with the `?`.  They include the `+` and `*` is used as a greedy quantifier to look for any number of string combinations if they are included.

## Author

I am a web designer in training. You can view my projects on Git Hub at https://github.com/Sessions21