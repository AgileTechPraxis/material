
### TPP table

| # | Transformation               | Start code         | End code                                 |
| -- | --------------------------- | -------------------| -----------------------------------------|
| 1  | {} -> nil                   | {}                 | [return] nil                             |
| 2  | Nil -> constant             | [return] nil       | [return] “1”                             |
| 3  | Constant -> constant+       | [return] “1”       | [return] “1” + “2”                       |
| 4  | Constant -> scalar          | [return] “1” + “2” | [return] argument                        |
| 5  | Statement -> statements     | [return] argument  | [return] min(max(0, argument), 10)       |
| 6  | Unconditional -> conditional| [return] argument  | if(condition) [return] 1 else [return] 0 |
| 7  | Scalar -> array             | dog                | [dog, cat]                               |
| 8  | Array -> container          | [dog, cat]         | {dog=”DOG”, cat=”CAT”}                   |
| 9  | Statement -> tail recursion | a + b              | a + recursion                            |
| 10 | If -> loop                  | if(condition)      | loop(condition)                          |
| 11 | Statement -> recursion      | a + recursion      | recursion                                |
| 12 | Expression -> function      | today – birth      | CalculateBirthDate()                     |
| 13 | Variable -> mutation        | day                | var Day = 10; Day = 11;                  |
