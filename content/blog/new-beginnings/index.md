---
title: New Beginnings
description: This Blog is written to know somewhat about javascript functions.
---

The split() method divides a String into an ordered list of substrings, puts these substrings into an array, and returns the array. The division is done by searching for a pattern; where the pattern is provided as the first parameter in the method's call

## JavaScript Demo: String.split()

> const str = 'The quick brown fox jumps over the lazy dog.';
>
> const words = str.split(' ');
> console.log(words[3]);
> // expected output: "fox"
>
> const chars = str.split('');
> console.log(chars[8]);
> // expected output: "k"
>
> const strCopy = str.split();
> console.log(strCopy);
> // expected output: Array ["The quick brown fox jumps over the lazy dog."]

The pattern describing where each split should occur. The separator can be a simple string or it can be a regular expression.

- The simplest case is when separator is just a single character; this is used to split a delimited string. For example, a string containing tab separated values (TSV) could be parsed by passing a tab character as the separator, like this: myString.split("\t").
- If separator contains multiple characters, that entire character sequence must be found in order to split.
- If separator is omitted or does not occur in str, the returned array contains one element consisting of the entire string.
- If separator appears at the beginning (or end) of the string, it still has the effect of splitting. The result is an empty (i.e. zero length) string, which appears at the first (or last) position of the returned array.
- If separator is an empty string (""), str is converted to an array of each of its UTF-16 "characters".

### Description

When found, separator is removed from the string, and the substrings are returned in an array.

If separator is a regular expression with capturing parentheses, then each time separator matches, the results (including any undefined results) of the capturing parentheses are spliced into the output array.

If the separator is an array, then that Array is coerced to a String and used as a separator.

> ## Using split()

When the string is empty, split() returns an array containing one empty string, rather than an empty array. If the string and separator are both empty strings, an empty array is returned.

> const myString = ''
> const splits = myString.split()
>
> console.log(splits)
>
> // ↪ [""]

The following example defines a function that splits a string into an array of strings using separator. After splitting the string, the function logs messages indicating the original string (before the split), the separator used, the number of elements in the array, and the individual array elements.

> function splitString(stringToSplit, separator) {
> const arrayOfStrings = stringToSplit.split(separator)
>
> console.log('The original string is: ', stringToSplit)
> console.log('The separator is: ', separator)
>
> console.log('The array has ', arrayOfStrings.length, ' elements: ', arrayOfStrings.join(' / '))
> }

## Removing spaces from a string

In the following example, split() looks for zero or more spaces, followed by a semicolon, followed by zero or more spaces—and, when found, removes the spaces and the semicolon from the string. nameList is the array returned as a result of split().

> const names = 'Harry Trump ;Fred Barney; Helen Rigby ; Bill Abel ;Chris Hand '
>
> console.log(names)
>
> const re = /\s*(?:;|\$)\s*/
> const nameList = names.split(re)
>
> console.log(nameList)

## Returning a limited number of splits

In the following example, split() looks for spaces in a string and returns the first 3 splits that it finds.

> const myString = 'Hello World. How are you doing?'
> const splits = myString.split(' ', 3)
>
> console.log(splits)
