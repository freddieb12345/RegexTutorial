# RegexTutorial

Regex (Regular expressions) are patterns that are matched up agaisnt a string. They can be used to replace text within a string, validate forms, extract substrings from a string based on the pattern match as stated previously. 

Regex allows you to create specific patterns allowing you to search through, find and replace anything withing the target string.

## Syntax

Using an example to more accurately describe what regex does:

```

`^([a-z0-9_-]{3,15})$`

```

Breaking down the above example, the '^' at the start of the regex is used to start the line. 
```

'[a-z0-9_-]'

```
The above means that the expression may contain any letter from a-z, any number from 0-9 aswell as underscores and hyphens. This can be used if you want to limit what characters a user can use in a certain variable(e.g. username or password). 
```

'{3,15}'

```
The above is used to define that length of the variable, in this case, it would be limited to be between 3 and 15 characters long.

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
Anchors are there to test whether a selected string fully matches with the created pattern from the regex. The anchors themselves dont match any of the characters with he selected string, but instead, indicate something about the matching process. They are essentially used to determine the current position in the string matches a determined locaion within it, i.e. the beginning of the string or the end of the line. There are two key anchors involved in regex and they are listed below:

* **Caret: ^**  Matches the following regex at the beginning of a string
* **Dollar Sign: $**  Matches the preceding regex at the end of a string

as displayed in the example in [Syntax](#syntax), the caret is shown at the start of the regex and the dollar sign is at the end.

### Quantifiers
Quantifiers are used to specify how many characters are required within the string and are always wrapped in curly brakets as shown in the example in [Syntax](#syntax). 

There are a number of different quantifiers that all serve different purposes as listed below:

* **`*`**	Match zero or more times.
* **`+`**	Match one or more times.
* **`?`**	Match zero or one time.
* **`{ n }`**	Match exactly n times.
* **`{ n ,}`**	Match at least n times.
* **`{ n , m }`**	Match from n to m times.

### Grouping Constructs
Grouping constructs allow you to break down the regex pattern into different groups.

For example, if you were to try and match an email, it would be seperated into 3 construct groups: 

`username` **`@`** `domain` **`.`** `com`

The username group is very similar to the example in [Syntax](#syntax), however, instead of 3-15 characters, we use the '+' quantifier, allowing it to be any length. 

```

([a-z0-9_\.-]+)

```

The next group is just for the @

```

@

```

The next group is the same as the first group, allowing the domain to be made up of any characters

```

([a-z0-9_\.-]+)

```

The next group is used to define the domain, which can only contain letters and a dot, and can only be between 2 and 6 characters long.

```
([a-z\.]{2,6})
```

And then the final group is just the dollar sign anchor, defining the end of the string.

```
$/
```
### Bracket Expressions
The 3 different types of brackets are all responsible for different things.

Parenthesis `()` define different groups within the regex expression.

```

([a-z\.]{2,6})
```


Square brackets `[]` are used to define what type of characters can be matched or unmatched within the string.

```

[a-z\.]

```

Curly brackets `{}` are used to define the number of characters that can be accepted into the string

### Character Classes

Character classes are used to help determine the differences between different characters, allowing you to find and/or remove any characters. All the character classses as listed below:

* `\s` – space symbols, tabs, newlines.
* `\S` – all but \s.
* `\d` – digits.
* `\D` – non-digits.
* `\w` – Latin letters, digits, underscore '_'.
* `\W` – all but \w.
* `\.` - A dot .  matches any character except a newline.

As shown in the regex example used for the email, we can see that the `\.` character class is used. 

```

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

```

### The OR Operator
OR Operators (Alternation Operator) matches on of a choice of regular expressions: if you put the character(s) representing the alternation operator between any two characters in the regular expression, the result matches the union of the strings that those two characters match.

Examples of OR Operators are as follows:

* `(|)` - matches a string that has any anterior characters followed by the characters on the left or right of the vertical bar
* `[]` - matches a string that has any anterior characters without any characters within the brackets
* Examples: 
```
x(y|z)  matches a string that has x followed by y or z (and captures y or z)
x[yz]   matches a string that has x, but without capturing b or c
```
The OR operator will match with one out of a selctiong of choices from your regex. 

Examples of OR operators can be seen listed below:
* `(|)` - matches a string that has any anterior characters followed by the characters on the left or right of the vertical bar
* `[]` - matches a string that has any anterior characters without any characters within the brackets

```

x(y|z)  matches a string that has x followed by y or z (and captures y or z)
x[yz]   matches a string that has x, but without capturing y or z

```

### Flags
Flags are optional parameters that can be added to the regex, allowing it to search in a different way.

A few examples of flags are listed below: 

* `g` - Makes the regex search for all occurences of the pattern as oppose to just the first one.

* `m` - Multi-line, when enabled the Anchors (^ $) will match the start and end of each line within the string as oppose to the whole string

* `i` - Insensitive, makes the entire expression case-insensitive

* `y` - The sticky flag causes the search to initiate at a set position with the string.


### Character Escapes

When using special characters in regex, there needs to be a way in which you can escape them. 

In order to do this, a `/` is used to escape them.

Shown below is another email regex example, where character escapes have been used 5 times in order to escape the special characters within the expression.
```

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

```

Below is a list of special characters that can be escaped using the `/`

* `[]` - Square brackets

* `^` - Caret

* `$` - Dollar sign

* `.` - dot

* `|` - Vertical bar

* `?` - Question mark

* `*` - Asterix

* `+` - Plus sign

* `()` - Parenthesis


## Author

https://github.com/freddieb12345