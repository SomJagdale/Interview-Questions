# Interview-Questions

Mathworks

1. What is Inode?
2. 32-bit vs 64-bit machine?
	A 32-bit system can access 232 different memory addresses, i.e 4 GB of RAM or physical memory ideally, it can access more than 4 GB of RAM also. 
	A 64-bit system can access 264 different memory addresses, i.e actually 18-Quintillion bytes of RAM. In short, any amount of memory greater than 4 GB can be easily handled by it.
3. Sort a given Queue without extra space.
4. The maximum sum of the array without taking two adjacent elements.




Persistent Company[assessment Round]
1.       Where and how used stack in ur application?
	 1. To verify matching paranthesisi is present in the expression or not
	 2. To convert prefix to postfix expression or tree conversion
	 
2.       Top command in linux?
	 Top command shows the real time performance of system and resource utilisation in term of time and space 
	 User details, Process Priority, %Utilisation, %CPU Utilisation, Virtual Memory, Resident Memory, Process ID, Application Name

3.       How to use binary search?
	 Convert list into sorted list, and compare search element with mid element if it smaller than mid element consider same algorithem 
	 in 1st half else in 2nd half and so on..
         first sort and then use binary search using mid, left and right position and comparision

4.       What is mean by mutex and semaphore ?
	Mutex is Locking menchnism
	Semaphore is Counting mechanism, binary semaphore and counting semaphore, Wait and signal
	semaphore use counting and mutex use lock mechanisam

5.       What is mean by synchronization?
	 Two or more process or threads runs parallely but access the critical section sequentlly to get with generate final resul valid
	 Mechanism to controll the access to common resource which is being accessed by two or more processess and threads

6.       Which system call u have used ?
	fork, exec, exit, read, write, open, close, runc, sleep
	Fork() used to duplicate process

7.       Without using c++11 smart pointer how u can achive smart pointer?
         Will create class design as Smart Pointer and will overload * and -> operator inside that class.
	 Will create wrapper class over the row pointer by overloading * and -> operator inside it. 

8.       How can you optimize code ?
	 Optimisation means remove or modify the code without changing meaning of program
	 Space Optimisation - Data Type Usage, Data packing and padding, Pass by Reference, Return type void, 
	 Time Optimisation - Optimise programe algorithm, Loop Optimisation, Inline function
	 
9.       Which IPC used?            
	 Interprocess Communication -  Pipe, Socket, Shared Memory, Queue, Seamaphore

10.   	So what is mean by TCP , UDP? And diff
	TCP used - Connection Oriented, Error correction - FTP, SSH, 
	UDP - COnnection less - High Trhoughput , No error control, Time, Video, Voice

11.   What is mean by little endian and big endian?
	Big-endian is an order in which the "big end" (most significant value in the sequence) is stored first, at the lowest storage address.
	Little-endian is an order in which the "little end" (least significant value in the sequence) is stored first.

12.   What is mean by IP4 and IP6 ?

Dassault Systems [1st Round]
1.        
class CopyDemo
{
              int Salary;
             public:
              CopyDemo(const CopyDemo& other)
              {
              }
              void SetSalary(int val)
              {
                             Salary = val;
              }
};

void fun(const CopyDemo& obj)
{
              obj.SetSalary(100);   //Does salary will set here or not?  Ans: no error: passing 'const CopyDemo' as 'this' argument discards qualifiers [-fpermissive]
}
int main() {

    // Write C++ code here

    std::cout << "Hello world!";
    CopyDemo obj1;
              fun(obj1);
    return 0;
}

2. Create class design or classes for chess in c++ [need to check it]
class Player
{
              string name;
              bool win;           
}
class ChessBoard
{
	map<hourse, moves> map;
}

3.       Create class design or classes for folder and files structur in c++

a.       Ans:
class File
{
              string fileName;
              string filePath;
}
class Folder
{
              string folderName;
              string folderPath;
              set<File> files;  //used composition relationship
              set<Folder*> Folders; //used composition relationship
}

4.       What is mean by interface?
	 An interface in the C++ programming language is an class contain all methods pure virutal methods.
	
5.       How to write down the code for memory leak?
	 void f()
	{
	   int *ptr = (int *) malloc(sizeof(int));
	   return; /* Return without freeing ptr*/
	}
	Write down the class and inside that create pointer and new it but don’t delete it

class CopyDemo
{
             int* data;
             public:
             copyDemo(int val)
             {
                            data = new int(val);

             }
             ~CopyDemo()
             {
                            //delete data;  if not delete then memory leak
                            //data = nullptr;
             }
};
int main()
{           
CopyDemo obj(10); //out of scope destr called but data object not delete //there so memory leak.
}

6.  Write down swap function using reference and pointer

Ans : void swap(int* a, int* b)
{
              int temp = *a;
              *a = *b;
              *b = temp;
}
int main()
{
              int a = 10, b = 20;
              swap(&a, &b);
              std::cout<< a << " " << b;  //a=20, b=10
              return 0;
}

7.       Write the program whete 100 elements are there and sort that based on salary
class CopyDemo
{
              int Salary;          
};
int main()
{           
              std::vector<CopyDemo> vec(100);
              vec.push_back() //till ;...100
              std::sort(vec.begin(), vec.end(), [](const auto& a, const auto& b)
                             {            
                                           return   a.Salary < b.Salary;
                             });         
}

CRISIL Company
1.       What is the difference between DOM parser and SAP parser?
2.       Templates has int, string…but return only int value?

template<typename T>
T fun(T val)
{
}
fun<int>(10);
fin<string>("A")
Ans : Use Template Specialization
#include <iostream>
#include <iostream>
using namespace std;
template <class T>
T fun(T a)
{
cout << "The main template fun(): "<< a << endl;
                             return a;
}
template<>
int fun(int a)
{
              cout << "Specialized Template for int type: "
                             << a << endl;
                             return a;
}
int main()
{
              fun<char>('a');
              fun<int>(10);
              fun<float>(10.14);
              return 0;
}

3.       Which one is better Inheritance or composition?
Ans: Composition - has-a relationship between objects.
Inheritance - is-a relationship between classes.
	We expose all the superclass methods to the other classes having access to subclass. So if a new method is introduced or there are security holes in the superclass, subclass becomes vulnerable. Since in composition we choose which methods to use, it's more secure than inheritance
Composition - Composing object holds a reference to composing classes and hence relationship is loosely bound.
Inheritance - Derived object carries the base class definition in itself and hence its tightly bound.
Composition - Used in Dependency Injection
Inheritance - Used in Runtime Polymorphism
Composition - Single class objects can be composed within multiple classes.
Inheritance - Single class can only inherit 1 Class.
Composition - Its the relationship between objects.
Inheritance - Its the relationship between classes.
	
4.   For the threaded application which smart pointer will use? Is Unique pointer or shared pointer thread safe
    Ans : Shared pointer
	Que: why shared pointer and not unique pointer
	
5.   Time complexity of std::sort() method?
	O(N log(N))
	Binary Search = O(log n)

6.       Find out min max value in const time?
	Ans - unorder_set can use which used internally hash Data structure.
I implememted vector and use sort method but that will not give u result in const time

EPAM Company
1.       Is it possible function overloading/static polymorphisam.
class Base
{
     public:
     int add()     //error note: previous declaration 'int Base::add()'
     {
         cout <<"return int";
         return 0;
     }
     double add()     // error: 'double Base::add()' cannot be overloaded with 'int Base::add()'
     {
         cout <<"return double";
         return 1.1;
     }
};

Ans :Not possible to override.
2.       What will be result? Which class add() method will get call
#include <iostream>
using namespace std;
class Base
{
     public:
     virtual void add(int i)
     {
         cout <<"Base"<<endl;
     }
};
class Derived: public Base
{
    public:
    void add(int i, int j)
    {
        cout <<"Derived"<<endl;
    }
};
int main() {
    Base* obj = new Derived;
    obj->add(1);     Ans: Base class add() method will get call
    return 0;
}

3.       What is mean by override? Final? Can we use final in method and class
	Ans: final keywork can use for class and method also.
4.       Is it possible to write only try block and not catch?
a.       int main() {
              try
              {
              }
              return 0;
	      }
b.       try
    {
        throw 1;
    }
Ans : Above both case will give error  , error: expected 'catch' before '}'

5.       what is the output? And is int get converts into double in catch bliock of second?
// Online C++ compiler to run C++ program online
#include <iostream>
using namespace std;
void last()
{
    cout<<"last entry"<<endl;
    throw 1;
    cout << "last exit"<<endl;
}
void second()
{
    cout<<"Second Entry"<<endl;
    try
    {
        last();
    }
    catch(double d)
    {
        cout<< "Second Catch = "<< d<<endl;
    }
    cout<<"second exit"<<endl;
}

void first()
{
    cout<<"First Entry"<<endl;
    try
    {
        second();
    }
    catch(int i)
    {
        cout<< "First Catch int = "<< i<<endl;
    }
    catch(double d)
    {
        cout<< "First Catch double = "<< d<<endl;
    }
    cout<<"first exit"<<endl;
}
int main() {
    // Write C++ code here
    std::cout << "main entry"<<endl;
    try
    {
        first();
    }
    catch(int i)
    {
        cout<< "main catch int="<< i<<endl;
    }
    cout<<"main exit"<<endl;
    return 0;
}
Ans :   main entry
	First Entry
	Second Entry
	last entry
	First Catch int = 1
	first exit
	main exit

6.       What is mean by unique pointer, shared pointer and weak pointer?
         check in cpp code base repo
7.       Can we pass unique pointer as a parameter in method? can we return unique pointer from method? If we have unique pointer p3=p2 ? is it possible?

	Ans : operator = and copy ctr both are default deleted in unique pointer .
		class UserQueues 
		{
		    public:
			explicit UserQueues();
			UserQueues(const UserQueues&) = delete;
			UserQueues& operator=(const UserQueues&) = delete;
			~UserQueues() = default;
		    [...]
		};
 
#include <iostream>
#include<memory>
using namespace std;
void fun(unique_ptr<int> p)
{
    cout <<"fun = " << *p<<endl;
}
unique_ptr<int> Fun1()
{
    cout<<"Fun1"<<endl;  //temp obj is return so internally move called
    return make_unique<int>(100);
}
int main() {
    // Write C++ code here
    cout<<"Hello"<<endl;
   unique_ptr<int> p=make_unique<int>(10);
   fun(std::move(p)); //pass unique pointer
   unique_ptr<int> p1 = Fun1();   //Return unique Pointer from function
   cout<< "p1 = "<<*p1;
   unique_ptr<int> p2=make_unique<int>(1000);
   unique_ptr<int> p3;
   // p3=p2;    // use of deleted function "operator="
    return 0;
}
8.       Any example of weak pointer?
9.       How to avoid increase the reference count when we pass shared pointer in methods?
         Ans : use shared parameter reference or pointer as a parameter.

10.   Lamba Expression Que: [=], [&] , How to  pass by ref, pass by val in lamba captcha? How to pass value as const in lambda expression. whole study of lambda .

11.   How to explicitly return any value from lamba?

a.       Ans :   []()->int{}

12.   User defined class and used set container to set user defined class .How to insert data in sorted order in set.
a.       Ans : use operator < overloading

class Emp
{
    public:
    int id;
    Emp(int val): id(val){}
    first approach overloas operator<
    bool operator<(const Emp& obj) const
    {
        return this->id < obj.id;
    }
};
int main() {
    // Write C++ code here
    cout<<"Hello"<<endl;
    set<Emp> data;
    data.insert(Emp(21));
    data.insert(Emp(14));
    data.insert(Emp(41));
    for(auto t: data)
    {
        cout<< t.id<< " ";
    }
}
b.       Second one is lambda
Auto cmp = [](){}
Set<Class> setData (cmp);
#include <set>
#include <iostream>
#include <iterator>
#include <algorithm>
int main()
{
  auto comp = [](int x, int y){ return x < y; };
  auto set  = std::set<int,decltype(comp)>( comp );
  set.insert(1);
  set.insert(10);
  set.insert(1); // Dupe!
  set.insert(2);
  std::copy( set.begin(), set.end(), std::ostream_iterator<int>(std::cout, "\n") );
}

 

//not working same code for Emp class ..need to study on this.

13.   Thread? Mutex?Race condition?

 

//t1 locked but return then it keeps locking and no one will enter in this line.SO what //is the solution instead of any synchronization?  Sol=> automic(cross check it)

 

m.lock();

i++;

return;  //above que on this line

m.unlock()

14.     what is mean by noexcept?

15.   Vec{5,6,5,6,7,6,7}

Print ans : 5-2, 6-3, 7-2

Means count the frequency of number.

Ans :

 

// Online C++ compiler to run C++ program online

#include <iostream>

#include<vector>

#include <map>

 

 

using namespace std;

 

int main()

{

    vector<int> v = {5,6,5,6,7,6,7};

    std::map<int, int> map;

    for(int i=0 ; i<v.size();i++)

    {

        auto iter = map.find(v[i]);

        if(iter!=map.end())

        {

            int val = iter->first;

            int count = iter->second;

            count=count+1;

            map.at(val) = count;

        }

        else

        {

             map.insert({v[i], 1});

        }

    }

   

 for(auto val: map)

 {

     cout<< val.first << " "<< val.second << endl;

 }

    return 0;

}

 

L&T
1.       What is mean by Multiple inheritance . Write down the classes and inheritance for that

2.       Write down the classes for diamon problem?

3.       Write down code for copy ctr?

4.       Write down code for upcasting and downcasting?

5.       What is mean by oops concept?

6.       What is mean by enum ? can we use duplicate numbers in enum(Ans-yes)?

7.       What is mean by #define ?what is the size if #define?

8.       Why will use #define and const and what is the difference

QT        

9.       Diff between Qvarient and templates

10.   Exec()?

11.   Synchronization?

12.   Can we connect multiple signals with signal slot?

13.   Can we connect single signal with multiple slots?

14.   QMap?Qvector?

15.   Blockedqueedconnection?

 

TCS
1.       More questions was on lead position

2.       Socket programming and asked if packet loss and then how to know that packet has lost.

3.       What is mean by QObject?

4.       In linux Virtual memory?

 

 

eInfoChips company
Write down the program for link list
Ans:

// Online C++ compiler to run C++ program online

#include <iostream>

#include <cstring>

using namespace std;

 

 

 

struct Node

{

int data;

Node* next;

};

 

 

 

int main() {

// Write C++ code here

struct Node* head = new Node;

head->next = nullptr;

head->data = 1;

 

struct Node* node = new Node;

node->next = nullptr;

node->data = 2;

 

head->next = node;

 

struct Node* temp = head;

while(temp !=nullptr)

{

cout << temp->data<<endl;

temp=temp->next;

}

return 0;

}

 

 String reverse
Ans: This program use second char to while reversing string;Instead of this use single char and do string reverse.

https://www.geeksforgeeks.org/reverse-a-string-in-c-cpp-different-methods/

#include<iostream>

#include<cstring>

#include <string>

using namespace std;

class String

{

    char* ch;

    int len;

 

public:

    String(char* val)

    {

        len = strlen(val);

        ch = new char[len+1];

        for(int i = 0; i< len;i++)

        {

             ch[i] = val[i];

        }

    }

    void ReverseString()

    {

        cout << "ReverseString"<<endl;

        char* val ;

        val = new char[len];

        for(int i= len-1 ;i>=0; i--)

        {

             int index=len-1-i;

             val[index] = ch[i];

        }  

       

        for(int i= 0 ;i<len; i++)

        {

            ch[i] = val[i];

        }

    }

    void Print()

    {

        for(int i = 0; i< len;i++)

        {

        cout << ch[i];

    }

}

};

 

//function to call reverse string

void ReverseStringUsingSwap(std::string& str)

{

    int n = str.length();

    cout << "len= " << n <<endl;

    for(int i =0 ;i< n/2; i++)

    {

        cout << i <<" ";

        swap(str[i], str[n-i-1]);

    }

   

    cout << str<<endl;

}

int main() {

// Write C++ code here

    std::cout << "Hello world!"<<endl;

    String obj("Abcd");

    obj.Print();

    cout <<endl;

    obj.ReverseString();

   obj.Print();

    cout <<endl;

   

    //reverse using Swap

    string str = "Rohini";

    ReverseStringUsingSwap(str);

   

    return 0;

}

 

 

Design pattern implementation of Observer pattern
 

// Online C++ compiler to run C++ program online

#include <iostream>

#include <vector>

using namespace std;

class Observer

{

public:

void Subscribe(string str)

{

cout << str <<endl;

}

};

class Subject

{

vector<Observer*> Vec;

 

public:

void AddObserver(Observer* obj)

{

Vec.push_back(obj);

}

 

void Publish(string str)

{

for(auto val: Vec)

{

val->Subscribe(str);

}

}

};

 

 

 

int main() {

// Write C++ code here

std::cout << "Hello world!"<<endl;

 

 

 

Subject subObj;

Observer obs1;

Observer obs2;

Observer obs3;

 

subObj.AddObserver(&obs1);

subObj.AddObserver(&obs1);

subObj.AddObserver(&obs3);

 

subObj.Publish("Design Pattern");

return 0;

}

Access Specifier
class A

{

public:

int a;

private:

int b;

protected:

int c;

}

class B:public A

{}

class C: private A

{}

class D:protected A

{}

 

Ans :

// Online C++ compiler to run C++ program online

#include <iostream>

using namespace std;

 

class A

{

    public:

    int a;

    private:

    int b;

    protected:

    int c;

   

    public:

    void Print()

    {

        cout << "Print A= " << a << " "<< b << " " << c << endl;

    }

  

};

 

class B:public A

{

    public:

    B()

    {

        a = 10;

        //b = 20; //Erro: int A::b' is private within this context

        c = 30;

    }

};

 

class C: private A

{

 public:

    C()

    {
    
MindTree - 
1. Write code where to allocate memory for integer variable and integer array
2. How to delete the allocated memeory above
3. Which Collection object is best for the to search the elements from the the list 
4. Write class A, with all possible functions in it
 
Mobileum - 
  1. grep command usage
  2. netstat command usage 
  3. ps command usage 
  4. how dynamic polimorphison can be implemented ?
  5. how to detect the memory leakage in application after its compilation
  6. what is smart pointer ?
 
Oracle Corporation
  1. why we cant have virtual constructor ?
  2. when v table created ?
  3. how we can implement multiple inheritance in cpp?
  4. 
  
 
 Diabold 
  1. what is signature of copy constructor and assignment operation in cpp
  
  
  
NextGen - 
1. Find the output of program 
2. What is difference between monolithic and microservices

Network Marvels - 
1. Deadlock and its conditions ?
2 malloc vs new
3. storage classes in c++

PubMatic
1. Can we implement Semaphore in UserSpace ?
2. Wait and Signal are automic operations ?
3. Deadlock and its conditions ?
4. lock vs semaphore 

Problems
        - get peek element from the unsorted array without adding extra space 
        - find the give string is ipv4 or not


Honeywell
Problem - Move linked list to the right by k
    		- Server client socker programes 
Design - How two process update one single file ?
Which Linux services used by the Docker to implement container isolation?


HCL Technologies
1. Design Problem - Three classes Keyboard Keystrock monitor, controller, and database 
How controller save key strock in database, controller has objects of Monitor and Database
2. Struc containing device id stored in Vector, how to access it quickely ?
3. difference between c++ struct and c++ class ?
Members of a class are private by default.	Members of a structure are public by default. 
It is normally used for data abstraction and further inheritance.	It is normally used for the grouping of data
4. does map key can be a user defined data type?
5. how to debug the core dump file
6. difference between global static variable vs local static variable?



		
