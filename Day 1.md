# Bootcamp - Day 1

## TDD Problems

### 3n + 1

#### Background

Problem in Computer Scient are often classified as belonging to a certain class of problems (e.g. NP, Unsolved, Recursive). In this
problem you will be analyzing a property of an algorithm whose classification is not known for all possible inputs

#### The Problem

Consider the following algorithm:

```
1. input n
2. print n
3. if n = 1 then STOP
4. 	if n is odd then n := 3n + 1
5. 	else n := n / 2
6. GOTO 2
```

Given the input `22`, the following sequence of numbers will be printed

```
22 11 34 17 52 26 13 40 20 10 5 16 8 4 2 1
```

It is conjectured that the algorithm above will terminate (when a `1` is printed) for any integral input value. Dispite the simplicity of the algorithm, it is unknown wheter this conjecture is true. It has been verified, however, for all integers `n` such that `0 < n < 1000000` (and, in facet, for may more numbers than this.)

Given an input `n`, it is possible to determine the number of numbers before *and including* the `1` is printed. For a given `n` this called the `cycle-length` of `n`. In the example above, the cycle length of `22` is `16`.

For any tow numbers `i` and `j` you are to determine the maximum cycle length over all numbers between *and including both* i and j.

#### The Input

The input will consist of a series fo pairs of integer `i` and `j`, one pair of integers per line. All integers will be less than `10,000` and greter than `0`.

You should processl all paris of intergers and for each pair determine the maximum cycle lenght over all integers between and including `i` and `j`.

#### The Output

For each pair of inout integers `i` and `j` you should output `i`, `j` and the maximum cycle length for integers between and including `i` and `j`. These numbers should be seperated by at least one space with all three number on one line and with one ine of output for each line of intput. The integers `i` and `j` must appear in the output in the same order in which they appeared in the input and should be followed by the maximum cycle length (on the same line).

#### Sample

```
Input           Output
1 10            1 10 20
100 200        	100 200 125
201 210        	201 210 89
900 1000        900 1000 174
```

### Minesweeper

Minesweeper is a computer game that became popular in the 1980s, and is still included in some versions of the Microsoft Windows operating system. This problem has a similar idea, but it does not assume you have played Minesweeper.

In this problem, you are playing a game on a grid of identical cells. The content of each cell is initially hidden. There are M mines hidden in M different cells of the grid. No other cells contain mines. You may click on any cell to reveal it. If the revealed cell contains a mine, then the game is over, and you lose. Otherwise, the revealed cell will contain a digit between 0 and 8, inclusive, which corresponds to the number of neighboring cells that contain mines. Two cells are neighbors if they share a corner or an edge. Additionally, if the revealed cell contains a 0, then all of the neighbors of the revealed cell are automatically revealed as well, recursively. When all the cells that don't contain mines have been revealed, the game ends, and you win.

For example, an initial configuration of the board may look like this ('*' denotes a mine, and 'c' is the first clicked cell):

```
*..*...**.
....*.....
..c..*....
........*.
..........
```

There are no mines adjacent to the clicked cell, so when it is revealed, it becomes a 0, and its 8 adjacent cells are revealed as well. This process continues, resulting in the following board:

```
*..*...**.
1112*.....
00012*....
00001111*.
00000001..
```

At this point, there are still un-revealed cells that do not contain mines (denoted by '.' characters), so the player has to click again in order to continue the game.

You want to win the game as quickly as possible. You want to find the minimum number of clicks to win the game. Given the size of the board (N x N), output such minimum number of clicks.

#### Input

The first line of the input gives the number of test cases, T. Ttest cases follow. First line of each test case contains one integer N. N lines strings with length N follows containing '*' and '.', denotes the Minesweeper initial board.

#### Output

For each test case, output one line containing "Case #x: y", where x is the test case number (starting from 1) and y is the minimum number of clicks to win.

#### Limits

```
1 ≤ T ≤ 100.
```

##### Small dataset

```
1 ≤ N ≤ 50.
```

##### Large dataset

```
1 ≤ N ≤ 300.
```

##### Sample

```
Input        Output 

2            Case #1: 2
3
..*
..*
**.
5            Case #2: 8
..*..
..*..
.*..*
.*...
.*...
```

### The Trip

A number of students are members of a club that travels annually to exotic locations. Their destinations in the past have included Indianapolis, Phoenix, Nashville, Philadelphia, San Jose, and Atlanta. This spring they are planning a trip to Eindhoven. The group agrees in advance to share expenses equally, but it is not practical to have them share every expense as it occurs. So individuals in the group pay for particular things, like meals, hotels, taxi rides, plane tickets, etc. After the trip, each student’s expenses are tallied and money is exchanged so that the net cost to each is the same, to within one cent. In the past, this money exchange has been tedious and time consuming. Your job is to compute, from a list of expenses, the minimum amount of money that must change hands in order to equalize (within a cent) all the students’ costs.

#### Input
Standard input will contain the information for several trips. The information for each trip consists of a line containing a positive integer, n, the number of students on the trip, followed by n lines of input, each containing the amount, in dollars and cents, spent by a student. There are no more than 1000 students and no student spent more than $10,000.00. A single line containing 0 follows the informationfor the last trip.

#### Output
For each trip, output a line stating the total amount of money, in dollars and cents, that must be exchanged to equalize the students’ costs.

#### Sample

```
Input    Output3        $10.0010.0020.0030.00415.00    $11.9915.013.003.010```

A certain computer has 10 registers and 1000 words of RAM. Each register or RAM location holds a 3-digit integer between 0 and 999. Instructions are encoded as 3-digit integers and stored in RAM. The encodings are as follows:

```
- 100 means halt- 2dn means set register d to n (between 0 and 9)- 3dn means add n to register d- 4dn means multiply register d by n- 5ds means set register d to the value of register s- 6ds means add the value of register s to register d- 7ds means multiply register d by the value of register s- 8da means set register d to the value in RAM whose address is in register a- 9sa means set the value in RAM whose address is in register a to the value of register s- 0ds means goto the location in register d unless registers contains 0
```
All registers initially contain `000`. The initial content of the RAM is read from standard input. The rest instruction to be executed is at RAM address 0. All results are reduced modulo `1000`.

#### Input
The input begins with a single positive integer on a line by itself indicating the number of the cases following, each of them as described below. This line is followed by a blank line, and there is also a blank line between two consecutive inputs. The input to your program consists of up to 1000 3-digit unsigned integers, representing the contents of consecutive RAM locations starting at 0. Unspecifed RAM locations are initialized to 000.

#### Output

For each test case, the output must follow the description below. The outputs of two consecutive cases will be separated by a blank line.The output from your program is a single integer: the number of instructions executed up to and including the halt instruction. You may assume that the program does halt.

#### Sample

````
Input       Output1           16299492495399492495399283279689078100000000000
````
