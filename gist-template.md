# RegEx Quick Ref

- As a web development student, I have developed a tutorial explaining the specifics of regex so that we can understand the search pattern the regex defines.

## Summary

- A Regex or regular expression is a sequence of characters that define a search pattern. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings. It also looks for input validations. It is a technique commonly developed in theoretical computer science.

We will look at a string of code using regex, this code looks for a match HTML tag.

Example: `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

The below content will explain what each section of this code does and more.

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

- `^abc$` -^start / $end of the string

  - `^` Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled.This matches a position, not a character.
  - `$` Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

- `\b\B` -word, not-word boundary
  - `\b` Matches a word boundary position between a word character and non-word character or position (start / end of string). See the word character class (w) for more info.
  - `\B` Matches any position that is not a word boundary. This matches a position, not a character.
  - See Boundaries for more detailed Information

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
