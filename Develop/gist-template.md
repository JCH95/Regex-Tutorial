Regular Expression (Regex) Tutorial
Regular Expressions are powerful tools that offer efficient methods for processing large blocks of text within code. It follows a pattern-matching notation that allows any user to parse large sections of text for a variety of reasons, some of which include: Finding character patterns, extracting strings into a collection for generating reports, and validating text that needs to match a predetermined pattern.

Summary
In the document below, one will find common regex components and syntax along with brief descriptions and how they may be used. There are many different ways to use regular expressions, however 2 specific ones I have chosen to utilize contain many (if not all) of the regex components include /^#?([a-f0-9]{6}|[a-f0-9]{4})$/ and /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,7})$/

Table of Contents
Anchors
Quantifiers
OR Operator
Character Classes
Flags
Grouping and Capturing
Bracket Expressions
Greedy and Lazy Match
Boundaries
Back-references
Look-ahead and Look-behind
Regex Components
Anchors
Anchors (or atomic zero-width assertions) can cause a match to pass or fail based on its current position within the string. However, they do not cause the regex engine to move through a string or change characters. Looking at exmaples of anchors, we find that \A means the match must occur at the beginning of a string, and \z means the match must occur at the end of a string. The start and end can also be signified using ^ and $.

Quantifiers
A quantifier esentially uses the regex engine to match sequences of text (like characters, groups, or even character classes). They must be present in the input string for a match to be generated through the quantifier. An example of a quantifier include * which matches the previous element 0 or more times. Another example includes { n } which matches the previos element exactly n times. One final example includes +? which matches the previos element one or more times, yet also as few times as possible.

OR Operator
OR operators are typically used to match characters or expressions on either or both side of the OR operator, signified as |. It tells the regex engine that it can use whichever expression on either side of the operator it wants, and both can produce the desired result.

Character Classes
Character classes basically matches one specific character within a set of characters. This means that they help shorten your search for characters by using keywords. \w matches any word character, \W matches any non-word character, \d matches any decimal digit, and \s & \S matches any white-space or non-white-space character, respectively. You can also use these to set character ranges like [ first - last ] matches any single character in a range from first to last. One last example involves [^ character_group ] which matches any single character that isn't contained within the character_group, and characters are also case-sensitive in said group.

Flags
There are 6 flags in regex, however the 2 most important involved g which is a global search that doesn't return after the first match, and i which is a case-insensitive search. Flags can also be combined into a single regex. They are also denoted at the end of a given pattern.

Grouping and Capturing
Grouping and capturing is used most often when trying to identify one or more subexpressions, which can also be used to capture substrings of an input string. They can also match a subexpression that is repeated within an input string. More often though, they retrieve individual sub expressions and process them separately from the matched text. One of the most common examples of grouping and capturing is from validating an email input as follows: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,7})$/. A short breakdown reveals ^ being used to identify the beginning of the email address, . - @ characters are used tp find literal characters, and the range {2,7} shows the correct length needed.

Bracket Expressions
Bracket expressions are expressions which utilize [ ] to find lists of characters. Using a hyphen (-) inside the brackets will produce a range like 0-9. The main use of these expressions is to help developers find and use hex colors within css. A bracket expression usually includes more than one bracket to combine for hex code searchers like /^#?([a-f0-9]{6}|[a-f0-9]{3})$/. In said example, the brackets are being used to show it finding ranges of [a-f] anf [0-9] four separate times (denoted by the {4} towards the end).

Greedy and Lazy Match
Greedy and Lazy matches are 2 different ways that quantifiers can be applied in a search. "Greedy" search will attempt to match the longest possible string, like in /<.+>/g where it will look for < followed by any possible number of characters. "Lazy" search will attempt to match the shortest possible string. Using the last example, simply applying a ? like this /<.+?>/g will then make the expression lazy.

Boundaries
Bounradies are similar to anchors in the sense that they too do not consume characters. However, boundaries like \b make assertions as to what can be matched on either side of the current position. \b essentially matches positions where one side of a given positon is a word character, and the other side is not a word character. They're particularly useful when the user wants to match a sequence of letters on their own.

Back-references
Back-reference constructs allow a previosuly matched sub-expression to be identified within the same regex. Essentially, using the syntax \<number> or \1 is used to indentify previous parts of the first declared pattern, and ensures 2 pieces of matching strings. There is also the \<name> command which matches the value of a named back-reference to a named expression.

Look-ahead and Look-behind
Otherwise known as lookaround expressions, there are 4 different paths from lookahead (checks ahead of the current location in a string) to lookbehind (checks behind the current location in a string). There is a positive lookahead and lookbehind, (?=check) or (?<=check) respectively, which asserts what follows or preceeds the current position respectively in the string is "check". Then there is a negative lookahead (?!check) and negative lookbehind (?<!check). Each of these asserts what would follow or preceed the current position respectively is not "check".

Author
Find me on GitHub! I would love to talk code! https://github.com/JCH95
