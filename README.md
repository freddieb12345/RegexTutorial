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
### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)