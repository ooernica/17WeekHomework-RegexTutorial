# Matching an Email

By: Erna Lukač

What is a RegEx? RegEx stands for REGular EXpression. RegExs are a series of special characters that define a search patter and can be utilized by all coding languages. A few use cases of this is "CTRL" and "F" to search for something familar or even to validate and email when you are signing up for an account at a website. 

## Summary

Today we will examine and break down the backend of an email validation tool, through the email RegEx, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
We will start from the biggest concepts, anchors, grouping consturctions, bracket expression, etc. and then go into smaller ones, like character classes, character excapes, quantifier, etc. Finally we will put it together as one summary. 

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

This RegEx is considered a literal, it must be wrapped in slashes / not quotations. 

Literal expressions are used when regular expressions are constant. If the regular expression you are using will change, consider using a constructor. You can read more about them [here.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)

### Anchors

The character ^ signifies the beginning of a string and the character $ signifies the end, making them anchors. 

### Grouping Constructs

Constructs are grouped by being enclosed withing parenthesis ().


### Bracket Expressions

Bracket expressions are enclosed withing square brackets []

They symbolize a pattern that we are searching for.

They are also known as positive character groups -- think of this as "Positive, it needs to be there." 

### Character Classes



### Character Escapes



### Quantifiers

Think of quantifiers as your resource to know what the quantities of the characters the RegEx is searching for. 

In the RegEx we are reviewing we see it one time, right before the ending anchor, in the third character set. {2,6}$

The 2 in this expresion means the MINIMUM amount of characters, 6 is the MAXIMUM in the preceeding character set. 

### The OR Operator

The OR operator is not used in this RegEx, but it is still important to know. It looks like this |. OR operators allows the search parameters to weild more results, for example: |
if you are searching for the word (cat), and type in (c|a|t), other combinations of the letters would also be found, like: "tac", "cta", "tca", "act", "atc", and so on.

Remember that the OR operator would only be appliable to the grouping construct, (cat). If something were to appear as such: (c|a|t|) + (pie) the cobinations about would still be found as the first three characters and + pie would be found as the second set. 

### Flags



## Putting it all together

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

- / : literal 
- ^ : anchor, signifies start of RegEx
- Group 1 : ([a-z0-9_\.-]+)
    - [] : positive character group, the symbols we are searching for here are LOWERCASE a-z, digits 0-9, and the following symbols _ . - 
    - .\ : character escape
    - MAKING SENSE OF THIS: this is the first part of your email. You often see emails as: firstname.lastname@domain.com. Group 1 is searching for the example "firstname.last" the + at the end indicated that it needs to add the @ sign which is just outside of the group name. The @ sign is required for ALL emails, whereas the username of the email has no creative limitiation (although there may be some character ones, depending on what you use)
- Group 2: ([\da-z\.-]+)
    - .\ : character escape
- Group 3: ([a-z\.]{2,6})
    - .\ : character escape
    - {2,6}: quantifier 
- $ : anchor, signified end of RegEx

## Want more practice?

Check out some of the following websites for more info on Regular Expressions.

## Author

Check out more of my work at: [ooernica](https://www.github.com/ooernica)  
Questions/Comments? [Contact Me](mailto:e.lukac@outlook.com)