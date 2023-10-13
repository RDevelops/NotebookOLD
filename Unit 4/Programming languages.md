# Terminology
| Term | Defenition | Example |
| -- | -- | -- |
| Low level language | Machine code | Assembly |
| High level language | A language that is translated to machine code | Python |

# Low level languages
Low-Level languages are Machine code, commonly written in binary or assembly.
This type of language is easily readable by the machine.
Different types of languages are designed for different CPU architectures, so it is not portable and very complex to use

# High level languages
These programming languages hide the complexity by translating to low level languages.
Each instruction in a language can have 1000s of instructions in low-level languages
This translation can slow down execution speed.

# Programming paradigms
Approach to solve a problem
- OOP (object Oriented Programming)
	- Python
	- C++
- Imperative
- Procedural
	- C
- Functional
- Declarative

## Procedural
- First languages learnt by a programmer usualy
- cinsidered to be general purpose tools
- well defined steps wto solve a specofoc problem
- if the steps become over complicated you an make them into functions/different procudes
C is an example

## OOP
- data structures or objects are defined with properties or attributes
- e.g. class Animals will have dogs, cats, etc as objects
Java, C++, C#

## Event Driven
- The program is decided by inputs or messages from other programs, e.g. events
- Can be written in almost any language
## Mark Up
- HTML, XML
- Formatting of a document
- Represent complex data structures
- Can move info from RDMS to XML to move to other formats

# Constructs, techniques and their use in languages
## Command Words
- Command or  reserved words are the core of most programming languages.
- They are often used in many ways, and we apply various techniques to solve problems
### Command words in screenshot
- if
- else
- return
- int
- cout

## Identifiers
- Identifiers is the name for something that is stored in the RAM.
- Main types of identfiers:

### Variable
These can change during the running of the program
In a language like C++, you can create variables with the following code:
`int age = 20`

| Syntax | Defenition |
| -- | -- |
| int | Define the data-type |
| age | Variable name |
| = | Used to tell that the info after is the data |
| 20 | The data |
#### Global and local variables
##### Global variables
Global variables are explained in the name, they can be used always anywhere in the code, in any function.
##### Local variables
Local variables can only be used inside of the function it is defined in.
#### global/local vars in screenshot
global: x, var
local: y, localvar1, var2
###  Constant
These can not change during the running of the program
In a language like c++, you can craete constants wth the following code:
`const int x = 5`

| Syntax | Defenition |
| -- | -- |
| const | define that its constant |
| int | Define the data-type |
| age | Variable name |
| = | Used to tell that the info after is the data |
| 20 | The data |
### data types
| data type | example value |
| -- | -- |
| int | 5 |
| float | 0.5 |
| str | "hello" |
| bool | True |
| char | H |

## Statements
Statements are a core aspect of many programming languages

They define the basic actions that can be preformed, and often combine several constructs.

### Assignments
Stores a value in an identifier (var or constant)

| C# | C++ | RUBY |
| -- | -- | -- |
| userAge = 17; | userAge = 17; | userAge = 17 |

## Logical operations
and, or, etc

# constructs and their implementation
## Subroutines , functions and procedures
Subroutines functions and procedures are used in procedural progrmming where code is split into multiple modules.
Each module has a different name depending on the language
They make code easier to read and write.
This also allos code to be used multiple times.
![[Function.png]]

# Data Structures.

A data structure is a programming technique used to collect and organise items in a formal structure, which helps the data to be processed efficiently.

- A format of organizing and storing data.
- Many are very common between data structures.
    - The common data structures include string, array (one- and two- dimensional), stack, queue and record.

More common data structures include:

- Linked list
- Stack
- Table
- Array
- Graph
- Binary search tree
- Queue
- Tree
- Hash Table

## Strings. (Or txt).

- Commonly used to store simple text entered by the user, such as a username.
- May be used to enter more complex text for processing, such as the content of an email, or tweet.
- ‘Substring’ is used to describe a part of a large string, for example ‘Ear’ is a substring of ‘Earth’.

## **Array (one-dimensional).**

[https://www.youtube.com/watch?v=55l-aZ7_F24](https://www.youtube.com/watch?v=55l-aZ7_F24 "https://www.youtube.com/watch?v=55l-az7_f24")

Usually, it is a static data structure, which means it has a fixed size. Modern programming languages however are more flexible and allow an array to be resized.

Usually, an array can only store on type of data, such as integers, or Boolean.

If we wanted to store seven daily maximum temperatures, we would create and array of seven decimal numbers.

A two-dimensional array is similar to one-dimensional but can store multiple rows of data.

## **Record (Or structure).**

Like an array. It differs because it can store a MIX of data types within its structure.

I.E., ‘Student’ and ‘Age’, are stored as integers, ‘Forename’ and ‘Surname’ are strings and ‘Enrolled’ is Boolean.

# Stack
LIFO (Last in first out)
2 OPERATIONS, PULL AND PUSH
PUSH = ADD DATA
PULL = REMOVE DATA

![[STASCK.png]]
# Queue
FIFO (FIRST IN FIRST OUT)
ENQUE AND DEQUEUE
ADD (TO ADD TO QUEUE)
REMOVE FROM START OF Q)
ONLY DATA FRM THE FRONT CAN BE ACCESSED AND REMOVED.
![[QUQUE.png]]