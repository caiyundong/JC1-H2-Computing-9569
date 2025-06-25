# PESUDOCODE
https://www.cambridgeinternational.org/Images/697401-2026-pseudocode-guide-for-teachers.pdf

# Some notes
* Use **Uppercase**, e.g. "IF", "REPEAT"
* Proper indent the code (same as python)

# Variables, constants and data types
* INTEGER: whole number
* REAL: containing a factional part
* CHAR: single character, 'x', "C", '@'
* STRING: a sequence of zero or more characters
* BOOLEAN: logical values TRUE or FALSE
* DATE: a valid calendar date, dd/mm/yyyy

## Variable Declaration
`DECLARE <identifier> : <data type>`
For example,
`DECLARE Counter: INTEGER`
`DECLARE TotalPay: REAL`

## Contant
`CONSTATNT HourlyRate = 6`

## Assignment
`<identifier> <- <value>`
For example,
`Counter <- 0`
`TotalPay <- NumberofHours * HourlyRate`

# Arrays
In pseudocode, array start index is 1, which is different from 0 as most of languages.

Declare 1D array
`DECLARE <identifier>: ARRAY[<lower>:<upper>] OF <data type>`
For example:
`DECLARE StudentName: ARRAY[1:30] OF STRING`

Declare 2D array
`DECALRE <identifier>: ARRAY[<lower1>:<upper1>][<lower2>:<upper2>] OF <data type>`
For example:
`DECALRE NoughtsAndCrosses: ARRAY[1:3][1:3] OF CHAR`

# Using Array
`StudentName[1] <- 'Ali'`
`NoughtsAndCrosses[2,3] ← ꞌXꞌ `
```
// initialize an array
FOR Index ← 1 TO 30
 StudentNames[Index] ← ""
NEXT Index
```

# Common Operations
Multiplication and division have higher precedence over addition and subtraction (this is the normal mathematical convention). However, it is good practice to make the order of operations in complex expressions explicit by using parentheses "()".
```
// input 
INPUT Ansnwer    

// output
OUTPUT "You have ", Lives, " lives left"

// arithemetic
a <- a + 1
a <- a - 1
a <- a * 2
a <- a / 2    // returns REAL, e.g. 4/2 -> 2.0

a <- DIV(5, 2) // integer divide, 2
b <- MOD(5, 2) // remainder
```

## Relational operations
```
IF age > 5 THEN
ENDIF
```
```
// The result of these operations is always of data type BOOLEAN.
> Greater than
< Less than
>= Greater than or equal to
<= Less than or equal to
= Equal to
<> Not equal to
```

## String functions
```
//length of a string
LENGTH("hello")

//substring
RIGHT(ThisString: STRING, x: INTEGER) RETURNS STRING

LCASE('W')
RCASE('w')
```

## Numeric functions
```
INT(281.14)   // returns 281
RAND(8)         // returns a random number from 0 to x (not inclusive of x)
```

# SELECTION
IF...ELSE...
```
IF <condition> THEN
 <statement(s)>
ELSE IF <condition> THEN
 <statement(s)>
ELSE
 <statement(s)>
ENDIF
```

CASE
```
CASE OF <identifier>
 <value 1> : <statement1>
<statement2>
...
 <value 2> : <statement1>
<statement2>
...
 ...
ENDCASE
```
For example:
```
INPUT Move
CASE OF Move
 ꞌWꞌ : Position ← Position − 10
 ꞌSꞌ : Position ← Position + 10
 ꞌAꞌ : Position ← Position − 1
 ꞌDꞌ : Position ← Position + 1
 OTHERWISE : CALL Beep
ENDCASE
```

# Iteration
## Count-controlled (FOR) loops
* Mostly used to iterate an array, or have a fixed number of loops
```
FOR <identifier> ← <value1> TO <value2> STEP <increment>
 <statement(s)>
NEXT <identifier>
```
For example,
```
Total ← 0
FOR Row ← 1 TO MaxRow
 RowTotal ← 0
 FOR Column ← 1 TO 10
    RowTotal ← RowTotal + Amount[Row, Column]
 NEXT Column
 OUTPUT "Total for Row ", Row, " is ", RowTotal
 Total ← Total + RowTotal
NEXT Row
OUTPUT "The grand total is ", Total
```

## Post-condition(REPEAT/UNTIL) loops
* Used for data validation
```
EPEAT
 <statement(s)>
UNTIL <condition>
```

```
REPEAT
 OUTPUT "Please enter the password"
 INPUT Password
UNTIL Password = "Secret"
```

## Pre-condition(WHILE) loops
* If not quite sure about number of loops, but with a clear condition
```
WHILE <condition>
 <statement(s)>
ENDWHILE
```
For example,
```
WHILE Number > 9
 Number ← Number – 9
ENDWHILE
```

# Procedures and functions
Two types of subroutines in pseudocode:
1. procedure (no return value)
2. function (has return)

```
// definition
PROCEDURE <identifier>()
 <statement(s)>
ENDPROCEDURE

// with parameter
PROCEDURE <identifier>(<param1> : <data type>, <param2> : <data type>...)
 <statement(s)>
ENDPROCEDURE
```

There is a need to call/invoke on the procedure and function
```
CALL <identifier>()
CALL <identifier>(value1, value2)
```

For example,
```
PROCEDURE DefaultSquare()
 CALL Square(100)
ENDPROCEDURE

PROCEDURE Square(Size : INTEGER)
 FOR Side ← 1 TO 4
 CALL MoveForward(Size)
 CALL Turn(90)
 NEXT Side
ENDPROCEDURE

IF Size = Default THEN
 CALL DefaultSquare()
ELSE
 CALL Square(Size)
ENDIF
```

```
// function has return type
FUNCTION <identifier>() RETURNS <data type>
 <statement(s)>
ENDFUNCTION
```

For example,
```
FUNCTION Max(Number1 : INTEGER, Number2 : INTEGER) RETURNS INTEGER
 IF Number1 > Number2 THEN
    RETURN Number1
 ELSE
    RETURN Number2
 ENDIF
ENDFUNCTION

OUTPUT "Penalty Fine = ", Max(10, Distance*2)
```

```
// pass by reference, default by value (BYVAL)
```
PROCEDURE SWAP(BYREF X : INTEGER, Y : INTEGER)
 Temp ← X
 X ← Y
 Y ← Temp
ENDPROCEDURE
```

# File handling
```
OPENFILE <file identifier> FOR <file mode>  // mode: READ, WRITE, APPEND
READFILE <file identifier>, <variable>
EOF(<file identifier>)  // check if EOF
WRITEFILE <file identifier>, <data>
CLOSEFILE <file identifier>
```