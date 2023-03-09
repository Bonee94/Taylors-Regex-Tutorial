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

## Quantifiers

## Grouping Constructs

## Bracket Expressions

## Character Classes

## The OR Operator

## Flags

## Character Escapes


# Author
