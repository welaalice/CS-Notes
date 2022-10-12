# CS16
## Lecture 1 (26/09)

**General notes**:
- hmwk 1 and 2 due **friday (30/09)**
- check zybook perm is correct

[Practice code from Repl for lecture 1](https://replit.com/@welaalice/CS16-lecture1#main.cpp) ||
[Looking up things for C++](https://cplusplus.com/) 


## Lecture 2 (28/09)

**Unix commands**:
- pwd = showing where/server currently on
- / = root directory
- ssh = secure shell
- cd = change directory
- ssh towela@csil.cs.ucsb.edu = endter csil account
- mkdir = make directory
- ls = see everything in directories
- cd../ = back to home directory
- -o = change name of executable file
- cat = see contents of the file (eg cat greeting.txt)
- al = shows all hidden files in folder
- - std=c++11 = telling compliler using this version of C++
- rm = remove

**Example of code in vim editor**:

```cpp
#include <io stream>
  using namespace std;
  
  int main(){
    cout << "Hello World!" << endl;
    return 0;
  }
```
**Compiling vim**:
- g++ (file name)
  - gets another file which is executible

### Functions practice

[Guessing Game example](https://replit.com/@welaalice/CS16-Lecture-2-Guessing-Game#main.cpp)


## Lecture 3 (03/10)

**Basic for loop structure**

[For loop structure](https://replit.com/@welaalice/CS16-Lecture-3-Loops#main.cpp)

```cpp

// ex1.cpp
// 10-3-22
#include <iostream>
using namespace std;

int main(){
	// Which code snippet prints Hello 4 times? --> B 0-4
	// Choose E if code has a compile time error i
	// because variable i is declared multiple times
	
	// Code A
	for(int i = 0; i < 5; i++){
		cout << "Hello ";
	}
	cout << endl;

	// Code B
	for(int i = 1; i < 5; i++){
		cout << "Hello ";
	}
	cout << endl;
    
	// Code C
	for(int i = 2; i < 9; i++){
		cout << "Hello ";
	}
	cout << endl;
	
	// Code D
	for(int i = 6; i > 0; i--){
		cout << "Hello ";
	}
	cout << endl;

	return 0;
}

```

[Link to other code problems from lecture](https://github.com/ucsb-cs16-f22/lectures/tree/main/lect03)

**notes:**

ex2: 
-  A result in compile error as i not declared
-  B and D are infifite loops as i is incrementing and doesn't have correct loop condition, if condidion missing, c++ assumes it is true

ex4:
- None of the code gives the desired output
- C gives one extra output

[Using loops to make shapes](https://replit.com/@welaalice/CS16-Lecture-3-Shapes#main.cpp) 

## Lecture 4 (05/10)

[Arrays](https://replit.com/@welaalice/CS16-Arrays#main.cpp)

**Git and Github**

- **Git**: version control system
	- maintain
	- collaborating

- **Github**: website that hosts Git
	- repo = repository 
	- clone = like making copy but with connecton to online repo

[updating repos](https://docs.google.com/document/d/1raNAa8WsRndatVXdV2eU4q_jZL7eyeD0P82Jp4Ecyec/edit)

## Lecture 5 (10/10)

**Automating complilation - Makefiles***

sample code:
[Automating complilation](https://replit.com/@welaalice/CS16-Automating-compliation#main.cpp)
- using make in same directory to automate
- make new file called **MakeFile**:

automation for one executable:
```cpp
# Makefile is given as an input make

#Rules
#targer/ output: dependency/ input
#cmd
#could also have flags ie: g++	-std=c++11	shapes.cpp	-o shapes -Wall(see all warnings)
#could also add command to run at same time

shapes : shapes.cpp
	#run compulation command
	g++	shapes.cpp	-o shapes

clean:
	rm shapes

```

## Lecture 6 (12/10)

continuation: 
[Automating complilation](https://replit.com/@welaalice/CS16-Automating-compliation#main.cpp)

- Reusing code from different files to use in other programs
- Cannot execute without main function --> get linker error

Complilation --> compliling + linking
linking: making excecutable using other libraires and files etc
- give option to g++: g++ -c shapes.cpp(just compling and not linking)
- gives shapes.o (just machine code version of file)

header files:
- make own header file
- ie shapes.h

**header file:** (just decleration)
```cpp

#include <iostream>
using namespace std;

string returnNstars(int n)
string drawRect_1(int rows, int cols)
string drawRect(int rows, int cols)

```
- including shapes.h sstill error wihtout code with declerations

how to eliminate error:
g++ drawMountain.cpp shapes.cpp -o test
