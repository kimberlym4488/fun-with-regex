# Fun with Regex

Regular Expression components assist developers behind the scenes. One common example is validating an email address. Let's take a peek behind the curtain at the world of 'regex' email validation!

## Summary

Regular expressions are simple 'code snippets' that can validate user input, find/replace characters, match positions before, after, trim whitespace, and work between characters. The basic built-in logic improves and simplifies a developers work. The components also improve the user experience by expanding allowable user input of lower case/upper case/spacing/symbols. Not only does regex validate input, it can automatically update the input to the correct format 'under the hood'.

Regex works with many different programming languages, or engines. There are known as expression flavors. The flavor highlighted in this tutorial is JavaScript.<br>
Source: https://www.regular-expressions.info/tutorial.html

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

Validating an email involves many Regex components. We'll go through each one step by step to get us to the final solution! We'll start with what looks like gibberish and break it down piece by piece:

> Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Anchors

Anchors do not match any specific characters at all. Rather they match -before- or -after- whatever you are attempting to match. <br>

> Examples:

```JS
// $ matches the end of the string its applied to
.$ matches f in def
// ^ matches the start of the string
^. matches d in def
```

```JS
// as it pertains to our email validation
'/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/'

^ '=the start of the email string we are matching'
$ '= is at the end to signal when we end matching'
```

### Quantifiers

Though labeled rather unattractively (lazy, greedy) quantifiers are anything but! A quick way to match something any number of times. The most common are generic \*, the lazy '?' or the greedy repeater '+' or number constraints<br>

> Examples:

```JS
// * will repeat the previous item or group zero or more times.
? will match 0 or 1
{3,5} will match 3,4, or 5 characters
```

```JS

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
+ '=find a letter or number in the grouping and repeat (i.e. 1 or more)'

// In the example case, our email regex is allowing any number of characters before the @ in an email address, and any number of characters after the @. 
// In practical use, we would want to limit this. An email address is limited to 254 characters for SMTP. We would add in a {1,64} for example after the '+', (before the @) to limit the beginning of the email address from 1 to 64 characters. 

// We can do the same for the domains, as 2-6 characters for the top level domain wouldn't work for kim@moran.solutions. A quantifier of {2-63} instead of {2,6} would be more than sufficient.

```

### Grouping Constructs
Anchors do not match any specific characters at all. Rather they match -before- or -after- whatever you are attempting to match. <br>

> Examples:

```JS
// $ matches the end of the string its applied to
.$ matches f in def
// ^ matches the start of the string
^. matches d in def
```

```JS
// as it pertains to our email validation
'/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/'

^ '=the start of the email string we are matching'
$ '= is at the end to signal when we end matching'
```

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

As a lifelong learner and lover of puzzles, regex is truly fun to learn. Reverse engineering it, creating my own, and trying to solve problems is why I love coding. Regex is the ideal integration into any programming language.
Github: kimberlym4488
