# Deconstructing an Email Address Validation RegEx

In this Gist, I'll attempt to provide a thorough exmination of the functionality of a common RegEx, piece by piece.

## Summary

The RegEx we'll look at is this: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ - a common email address validation RegEx.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components
This RegEx begins with the "^", a meta escape character that asserts the starting position of the string an email address is comprised of. The local part of the email address is then wrapped in parentheses, forming a Capture Group, followed by a literal match requirement of the "@" character, followed by the domain name wrapped in parentheses as another Capture Group. Then the RegEx requires a literal match of "." before the final, parentheses-wrapped Capture Group representing the domain. Finally, the "$" meta escape character asserts the end of the string.

### Anchors 
The "^" that asserts the start and the "$" that ends the string in the example are anchors of this RegEx.

### Quantifiers and Greedy Matches
IN this example, the "+" charactersthat end the first two capture groups are quantifiers that match bewteen one and unlimited time(s) as many times as possible, giving back as needed. The "{2,6}" in the third capture group functions similarly, but matches the preceeding token between two and six times. These are "greedy" in that they allow for matching one or more of the token quantified.


### Character Classes 
In this example, the character classes are set within "[]". In the first capture group, the character classes set a range of letters from a-z, case sensitive, and/or digits 0-9. The escape characters "\.-" set a literal match allowing "." and "-" as valid characters. The second capture group similarly matches digits 0-9 using the "\d" and "a-z\" ranges as well as allowing "." and "-" using the same syntax. The final capture group allows for a case-sensitive range from a-z and "."

### Grouping and Capturing
This RegEx is broken into three Capturing Groups, each wrapped in parentheses. Each represents a range of acceptable values for each portion of an email address: the local-part, the "@" symbol, and the domain name and domain (.com, .org, .net, et c.).

### Bracket Expressions
The bracketed expressions "[]" match a specific set of single chharacters based on the set of list expressions contained within, as defined by the character class parameters set and explained above.

## Author

The author, J Howell, can be found on GitHub at https.github.com/J-Howell-kc.
He is a current bootcamp student in Full Stack Web Development, a PMI-certified Associate Project Manager (CAPM), as well as an experienced copywriter and published journalist and music critic. He's done a few other things too. 
