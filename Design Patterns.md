2. Write about Description of Design Patterns?

When the central elements a design are abstracted from a particular solution and found to apply to a number of different solutions, 
we have a design pattern. While patterns in designs can be observed in many domains - from building architecture to object-oriented programming - 
the Open Source Design Pattern Library will initially focus on user experience patterns. 
A design pattern usually arises through a combination of creativity and discovery. They are sometimes seen to appear in the wild: a design is observed to have a wider application than its existing implementation, and someone records a description of it in general terms.

Formally, the term "design pattern" has been defined as a proven solution to a common problem within a specified context. Let's explore the details of this definition.
Here, the word proven means "tested or tried", with implications of trustworthiness and reliability. A design pattern is proven through assessment by design experts, and demonstrations that effective designs can be derived from it.
The word common in our definition simply means "recurring". Design patterns address problems that occur over and over.
Specified context also deserves some explanation. The context description tells us where the pattern works and where it doesn't. When a designer seeks guidance from a design pattern, she must match the context of the problem she is trying to solve with the range of contexts in which the pattern has been shown to be useful.

Elements of a Design Pattern
The core elements of a design pattern are:
Statements of the problem it addresses, and the offered solution.
The scope of a pattern's usefulness is outlined the context description - the situations in which the pattern leads to workable results.
User interface patterns also include visual examples of how implementations based on the pattern will appear to the user.
Context Outline
The context outline describes the set of contexts in which the pattern is effective in responding to what the user needs. It may also indicate situations where the pattern is not a useful guide for the creation of designs.
Problem Statement
The problem statement is an expression of what the user needs to do, perceive, or understand.
Solution
The solution statement explains how the user's problem is solved through a clear and understandable set of steps and perceptions. Solutions are often expressed through strong visual metaphors which help the user understand the process taking place.

The design pattern centres on the user's problem, and how it may occur in a variety of circumstances. The pattern provides a solution outline that employs well-established design principles. It is a model on which a designer can base solutions to specific cases of the problem.

The designer makes design choices within the guidelines set by the design pattern. These are influenced by information that brings specificity to the problem. There will be personas that describe the user's likely intentions and desires as well as use cases that describe the user's objectives. All these serve to limit the scope of the problem to the application context, which should always be compatible with the design pattern context. The design description is user-focused, centring on the user's behaviour in interaction with the service.

A specification is a precise description of the behaviour of the service in its interactions with the user. Once a specification has been set, there are no user-perceptible design choices left to be made. To put this another way, a specification carries sufficient design information that different implementations – by different implementers – are behaviourally indistinguishable to the user.

3. Write about Catalog of Design Patterns

Design patterns divided into 3 categories.

1. Creational
2. Structural
3. Behavioral

1. Creational Design Patterns

 Which is responsible for efficient object creation mechanisms, which increase the flexibility and reuse of existing code.

1. Creational Design Patterns is divided into 5 types
* Factory Method 
		 
Define an interface for creating an object, but let subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses. The Factory Method pattern suggests replacing direct object creation (using a new operator ) with a call to a special "factory" method.  Objects returned by factory methods are often referred to as "products".
		  
* Abstract Factory
            
Provide an interface for creating families of related or dependent objects without specifying their concrete classes. First thing that Abstract Factory pattern suggests is to go over all distinct products and  force their variants to follow common interfaces. The second step is to create the AbstractFactory, a base interface that declares methods for creating all products that make a product family. The third step is to implement concrete factories. Factories are classes that return products of a particular kind. All factories must follow the AbstractFactory interface while creating the same variety of products. AbstractFactory classes are often implemented with Factory Methods, but they can also be implemented using prototype.
			
* Builder
      
Builder Pattern separate the construction of a complex object from its representation so that the same construction process can create different representations.
   
* Prototype
    
Prototype is a creational design pattern that lets you produce new objects by copying existing ones without compromising their internals. It delegates cloning process to objects themselves. It can help when you need to save copy of the command into history.
	   
* Singleton
      
Singleton is a creational  design pattern that lets you ensure that a class has only one instance and provide a global access point to this instance. It solves two problems at the time (violating Single Responsiblity Principle). 1. Ensures that a class has only a single instance.
2. Provides global access point to that instance.
	   All singleton implementations share two common steps: 
	   1. Making the default constructor private
	   2. Creating a static creation method that will act as a constructor. This method creates an object using the private constructor and saves it in static variable or field. 
	   All following calls to this method return the cached object.
	   
2. Structural Design Patterns :
		Structural design patterns are responsible for building simple and efficient class hierarchies and relations between different classes.

Divided into 7 types 

2.1  Adapter

             Adapter is a structural design pattern that allows objects with incompatible interfaces to collaborate. You can create an Adapter. It is a special object that converts calls sent by one object to the format that another object can understand. Adapter wraps one of the objects to hide the complexity of conversion happening behind the scenes.
			 Adapters can convert not only data formats but also interfaces. 
2.2  Bridge
    
	        Bridge is a structural design pattern that lets you split a giant class or a set of closely related classes into two separate hierarchies, abstraction and implementation, which can be developed independently of each other.
2.3  Composite
          
		  Composite is a structural design pattern that lets you compose objects into tree structures and allow clients to work with these structures as if they were individual objects

2.4 Decorator
  
        Decorator is a structural design pattern that lets you attach new behaviors to objects by placing them inside wrapper objects that contain these behaviors.
		
2.5  Facade
       Facade is a structural design pattern that lets you provide a simplified interface to a complex system of classes, library or framework.
	   
2.6  Flyweight
       Flyweight is a structural design pattern that lets you fit more objects into the available amount of RAM by sharing common parts of object state among multiple objects, instead of keeping it in each object.

2.7 Proxy
        Proxy is a structural design pattern that lets you provide a substitute or placeholder for another object to control access to it.
 
3. Behavioral Design Patterns
		Behavioral patterns are responsible for the efficient and safe distribution of behaviors among the program's objects. 

3.1. Chain of Responsibility 
       Chain of Responsibility is a behavioral design pattern that lets you avoid coupling the sender of a request to its receiver by giving more than one object a chance to handle the request. Chain the receiving objects and pass the request along the chain until an object handles it.

3.2  Command
        Command is a behavioral design pattern that lets you turn a request into stand-alone object, which can be used to parametrize objects with different requests, queue or log requests, and support undoable operations.
		
3.3 Intent
         Iterator is a behavioral design pattern that lets you access the elements of an aggregate object sequentially without exposing its underlying representation.

3.4 Mediator
         Mediator is a behavioral design pattern that lets you define an object that encapsulates relations between a set of objects to make them independent of each other.

3.5 Memento
        Memento is a behavioral design pattern that lets you capture the object's internal state without exposing its internal structure, so that the object can be returned to this state later.

3.6 Observer
        Observer is a behavioral design pattern that lets you define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

3.7 State
      State is a behavioral design pattern that allows an object to alter its behavior when its internal state changes. The object will appear to change its class.

3.8 Strategy
     Strategy is a behavioral design pattern that lets you define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from the clients that use it.

3.9  Template Method
     Template Method is a behavioral design pattern that lets you define the skeleton of an algorithm and allow subclasses to redefine certain steps of the algorithm without changing its structure.

3.10 Visitor
     Visitor is a behavioral design pattern that lets you define a new operation without changing the classes of the objects on which it operates.



  
  
