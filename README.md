StringLib v1.1.2
================

An open-source string library for adding additional string functionality into LUA.



Indexing
--------

string[index]					-> returns character at given index from the string

	s = "hello"
	s[2] = "e"

string(index1, index2)		-> returns substring of string between given indices

	s = "hello"
	s(2,5) = "ello"

string(index)					-> returns unicode value of character at given index in the string

	s = "hello"
	s(2) = 101

string(index, chars)			-> replaces character at given index with given characters in the string

	s = "hello"
	s(2,'p') = "hpllo"



Functions
---------

startsWith(str, chars)			-> Checks to see if the string starts with the given characters

	s = "hello, world!"
	s:startsWith("hello") = true

endsWith(str, chars)			-> Checks to see if the string ends with the given characters

	s = "hello, world!"
	s:endsWith("world!") = true

removeFromStart(str, length)	-> Removes some length from the start of the string

	s = "hello, world!"
	s:removeFromStart(7) = "world!"  -or-
	s:removeFromStart("hello, ") = "world!"

removeFromEnd(str, length)		-> Removes some length from the end of the string

	s = "hello, world!"
	s:removeFromEnd(8) = "hello"  -or-
	s:removeFromEnd(", world!") = "hello"

remove(str, pattern, limit)		-> Removes a number of occurrences of a pattern from the string

	s = "hello, world, world!"
	s:remove("world") = "hello, , !"
	s:remove("world", 1) = "hello, , world!"

removeAll(str, pattern)			-> Removes all occurrences of a pattern from the string

	s = "hello, world, world!"
	s:removeAll("world") = "hello, , !"

removeFirst(str, pattern)		-> Removes the first occurrence of a pattern from the string

	s = "hello, world, world!"
	s:removeFirst("world") = "hello, , world!"
	
contains(str, pattern)			-> Returns whether the string contains the pattern

	s = "hello, world!"
	s:contains("lo, w") = true

findi(str, pattern)				-> A case-insensitive string.find

	s = "Hello, world!"
	s:findi("hello") = 1, 5

findPattern(str, pattern, start)-> Returns the first substring which matches the pattern

	s = "hello, world!"
	s:findPattern('w....') = "world"

split(str, pattern)				-> Splits the sting on the pattern

	s = "hello, world!"
	s:split() = {"hello,", "world!"}
	s:split('o') = {"hell", ", w", "rld!"}

getWords(str)					-> Returns an array of words within the string

	s = "hello, world!"
	s:getWords() = {"hello", "world"}

spaceCount(str)					-> Returns the number of spaces within the string

	s = "hello, world! I am awesome~"
	s:spaceCount() = 4

patternCount(str, pattern)		-> Returns the number of occurrences of the pattern in the string

	s = "hello, world!"
	s:patternCount('o') = 2
	s:patternCount('l') = 3

charTotals(str)					-> Returns a table of how many of each character is in the string

	s = "hello"
	s: charTotals() = {'h' = 1, 'e' = 1, 'l' = 2, 'o' = 1}

wordCount(str)					-> Returns the how many words are in the string

	s = "hello, world!"
	s:wordCount() = 2

wordLengths(str)				-> Returns a string which contains the length of each word in the string

	s = "hello, world!"
	s:wordLengths() = "5, 5!"

wordTotals(str)					-> Returns a table of how many of each word is in the string

	s = "hello, world, world!"
	s:wordTotals() = {"hello" = 1, "world" = 2}

toByteArray(str)				-> Returns unicode representations of each character in an array

	s = "hello"
	s:toByteArray() = {[1] = 104, [2] = 101, [3] = 108, [4] = 108, [5] = 111}

toCharArray(str)				-> Breaks the string up into a character array

	s = "hello"
	s:toCharArray() = {[1] = 'h', [2] = 'e', [3] = 'l', [4] = 'l', [5] = 'o'}

patternToUpper(str, pattern)	-> Returns a string where occurrences of the pattern are put into upper-case

	s = "hello"
	s:patternToUpper('e') = "hEllo"

patternToLower(str, pattern)	-> Returns a string where occurrences of the pattern are put into lower-case

	s = "HELLO"
	s:patternToLower('e') = "HeLLO"

replace(str, pattern, chars, limit) -> Replaces limited occurrences of the pattern in the string with the characters

	s = "hello"
	s:replace('l', 'p', 1) = "heplo"
	s:replace('l', 'p') = "heppo"

replaceAt(str, index, chars)	-> Replaces the character at the index with the given characters

	s = "hello"
	s:replaceAt(4, 'p') = "helpo"

replaceAll(str, pattern chars)	-> Replaces all occurrences of the pattern in the string with the characters

	s = "hello"
	s:replaceAll('l', 'p') = "heppo"

replaceFirst(tr, pattern, chars) -> Replaces the first occurrences of the pattern in the string with the characters

	s = "hello"
	s:replaceFirst('l', 'p') = "heplo"

indexOf(str, pattern, start)	-> Returns index for first occurrence of pattern in the string from start index

	s = "hello"
	s:indexOf('l') = 3
	s:indexOf('l', 3) = 4

firstIndexOf(str, pattern)		-> Returns index of first occurrence of the pattern in the string

	s = "hello"
	s:firstIndexOf('l') = 3

lastIndexOf(str, pattern)		-> Returns index of last occurrence of the pattern in the string

	s = "hello"
	s:lastIndexOf('l') = 4

charAt(str, index)				-> Returns character from the string at the given index

	s = "hello"
	s:charAt(2) = "e"

byteAt(str, index)				-> Returns unicode value of characters found at given index in the string

	s = "hello"
	s:byteAt(2) = 101

byteValue(char)					-> Returns unicode value of a single given character only

	s = "e"
	s:byteValue() = 101

compare(str1, str2)				-> Compares the two strings. 1 if first is greater, -1 if less, 0 if equal

	s1 = "hello"
	s2 = "Hello"
	s1:compare(s2) = 1

comparei(str1, str2)			-> Compares the two strings again, but this time it is case-insensitive

	s1 = "hello"
	s2 = "Hello"
	s1:comparei(s2) = 0

equal(str1, str2)				-> Returns whether the two strings are equal

	s1 = "hello"
	s2 = "Hello"
	s1:equal(s2) = false

equali(str1, str2)				-> Returns if two strings are equal. This time it is case-insensitive

	s1 = "hello"
	s2 = "Hello"
	s1:equali(s2) = true
	
valueOf(value)					-> Returns string representation of the value. (number, boolean, string or table)

	string.valueOf("hello") = "hello"
	string.valueOf(74) = "74"
	string.valueOf(true) = "true"
	string.valueOf({[1] = 'h', [2] = 'i'}) = "[1] = h, [2] = i"

insert(str, chars, index)		-> Inserts the characters into the string at the given index

	s1 = "hello"
	s2 = ", world!"
	s1:insert(s2, 5) = "hello, world!"
	s1:insert(s2, 3) = "hel, world!lo"

insertRep(str, chars, rep, index) -> Inserts the characters rep times into the string at the given index

	s = "ello"
	s:insertRep("h", 4, 0) = "hhhhello"

removeToEnd(str, index)			-> Removes all characters from string starting at index to end of string

	s = "hello, world!"
	s:removeToEnd(6) = "hello"

removeToStart(str, index)		-> Removes all characters from string starting at index down to the start of the string

	s = "hello, world!"
	s:removeToStart(7) = "world!"

trim(str, char)					-> Trims leading and trailing ends of the specified character

	s = "   hello   "
	s:trim('%s') = "hello"
	s:trim() = "hello"
	
	s = "[[[hello]]]"
	s:trim('%[') = "hello]]]"

trimStart(str, char)			-> Trims leading characters from the string

	s = "   hello   "
	s:trimStart('%s') = "hello   "
	s:trimStart() = "hello   "

trimEnd(str, char)				-> Trims trailing characters from the string

	s = "   hello   "
	s:trimEnd('%s') = "hello   "
	s:trimEnd() = "hello   "

subvar(str, table)				-> Substitutes variables from the table into the string

	s = "(x=$(x), y=$(y))"
	s:subvar({x=200, y=300}) = "(x=200, y=300)"

rotate(str, index)				-> Rotates the string about the given index

	s = "hello"
	s:rotate(3) = "lohel"

add(str1, str2)					-> Adds the two stings together by parallel characters, and then averages them

	s1 = "hello"
	s2 = "world"
	s1:add(s2) = "pjolj"

swap(str, index1, index2)		-> Swaps the two characters at the given indices of a string

	s = "hello"
	s:swap(2,4) = "hlleo"

sortAscending(str)				-> Sorts the string's characters into ascending order

	s = "hello"
	s:sortAscending() = "ehllo"

sortDescending(str)				-> Sorts the string's characters into descending order

	s = "hello"
	s:sortDescending() = "ollhe"

highest(str)					-> Returns the character with the highest unicode value

	s  = "hello"
	s:highest() = 'o'

lowest(str)						-> Returns the character with the lowest unicode value

	s = "hello"
	s:lowest() = 'e'

isEmpty(str)					-> Checks to see if the string is empty

	s1 = "hello"
	s1:isEmpty() = false
	
	s2 = ""
	s2:isEmpty() = true
	
	s3 = nil
	s3:isEmpty() = true







