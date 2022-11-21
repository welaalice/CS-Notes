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


## Lecture 7 (17/10)
**Pointers**

Pointer: A variable that contains the address of another variable
- decleration: type* pointerName;
- pointers only store address

[Pointers](https://replit.com/@welaalice/CS16-Pointers#main.cpp)

**&** - used to get address of specific variable

[Pointer example (doc)](https://docs.google.com/document/d/1rpUJedeYlvomOVySiBtqyNUddU4jB6cnOhVmuU1WYdY/edit)

## Lecture 8 (19/10)

[Array and pointers](https://replit.com/@welaalice/CS16-Pointers-and-Arrays#main.cpp)
- sizeof() = number of bytes
- int - 4 bytes*
- double = 8 bytes*
- * on 64 byte pc

## Lecture 9 (24/10)

```cpp
mat2D[i][j] = *(*(mat2D + i)+j);
```

using vectors:
```cpp
//declaring vector
vector<doubles> scores = {95, 50, 100, 75};

//2D vector
vector<vector<double>> mat2D = { {10, 20}, {30, 40} , {50, 60} };

//iterating thorugh 2D vector
for (int i = 0; i < mat2D.size(); i++){ //get no of rows
        for(int j = 0; j < mat2D[0].size(); j++){ //get no of cols
            cout << "mat2D["<< i <<"]["<< j <<"]" << setw(3)<< mat2D[i][j] << " is at location: " << &(mat2D[i][j]) << endl;
        }
    }

//length of vector
int len = scores.size();


```
**References**:
Reference: A reference in C++ is an alias for another variable

*using & to reference*

[Slides on references](https://drive.google.com/file/d/1_EVyuwQSee5ZFigkQtdajxwUM0eMIqwX/view)

auto = keyword c++ uses to figure out type of keyword depending on circumstance

--> argv[1] = *(argv + 1) //storing address
* iterating through array using argv in main decleration

## Lecture 10 (26/10)

**files and structs**

- ifstream = open file
- oftream = write to file
- ifs.close() = closing file

**C++ structures**
 * Struct = data structure composed of similar data types
 * Access the member variables of p1 using the dot ‘.’ operator
 * Can be of different types

different ways to access the struts:

```cpp
bool isSmarter(superhero a, superhero b){ //pass by value
    return a.intelligence > b.intelligence;

}

bool isStronger(superhero& a, superhero& b){ //by referece (alias)
    return a.strength > b.strength;

}

bool isFaster(const superhero* p, const superhero* q){ //pointers
    return p->speed > (*q).speed; //same thing , first is just short hand for second

}
```

## Lecture 11 (31/10)

**Midterm review**

* -o = name of executable
* 	a.out without ^

**data representation** non negative for midterm 
- char intitialised to a number will output the ascii value
- 0b = binary
- 0x = hexadecimal
- 0b1010 = 10
- 0xa1 = 161
- int(digit) from char returns ascii value --> interpret at int and not convert to int
- stoi(digit) returns the actual integer //or atoi
- n bits = 2^n bit patterns
- ints = 4 bytes
- hex digit = 4 bits, 8 bits = 1 byte
- 0x10a5 to binary = 5 --> 0101, a --> 1010, 0 --> 0000, 1 --> 0001 == 0b0001000010100101 (1 at the start, 5 at the end)
	- using 4 bits

## Lecture 12 (07/11)

Headerfiles, Makefiles
* header gaurds:
```cpp
#ifndef SUPERHERO_H //if it is not defined in other files then
#define SUPERHERO_H //include it, if it is then skip this


#endif //close
```

## Lecture 13 (09/11)

```cpp
void legion::combine_powers(){
}

legion legion1;
legion.name; //accessing fuction from object in class/struct

//inline definition
//making a vector with 3 zeros: vector<int>(3,0);
//this->powers = pointing to global variable
```
access specifiers: private, public
- Scope resolution operator = **::**
	- kinda like 's --> saying combine powers is fuction belonging to legion
```cpp
class legion
{
   private:
   /* code */
   // can only be accessed by member fuctions of the class (eg. cant do legion.name)
   
   public:
   /* code */
   //member functions
   //public data may be accessed by any code user (in main)

};
```
- use getter to access private data , dont modify any member data, end with const, only return data by value
- setter to change ==> these are public functions
- constructor: called everytime new object is made, public, same name as class, no return value, without = c++ generates one with no parameters
```cpp
//constructor decleration
legion();
legion(string name);

//definition
legion::legion (string name){
	//initialise all data members
	name = team_name;
	powers = vector<int>(3,0);
}

```


## Lecture 14 (14/11)

more on classes (included in lecture 13)
**Dynamic memory**

Heap vs Stack
- stack: segment of memory managed automatically using the Last In First Out (LIFO) principle
- heap: segment of memory anaged by the programmer


## Lecture 15 (16/11)
**Linked lists**
- vector type with being dynamically resizeable

```cpp
//linkedlist.h

struct Node{
	int data;
	Node* next;
};

```


```cpp
//linkedlist.cpp
#include <iostream>
#include <vector>
#include "linkedlist.h"
using namespace std;

int main(int argc, char const *argv[])
{
	Node n {5, nullptr}; //node on stack
	node *p = new Node {50, nullptr}; //node on heap
	
	cout << n.data << ", " << n.next << endl; // accessing data on stack
	cout << p->data << ", " << p->next << endl; // accessing data on heap
    
    return 0;
}
```
Adding nodes to empty list:
```cpp
//function

Node* push_front (Node* h, string value){

    if (h == nullptr){
	Node* p = new Node {value, nullptr};//on heap because want list to exist after function
	return p;
     } else{
     	Node* p = new Node {value, nullptr}; //new node to go front
	p->next = h; //new node next assigned with existing node's address 
	return p;
     }

}//end function

```
Since basically dong samae thng then shrthand of code:

```cpp
//function

Node* push_front (Node* h, string value){

Node* p = new Node {value, nullptr};
    if (h){ // if h false = nullptr
	p->next = h;
     } 
     return p;
}//end function
```

## Lecture 16 (21/11)

code on linked list and recursion noability slides
	
	
