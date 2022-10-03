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







