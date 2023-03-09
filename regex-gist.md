# Taylor's Regex Tutorial

This gist will be discussing the concept and implementation of a regular expression in JavaScript. A regular 
expression, or Regex for short, is a sequence of characters that creates a search pattern in text. 
These expressions can be used for find, match, find and replace or validation type operations on 
a string.

## Summary

The Regex we will be covering will be a pattern used for validation of an email address. The pattern will be broken down into each piece and explained. So as to understand it's purpose and and other possible options along the way. First, we will start with an example of the regular expression. Let it be noted that the expression has to be placed within a starting and ending forward slash.

```js
const re = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/; // Pattern for validating is an email format 

const exp = 'email@example.com';

console.log(re.test(exp)); // Output: true
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

# Regex Components

## Anchors

So let's begin with anchors. Anchors are tokens that don't match with any character, but rather assert something about the matching process. Anchors are the Caret `"^"`, it determines the matching process starts at the beginning of the string (or line). And the Dollar Symbol `"$"`, determines the process to find the final match in the string (or line).

Either of which can be used to match an exact string or a range of matches using bracket expressions. The caret, matching with what follows it. And the dollar symbol with what precedes it. 

Keep in mind that regex expressions are case sensitive. So in the search `^Hello`, the strings `"Hello"` and `"Hello World"` will match. But `"hello"` or `"hello y'all"` will not.  

In the example below, we use both anchors. Stating that the string must start and end with what matches the expression in between.

```js
const re = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/; 

// Pattern for validating is an email format 
```

## Quantifiers

Quantifiers are used to set the limits of the string that your regex matches (or an individual section of the string). They are also inherently greedy. Meaning that they match as many occurrences of the pattern as possible. 

These limiters are used as follows:
- `?` - Matches the pattern zero or one time
- `*` - Matches the pattern zero or more times
- `+` - Matches the pattern one or more times
- `{}` - Curly brackets give three ways to set limits for a match following a `{start, stop}` syntax. 

    - `{ n }` - Matches the expression exactly `n` number of times when the range starting comma and the stop point are omitted.
    - `{ n, }` - Matches the expression at least `n` times, still omitting the stop point.
    - `{ n, s }` - Matches the expression from a minimum of `n` times to a maximum of `s` times. 


## Grouping Constructs

As a regex becomes more complicated, you may want to check multiple parts of a string for the fulfillment of different requirements in different sections. This is where **grouping constructs** come into play, as they do exactly that.

The primary way to group a section is by using parentheses `"()"`. Each of these sections are known as a **subexpression**. 

THe following contains two grouping constructs or subexpressions:
```
(abc)@(123)
``` 
The first subexpression is searching for a part of a string that matches `"abc"` exactly. While the second is searching for an exact match `"123"`. In between them we have an ampersand `"@"`. Subexpressions look for an exact match unless told to do otherwise. Therefore, the string `"abc@123"` would be a match whereas `"cba@321"` would not.

## Bracket Expressions

Using a set of square brackets `"[]"` represents a range of characters that we want to match. These are known as bracket expressions, or also as a positive character group because the describe the characters we want included. 

Bracket Expressions can be used to include specific characters, `[mst]`, which will match against anything including those letters. Matching: `"mountain"`, `"sarah"`, `"telephone"`.

For a negative character group you add the caret `"^"` to the begining of the expression inside the brackets. What this does is matches a string that doesn't contain any of the included characters. So `[^a]` would match `"bot"` but not `"bat"` 

More commonly seen then either, is a hyphen `"-"`, which can be used to indicate a range between alphanumeric characters (letters and numbers only). This means that `[x-z]` and `[xyz]` will search for the same exact thing.

Bringing this to the first group (or subexpression) of our example,

```js
const re = /^([a-z0-9_\.-]+)/; 
```
- The expression is looking for the range of letters `[a-z]`. Lower case only. If lower and upper case were desired: `[a-zA-Z]`.

- The range of numbers `[0-9]`

- Following the `"9"` we are looking for an underscore `"_"` , a single backslash preceding the period `"\."` which is a character escape that we wll cover later and a hyphen `"-"`.

Now keep also in mind that the characters can be in any order. And do not need to have all of the characters in a string meeting this criteria. It may meet any of them.

## Character Classes

A **Character Class** in a regex expression defines a set of characters that any one of which can occur in an input string to make a match. Some classes have already been shown, positive and negative characters groups through bracket expressions are considered character classes.

Some other common examples are:

- `.` -- Matches any character except the newline character `"\n"`.
- `\d` -- Matches any Arabic numeral digit. This class is equivalent to the bracket expression `[0-9]`.
- `w` -- Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_).
- `s` -- Matches a single whitespace character, including tabs and line breaks.

The last three examples can each be made to do the inverse match by capitalizing the character. For example, `"\D"` would match any non digit character.

## The OR Operator

## Flags

## Character Escapes


# Author
