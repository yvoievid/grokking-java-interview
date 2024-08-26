# Grokking Java Interview (or self-marketing in action) :coffee:


## Core Java :thinking: 

<details>
    <summary style="font-size:18px">What is OOP?</summary>
        OOP is a metodology of programming that describes the program as set of objects
</details>

#### What are OOP paradigms?
There are four OOP paradigms 
- encapsulation
- polymorphism
- inheritance
- abstraction

#### Define what the encapsulation is, also tell about polymorphism, inharitance and abstraction
* Encapsulation - the programming paradigm that describes the idea of building data and methods that works on that data within one unit and hide internal representetion and state of the object from the outside providing only kind of interface.
* Polymorphism - the programming paradigm that describes the idea of having the same signature of method whith different concrete implementation
* Inharitance - the paradigm of OOP that gives a posibility for a class to use code of the other parent class 
* Abstraction - the paradigm of OOP that shows only essential information and hides unnecesary information from the user

#### What is a class?
Class - the construction of OOP that represent an real life object blueprint. It consists of variables and methods (also called characteristics and behavoiour).


#### What is constructor?
#### What is `this` keyword?
#### What is `final` keyword?
#### What is `super` keyword?


#### Data types in Java?
![alt text](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191105111644/Data-types-in-Java.jpg)

#### What is interface?
Interface the defined abstract type used to specify the bahaviour of a class. A interface in Java is a blueprint of a class. A Java interface contains static constants and abstract methods. A Java interface contains static constants and abstract methods.
Class that implements interface have to override all its method.
Like a class, an interface can have methods and variables, but the methods declared in an interface are by default abstract (only signature, no body)

```
// A simple interface

interface Player
{
    final int id = 10;
    int move();
}
```

#### What is functional interface?


#### What is abstract class?
Abstract class is a class from which you can't create an instance. Abstract class defined by `abstract` keyword. It can have have both abstract and non-abstract methods(methods with bodies). An abstract modifier can be applied for classes and methods but not for variables.

```
abstract class Shape 
{
    int color;
    // An abstract function
    abstract void draw();
}
```

#### What is anonymous class?
In a simple way, anonymous class is a class without name (lol). You can reimplement class while creating an instance of it
For example:
```
       HelloWorld frenchGreeting = new HelloWorld() {
            String name = "tout le monde";
            public void greet() {
                greetSomeone("tout le monde");
            }
            public void greetSomeone(String someone) {
                name = someone;
                System.out.println("Salut " + name);
            }
        };
```

Here `HelloWorld` class have no name, it can be implemented elsewhere but despite that we can override it with anonymous class.

#### Difference between Override and Overload
- Override - is a mechanism when you redefine implementation of the method with the smae name in child class.
- Overload - is a mechanism when you redefine implementation of the method with the same name in the same class but with different signature (arguments).

#### Nested class?
Nested class is a class that defined within another class.
A nested class has access to the membets, including private members, of the class in which it is nested. The reverse is also true, the enclosing class can access the members of the nested class.
Nested classes are divided into two categories:
- static nested class : Nested classes that are declared static are called static nested classes.
- inner class : An inner class is a non-static nested class.

| Regular Nested Class | Static nested class |
| --- | --- |
| 	Without an outer class object existing, there cannot be an inner class object. That is, the inner class object is always associated with the outer class object. | Without an outer class object existing, there may be a static nested class object. That is, static nested class object is not associated with the outer class object.|
| Inside normal/regular inner class, static members can’t be declared. | Inside static nested class, static members can be declared |
| 	As main() method can’t be declared, regular inner class can’t be invoked directly from the command prompt. | As main() method can be declared, the static nested class can be invoked directly from the command prompt.
| Both static and non static members of outer class can be accessed directly. | Only a static member of outer class can be accessed directly.


#### What is JVM?
JVM stands for Java Virtual Machine. This virtual machine compalies the java code to the bytecode that can be executed.
![alt text](https://media.geeksforgeeks.org/wp-content/uploads/jvm-3.jpg)

#### What is JIT?
JIT stands for Just in Time and is the JVM's mechanism to optimize code at runtime. 
It can perform code inlining, lock coarsening, lock eliding, escape analysis, and other optimizations.

![alt text](https://media.geeksforgeeks.org/wp-content/uploads/CommonArticleDesign20-min-1.png)

#### What access modifiers are available in Java?
- public
- private
- protected 
- default
  
![alt text](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Access-Modifiers-in-Java.png)

#### Difference between equals and hashcode 
Basicly, equals and hashcode are methods that are used for object comparison. Each class should override this two methods to define the method of evaluating differense of objects of it's class. To have quick comparison of objects it's good to have some numeric representation of object, that's where `hashCode` kick in. By overriding this method you define a method of calculating special number that will be returned after executing. That will be a unique identifier for object, but there is a problem - there are not a lot of numbers actualy( . That's where `equals` kicks in. By overriding that method you define the comparison of objects usings their fields when comparison by `hashCode` isn't enought.

#### Difference between functional programming and object oriented programming
OOP uses objects and methods as the key coding elements, while FP emphasises functional factors such as variables and functions. 
Functional programming is the form of programming that attempts to avoid changing state and mutable data. In a functional program, the output of a function should always be the same, given the same exact inputs to the fucntion (pure functions)

- OOP does follow imperative programming model, while FP follows declarative programming model
- FP supports parallel programming while OOP doesn't
- In FP the statements can be executed in any order while in OOP there is particular order
- FP basic elements: variables and functions. OOP basic elements: objects and methods
  
Object-oriented languages are good when you have a fixed set of operations on things, and as your code evolves, you primarily add new things. This can be accomplished by adding new classes which implement existing methods, and the existing classes are left alone.

Functional languages are good when you have a fixed set of things, and as your code evolves, you primarily add new operations on existing things. This can be accomplished by adding new functions which compute with existing data types, and the existing functions are left alone.

#### Difference between comparator and comparable
Comparable - is an interface defining a strategy of comparing an object with other objects of the same type. This is called the class's "natural ordering"

```
public class Player implements Comparable<Player> {

    @Override 
    public int compareTo(Player otherPlayer) {
        return Integer.compare(getRanking(), otherPlayer.getRanking());
    }
}
```
<b>The sorting order is decided by the return value of the compareTo() method</b> 

Comparator - interface that defines a compare(arg1, arg2) method.
and works similarly to the Comparable.compareTo() method

```
public class PlayerAgeComparator implemets Comparator<Player> {
    @Override
    public int compare(Player firstPlayer, Player secondPlayer) {
        return Integer.compare(fisrtPlayer.getAge(), secondPlayer.getAge());
    }
}
```
#### Difference between stack and heap?
The stack is the memory set aside as scratch space for a thread of execution. The stack is a memory space that is used by threads for holding the function pointer, attributes and local variables. When a function is called a block is reserved on the top of the stack for local variables and some bookkeping data. When that function returns, the block becomes unused and can be used the next time a function is called. The stack is always reserved in a LIFO (last in first out) order.

The heap is the memory set aside for dynamic allocation. Unlike the stack, there's no enforced pattern to the allocation and deallocation of blocks from a heap. This makes it very hard to track of which parts of the heap are allocated or free at any given time.

![alt text](https://www.baeldung.com/wp-content/uploads/2018/07/java-heap-stack-diagram.png)


In Java, memory management is divided into two main areas: the heap and the stack. These two memory areas are used for different purposes and have distinct characteristics.

1. Heap
Definition: The heap is a portion of memory used for dynamic memory allocation. All objects and their instance variables are stored in the heap.
Lifetime: Objects in the heap have a longer lifespan and exist as long as they are referenced. When they are no longer referenced, they become eligible for garbage collection.
Access: Objects in the heap are accessed via references stored in the stack. Memory allocation and deallocation for the heap are managed automatically by the garbage collector.
Size: The heap is typically larger than the stack and can grow as needed, limited by the maximum heap size set by the JVM.
Usage:
Objects and instance variables.
Shared across all threads.
2. Stack
Definition: The stack is a region of memory that stores method call frames, including local variables, method parameters, and the return address.
Lifetime: Variables in the stack exist only for the duration of the method call. Once the method execution is completed, the corresponding stack frame is removed, and the memory is reclaimed.
Access: The stack follows a Last-In-First-Out (LIFO) order. Each thread in Java has its own stack, making it thread-safe without requiring synchronization.
Size: The stack size is generally smaller than the heap. Its size is fixed when the thread is created, and if the stack memory limit is exceeded, a StackOverflowError is thrown.
Usage:
Primitive data types and references to objects.
Method call information, including parameters, local variables, and return addresses.
Key Differences
Memory Location:

Heap: Dynamic memory (shared among threads).
Stack: Static memory (private to each thread).
Lifetime:

Heap: Objects persist as long as they are referenced.
Stack: Variables persist only within the method call.
Speed:

Heap: Slower access due to dynamic memory allocation and garbage collection.
Stack: Faster access due to its LIFO nature.
Garbage Collection:

Heap: Managed by the garbage collector.
Stack: Managed automatically when the method call ends.
Thread Safety:

Heap: Requires synchronization for thread safety.
Stack: Thread-safe as each thread has its own stack.



#### What is Java Collection Framework?
> JCF - collection of linked classes and interfaces that implements commonly reusable data structures.

![alt text](https://highload.today/wp-content/uploads/2021/08/image8-3.png)


#### Exception hierarchy
![alt text](https://sematext.com/wp-content/uploads/2021/09/java-exceptions-1.png)


#### Exception Handling
1. Checked Exceptions Definition: Checked exceptions are exceptions that are checked at compile-time. The compiler ensures that these exceptions are either caught or declared in the method's throws clause.
   Examples:
   IOException
   SQLException
   FileNotFoundException
   Handling: They must be either caught using a try-catch block or declared in the throws clause of the method.
2. Unchecked Exceptions
   Definition: Unchecked exceptions, also known as runtime exceptions, are not checked at compile-time. These exceptions occur during the execution of the program.
   Examples:
   NullPointerException
   ArrayIndexOutOfBoundsException
   ArithmeticException
   Handling: Unlike checked exceptions, unchecked exceptions do not need to be explicitly handled or declared in the throws clause.
3. Errors
   Definition: Errors are not exceptions but issues that occur in the JVM, typically beyond the control of the application. These are usually serious problems that applications are not expected to catch.
   Examples:
   OutOfMemoryError
   StackOverflowError
   VirtualMachineError
   Handling: Errors generally indicate serious issues and are not meant to be caught by application code. They are usually unrecoverable.

#### CAP theorem
![alt text](https://miro.medium.com/v2/resize:fit:1400/0*Qfb1P6Pkm2-dY1UB.png)


#### What is Stream API?
Stream API is an way that makes work with data structures easier in functional style.
Stream API allows you to write structure processing in followig way.

Non Stream API:
```
        Integer sumOddOld = 0; 
        for(Integer i: collection) {
            if(i % 2 != 0) {
                sumOddOld += i;
            }
        }
```

Stream API:
```
       Integer sumOdd = collection.stream().filter(o -> o % 2 != 0).reduce((s1,s2 -> s1 + s2).orElse(0);
```
 
#### Terminal and Intermediate operations
- Terminal - returns another object such as collections, primitives, objects, Optiona etc.
- Intermediate - returns another stream working as a builder

General Rule:
There can be a lot <b>Intermediate</b> operations in the middle but just one <b>Terminal</b> operation in the end
Intermediate operations are executed in a lazy way so till terminal operation is not executed there will be no actions. 

#### What is Maven?
Maven is a software for automatiion build based on structure files called POM (Project Object Model)

#### Maven lifecycle
- validate - validate the project is correct and all necessary information is available
- compile - compile the source code of the project
- test - test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
- package - take the compiled code and package it in its distributable format, such as a JAR.
- verify - run any checks on results of integration tests to ensure quality criteria are met
- install - install the package into the local repository, for use as a dependency in other projects locally
- deploy - done in the build environment, copies the final package to the remote repository for sharing with other developers and projects.
  
#### Processes vs Threads
An application consists of one or more processes. A process in an executing program. One or more threads run in the context of the process. A thread is the basic unit to which the operating system allocates processor time. A thread can execute any part of the process code, including parts currently being executed by another thread (shared memory)

<i> <b>Job object</b>  
A job object allows groups of processes to be managed as a unit. Job objects are namable, securablem sharable objects that contro attributes of the processes associated with them. Operations performed on the job object affect all processes associated with the job object
</i>  

#### Synchronized keyword
Synchronized keyword is applied to method/attribute to prevent `race condition` between two threads that use shared resource. 

#### Runnable vs Callable
Callable interface and Runnable interface are used to encapsulate tasks supposed to be executed by another thread.

However, Runnable instances can be run by Thread class as well as ExecutorService but Callable instances can only be executed via ExecutorService.

<i>Callable Interface</i>

In a callable interface that basically throws a checked exception and returns some results.
```
    public interface Callable<V> 
    {
        V call() throws exception ;
    }
```
1. It is declared in the 'java.util.concurrent' package
2. This interface also contains a single, no-argument as a parameter.
3. We can't create a thread by passing callable as a parameter.
4. Callable can return results. Callable's `call()` method contains the "throw Exception" clause, so we can easily propagate checked exceptions further.
   
<i>Runnable interface</i>

When an object implementing this interface is used to create a thread, staring the thread causes the object run method to be called in a separately executing thread.
```
    public interface Runnable 
    {
        public abstract void run();
    }
```

#### Concurrent Map
ConcurrentMap is an extension of the Map interface. It aims to provides a structure and guidance to solving the problem of reconciling throughput with thread-safety.

By overriding several interface default methods, ConcurrentMap gives guidelines for valid implementations to provide thread-safety and memory-consistent atomic operations.

Several default implementations are overridden, disabling the null key/value support:

getOrDefault
forEach
replaceAll
computeIfAbsent
computeIfPresent
compute
merge
The following APIs are also overridden to support atomicity, without a default interface implementation:

putIfAbsent
remove
replace(key, oldValue, newValue)
replace(key, value)
The rest of actions are directly inherited with basically consistent with Map.


#### String vs StringBuilder vs SpringBuffer
- String is immutable whereas StringBuufer and StringBuilder are mutable classes.
- StringBuffer is thread-safe and synchonized whereas StringBuilder is not, that is why StringBuilder is faster than StringBuffer.
- String concatenation operator (+) internally uses StringBuffer or StringBuilder class.
- For String manipulations in a non-multi threaded environment, we should use StringBuilder else use StringBuffer class
- When we create a string using double quotes, JVM first looks for the String with the same value in the string pool. If found, it returns the reference of the string object from the pool. Otherwise, it creates the String object in the String pool and returns the reference. JVM saves a lot of memoty by using the same String in defferent threads.
  

#### App server vs Web server
Web Server is a computer program that accepts the request for data and seds the specified documents. Web server may be a computer where the online concept is kept. Essentially internet server is employed to host sites however there exist different web servers conjointly like recreation, storage, FTP, email, etc.
Web Servers: Apache HTTP Server, Nginx

Application encompasses Web container as well as EJB container. Application servers organize the run atmosphere for enterprises applications. 
Application Server Examples: Weblogic, JBoss, Websphere.

#### Java 8 Thingies
- lambdas 
- functional Interfaces
- streams
- optional class
- default method realisation in interface;
- collectors class 

#### What is Generics and what they for
Let's immagine tha situation when you need to create a List in Java and store a value
```
List list = new LinkedList();
list.add(new Integer(1)); 
Integer i = list.iterator().next();
```

On the last line compiler will argue because the type of retrieving value should be specified
The compiler will ask for explisit casting

```
Integer i = (Integer) list.iterator().next();
```

There is no contract that will guarantee that return type will be an integer.
The defined list could hold any object 
We can impove this using dimond `<>` operator when we define a list

```
List<Integer> list = new LinkedList();
```

Now we specified type inside the list. The compiler can enforce type at compile time

In small programs it may seem like a trivial addition, but in large ones it can add sugnifficant robustness and make easier to read

Generic Methods



## Spring Core

#### What is Dependency Injection
Dependency Injection is a mechanism of passing dependency to other object or framework. The injection can be done through constructor. 

#### What is Invertion of Control
Inversion of Control is a pattern, that provides king of callback, instead of ourself directly, in other work passing the dependency with constructor

#### What are Spring beans
In Spring, the objects that form the backbone of your application and that are managed by the Spring IoC container are called beans. A bean is an object that is instantiated, assembled, and otherwise managed by a Spring IoC container.

#### Spring Security
Spring Security is a framework that focuses on providing both authentication and authorization to Java applications. Like all Spring projects, the real power of Spring Security is found in how easily it can be extended to meet custom requirements.

#### What are benefits of using Spring?

- Lightweight. The basic version of the Spring framework is around 2MB, making Spring lightweight in terms of size and transparency.

- Inversion of Control (IoC). Spring uses the technique of IoC to achieve loose coupling and give objects their dependencies instead of creating or searching for dependent objects.

- Container. Spring manages and contains the configuration of application objects, as well as their life cycles.

- Aspect Oriented (AOP). Spring supports Aspect-oriented programming. It also separates application business logic from system services to enable cohesive development.

- MVC framework. Spring utilizes a well-designed MVC framework that is efficient and popular in comparison to other types of web frameworks.

- Transaction management. Spring’s consistent management interface can be scaled up or down for global and local transactions.

- Exception handling. Spring’s application programming interface (API) translates technology-specific exceptions into consistent, unchecked exceptions.

#### What is Spring Data
Spring Data is a projects that covers multiple technologies for accessing DB data using Spring Framework. It includes such things as Spring JPA and Spring JDBC

## Git

#### basic commands (commit, checkout, push, pull, merge, rebase)
- git commit - creates a copy of your source code but containing only difference that you made.
- git checkout - allows you to switch between branches that were created by `git branch` 
- git push - uploads local commited changes to the remote branch
- git pull - uploads remote changes to the local repo
- git rebase - reapply commits on another base tip
- git merge - aggregates two different commits into one commit history

 - difference between merge and rebase

## Databases

#### What are subsets of SQL?
- Data Definition Language (DDL)
  DDL queries are made up of SQL commands that can be used to define the structure of database and modify it
  - CREATE
  - DROP
  - DROP COLUMN
  - ALTER
  - TRUNCATE:  Removes tables, views, procedures, and other database objects
  - ADD COLUMN
- Data Manipulate Language (DML)
  - SELECT
  - INSERT 
  - UPDATE
  - DELETE: Deletes records from the table 

#### UNION vs UNION ALL
The UNION is equal to UNION ALL, except that UNION ALL will not eliminate duplicate rows

#### Indexes
An index is performance tuning method of allowing faster retrieval of records from the table. An index creates an entry for each value and it will be faster to retrieve data.

#### Clustered vs Non-Cludstered Indexes
There are three types of indexes:

`Unique Index`
This indexing does not allow the field to have duplicate values if the column is unique indexed. Unique index can be applied automatically when primary key is defined.

`Clustered Index`
This type of index reorders the physical order of the table and search based on the key values. Each table can have only one clustered index.

`NonClustered Index`
NonClustered Index does not alter the physical order of the table and maintains logical order of data. Each table can have 999 nonclustered indexes.

#### Relations (One to One, Many to Many, One to Many)
#### Index fragmagtation
#### What is 2nd normal form
#### What is 3rd normal form
#### What is Boise-Code normal form
#### Trigger
#### Group By / Order by
#### Joins (outer, inner, left, right)

#### ACID 
ACID is an collection of rules that guarantees good work of transaction
- Atomarity - trasaction executes from start to end or don't executes at all
- Consistency - the system have to be in consistent state before and after transaction
- Isolation - the changes that are made withing transaction will not be vissible till transaction ends
- Durability - despite of probles of the system the results of commited transactions will be saved
  
#### Isolation Levels
- Read Uncommited
- Read Commited
- Repeatable Read
- Serializable

## Networks
#### HTTP request methods
 - GET 
 - POST 
 - PUT
 - DELETE
 - HEAD
 - DELETE
 - PATCH
 - OPTIONS
 - CONNECT
 - TRACE
  
#### GET vs POST 
- GET request can be cached
- GET request remain in browser history
- GET request can be bookmarked
- GET request should never be used when dealing with sensitive data
- GET requests have length restrictions
- GET requests are used only to modify data
  
- POST requests are never cached 
- POST requests DO NOT remain in browser history
- POST request can not be bookmarked
- POST requests have no restrictions on data length


#### TCP/IP 


#### DNS server


#### DHCP server


#### Error codes

1xx informational response – the request was received, continuing process
2xx successful – the request was successfully received, understood, and accepted
3xx redirection – further action needs to be taken in order to complete the request
4xx client error – the request contains bad syntax or cannot be fulfilled
5xx server error – the server failed to fulfil an apparently valid request



## Algorithms and Data Structures

## Datastractures

### Map
#### HashMap
#### TreeMap
#### SortedMap

### List
#### ArrayList
#### LinkedList
#### Stack

### Tuple

### Tree
#### Red-Black tree
#### Binary tree


### Array 

## Algorithms 

### Search
#### Binary search
#### Wide first search
#### Breadth first search

### Sorting 
#### Bubble sort

#### Quick sort
#### Merge sort


## Unix 

#### Difference between sudo and root
root - user, sudo - command to 

#### Semaphores and mutexes 

## Clean Code Thingies

### What is TDD?
### Define SOLID principles
 SOLID is a mnemonic acronym for five design principles intended to make object-oriented designs more understandable, flexible, and maintainable. 

 - S - Single responsibility prinsiple
 - O - Open closed principle
 - L - Liskov substitution principle
 - I - Interface segregation principle
 - D - Dependency inversion principle

### Define DRY principles

## Docker Thingies

#### What is container?
#### What is image?

## RegExps

## Code Thingies

### How many objects will be created?
String s1="Lviv" ;
String s2="Kyiv" ;
String s3="Lviv" ;
String s4=new String("Kyiv");

answer: 3, because of String Pool


healthcare 
microservices занадто сильно роздробили
transaction management
rest api
compensational transaction
spring streams
saga
POC, RabbitMQ
MQTT brokers 

is java crossplatform vs multiplatform 
Is Java pure OOP language: static not object
Problems of perfect infrastructure (with perfect patterns)
big O
hardly readable
a lot of memory usage
time of execution

microprocessor

Generics 
Type check to compile time 

List<?> 
producer super producer extend
? - for backport compatability

Service vs Component

holywar: Autowired on fields 

Where suitable to make beans with constructors

What are good points with spring boot (dependensies)

NoSQL vs SQL databases

CAP theorem

MISK vs RISK

Maturity levels of REST

Usage of OPTION 

What happend when u type url on browser

What is better than HTTP -> websocket?

JRPC

What is wrong with HTTP -> TTL?

Reactive, Reactor Native, WebFlux

What is saga, 

what was before microservice

What are problems of microservices 

circuit breaker in microserver

Contracts

DDD 

What is DevOps

Mock vs Stab

TDD

Spring Contracts

REST maturity levels

scrum artefacts
