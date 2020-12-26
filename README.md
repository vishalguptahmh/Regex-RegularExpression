# Regex-RegularExpression
guide to regex

Expressions      | Description
---              | --- 
.                |  Any Character Except New Line
\d               | Digit (0-9) 
\D               | Not a Digit (0-9)     
\w               | Word Character (a-z, A-Z, 0-9, _)
\W               | Not a Word Character
\s               | Whitespace (space, tab, newline)
\S               | Not Whitespace (space, tab, newline)
---              | ---
\b               | Word Boundary
\B               | Not a Word Boundary
^                | Beginning of a String
$                | End of a String
---              | ---
[]               | Matches Characters in brackets
[^ ]             | Matches Characters NOT in brackets
\|                | Either Or
( )              | Group


Quantifiers      | Description
---              | --- 
\*                | 0 or More
\+                | 1 or More
?                | 0 or One
{3}              | Exact Number
{3,4}            | Range of Numbers (Minimum, Maximum)


### Examples
### Phone Number
321-555-4321

123.555.1234

`\d\d\d.\d\d\d.\d\d\d\d` this will match any charcter between number or `\d{3}.\d{3}.\d{4}`

`\d\d\d[-.]\d\d\d[-.]\d\d\d\d` this is will match only - or . between numbers

`[89]00[-.]\d\d\d[-.]\d\d\d\d` this will find 800 or 900 in beginning of numbers

`[1-7]00[-.]\d\d\d[-.]\d\d\d\d` this will find 100 to 700 in beginning of numbers


[^a-z] this will match everything except small case letters

[a-z] this will match small case letters

[a-zA-Z] this will match small and captial case letters


#### Names
Mr. Vishal

Mr Sachin

Ms Jobby

Mrs. Twinkle

Mr. L

`M(r|s|rs)\.?\s[A-Z]\w*`

#### Email
vishalgupta@gmail.com

vishal-gupta@gmail.com

_vishal@gmail.com

vishal01-gupta.hmh@yahoo.edu

`[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+`


#### URLS
https://github.com

https://www.github.com

`https?://(www\.)?\w+\.\w+`

#### Replace string with help of group

https://github.com

https://www.github.io

`https?://(www\.)?(\w+\.)(\w+)`

Now you want to replace matching strings  with group 3 

- search with `https?://(www\.)?(\w+\.)(\w+)`

- replace section type `$3`
```
output : 
com
io
```

#### PAN verification (Permanent Account Number)
- The length of the PAN number is always 10
- Each char is an uppercase letter,
- ABCDS1234Y (<char><char><char><char><char><digit><digit><digit><digit><char>)
```
  [A-Z]{5}[0-9]{4}[A-Z]
  
```
  

