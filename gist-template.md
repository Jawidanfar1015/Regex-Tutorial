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
- [Sources and References](#sources-and-references)

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

Quantifiers indicate that the preceding token must be matched a certain number of times. A quantifire can be greedy or lazy that is explained below.

- `a*a+a?` -0 or more, 1 or more, 0 or 1

  - "+" Matches 1 or more of the preceding token.
  - "\*" Matches 0 or more of the preceding token.
  - "?" Matches 0 or 1 of the preceding token, effectively making it optional.
  - "?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.

- `a{5}a{2,}` -Looks for exactly five, two or more
- `{2,6}` -forces the input of characters between two & six characters long.
- `a+?a{2,}?` -match as few as possible
- `ab|cd` -match ab or cd

### Grouping Constructs

- `(ABC)` Capturing groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
- `(?<name>ABC)` named capturing group captures groups of a specific name.
- `\1` is a numeric Referance
- `(?:ABC)` Groups multiple tokens together without creating a capture group.

### Bracket Expressions

A bracket expression enclosed in square brackets is a regular expression that matches a single character, or collating element. If the initial character is a circumflex ^, then this bracket expression is complemented.

See Character Class to see some examples.

### Character Classes

Character classes match a character from a specific set. There are a number of predefined character classes and you can also define your own sets.

- `[ABC]` Characters inside brakets will match any character in the set.
- `[^ABC]` Adding a caret will match any character that is not in the set.
- `[A-Z]` Add a dash between two characters will select a Range.
- `.` Will Match any characters expect linebreaks. Its like a wildcard and will accpet any input.
- `[\s\S]` A character set that can be used to match any character, including line breaks, without the dotall flag. An alternative is [^] carrot in brackets, but it is not supported in all browsers.
- `\w` Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters).
- `\W` Matches any character that is not a word character (alphanumeric & underscore).
- `\d` Matches any digit character (0-9)
- `\p` Matches a character in the specified unicode category.

### The OR Operator

- `|` Acts like a boolean OR. Matches the expression before or after the |.
  It can operate within a group, or on a whole expression. The patterns will be tested in order. Just as in java will match either set of characters. It will look for this OR that.

### Flags

Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression.

- `i` Ignores case
- `g` Global search retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.
- `m` Multiline flag When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
- `u` Unicode
- `y` The expression will only match from its lastIndex position and ignores the global (g) flag if set. Because each search in RegExr is discrete, this flag has no further impact on the displayed results.
- `s` Dot (.) will match any character, including newline.

### Character Escapes

The backslash in a regular expression precedes a literal character. You also escape certain letters that represent common character classes, such as \w for a word character or \s for a space. The following example matches word characters (alphanumeric and underscores) and spaces.

"Are you there, Alice?, asked Jerry."
"(here|there).+(\w+).+(said|asked)(\s)(\w+)\." );

## Author

Jawid Noori: UW Coding Bootcamp Student
[github] https://github.com/Jawidanfar1015

### Sources and References

- [regexr](https://regexr.com/)
- [BackRef](https://www.regular-expressions.info/backref.html)
- [RegExpression](https://www.regular-expressions.info/wordboundaries.html)
