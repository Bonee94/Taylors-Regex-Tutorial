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

## Grouping Constructs

## Bracket Expressions

## Character Classes

## The OR Operator

## Flags

## Character Escapes


# Author
