# Regular Expression Study notes

## Useful tips

First things first, Regex expression is much easier to write than read. If you find it difficult to debug your broken Regex expression, you would better to rewrite it than debug the expression.

## Essentials

Regex is essentially variations of the following:

> \[set of characters\]{number of characters to match}

## Most simple regex

  1. Nick => Nick

  2. \[ \] is called a character class

    * [Nn]ick => **Nick, nick**

    * [a-c] => **a, b, c**

    * [Nn]ick can also be written as alternation (Nick|nick)

  3. The Special . sign

    * '.' in regex has a special meaning. It matches **any character** (not strictly speaking) in stead of a dot literal

  4. Some shortcuts for simple regex

    * [0-9]+ => any non-negative integers, which is the same as **\d+**
    * \\w => word characters, including alphanumerics or underscore.
    * \\s => white spaces
    * \\S => any non-whitespace character

## How to repeat the pattern

  1. ? (one time or no)

    * ab?c => **ac or abc**

  2. \* (zero or more times)

  3. \+ (one or more times)

  4. {n} (exactly n times)

  5. {n,} (at least n times)

  6. {n,m} (at least n times but no more than m times)

  * [Nn]ick => **ick, Nick, nick, Nnick, nNick, nnick ...**

## Quantifier and Grouping

**A quantifier modifies the pattern to its immediate left**

* 0abc+0 => **0abcc0, 0abcc0 ...**

* 0(abc)+0 => **0abcabc0, 0abcabcabc0 ...**

## Greediness

Greediness means that Regular Expression quantifiers match as much text as they possibly can while allowing the entire pattern to match successfully

* (123)(456): **\(.+\)** does not give you just (123) but the whole string (123)(456)
   **\((.+?)\)** => add a questio mark after the quantifier gives the expected result (123)

## Anchors

Anchors means two things at the beginning and end of a string: ^ and $. If you are certain about the beginning and end of the matching pattern, you can use this one.

* -- This is a comment --
   Write the following regex to match this comment: **^--\s+(.+)\s+--$**

## Escaping

Characters that you will almost always have to escape in regex is **\+\*\[\]()^$** and possibly a space






