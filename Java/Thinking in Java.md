# JAVA  
In this document, I'm trying to write down all my understanding after reading **Thinking in Java**

## Three main features in Object-Oriented programming
* Data encapsulation or data abstraction
* Inheritance or derivation
* Dynamic or runtime binding or late binding or polymorphism

## Polymorphism
* Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.
* Why we need to use polymorphism? Idea is "separate the things that change from the things that stay the same." That means we could use a base class as a provider of some services. In this way we could keep using the same operation or logic , even if there is a big change inside the derived classes.

### Overloading and Overriding
* **Overloading**:
The use of name is one of the most important features in ANY programming language. A well-chosen name can help reader having a better understanding for the program. In C the name of method is required as an unique ID. But Java have something much more reasonable and powerful -- the Overloading which allows the same name methods to be used with different arguments. That is what happens in real life. Like reading, we can read the paper books, but meanwhile we can also read the digital books. So here we have the same name action (method) -- reading, but handling on different objects (paper books and digital books).
* **Overriding**:
It happens in inheritance. That means the child classes could rewrite the same name method's logic in parent classes. Thanks to polymorphism, the part of the code that finally executed could be decided at runtime.

### Binding
* Definition: Connecting a method call to a method body is called binding
* There are two types of binding: _early binding_ and _late binding_. Java is using _late binding_ which means the binding is performed after the program running
* __BUT__ if the method is declared with static or final then than the early binding occurs. __ATTENTION__ here, all __private__ method are implicitly __final__. This is really reasonable because those method won't be modified during the execution. In other words, all method binding in Java happens Polymorphically via _late binding_.

### Composition and inheritance
Both of them allow you to place super objects inside a new class. The composition is explicit and the inheritance is implicit.<br>
The composition is generally used when you want to use the features of this object, but not its interface. So in case, you embed objects as private fields in the new class. If you are much more interested in its interface, do with inheritance.

### Interface and abstract class
* **Abstract class**: it's the midway between the traditional class and the interface.
  - Abstract method: declare with keyword **abstract**. This is a method which has only declaration and no method body.
  - A class containing abstract classes is called **Abstract class**.
  - An abstract class cannot be instanced.
  - It's possible to make a class abstract without any abstract method. It's useful when you want to prevent any instance of this class.
* **Interface**
  - The interface is a completed abstract class without providing any implementation.
* **Differences**
  - Use **implements** to inherit interface but **extends** for abstract classes.
  - All fields in interface are implicitly **public**, **final** and **static**.
  - You can do access control on abstract class's methods but at least **protected**. All methods declare inside interface are directly and implicitly **public**.
  - Interface can have multiple inheritances but abstract class can only have one.

### Inner class
We can place the definition of a class inside another class, which is called inner class. It looks like a simple hide-code mechanism. Since the inner class can communicate with surrounding class, it provide a simple approach to group the code that logically belong together. Be careful when you want to instant an inner class, you must use an object of the outer class to make an object of the inner class.

## Just in time
* JIT (just-in-time) compiler convert the program into native machine code without any interpretation through JVM. That's why people say Java have a good performance.
* The __.class__ file will be located when this class must be loaded (typically when the first object of this class needs to be created or the static field is used).
* The Java HotSpot takes the similar approach. By the way, the Java HotSpot is one of the implementation of JVM concept, which is developed by Sun and now owned by Oracle.

## Reference
We should treat everything as an object in Java. But we won't directly do the operations on it. Normally we manipulate on a "reference".
### Little tips
Is Java pass-by-value or pass-by-reference?<br>
**Java is always pass-by-value**<br>
Here are two great answers on stackoverflow: [What's the difference between passing by reference vs. passing by value?](http://stackoverflow.com/questions/373419/whats-the-difference-between-passing-by-reference-vs-passing-by-value) and [Is Java “pass-by-reference” or “pass-by-value”?](http://stackoverflow.com/questions/373419/whats-the-difference-between-passing-by-reference-vs-passing-by-value)

## Object
### Create object
* Where storage lives:
  - Register: the fastest, inside processor
  - The stack: the primitive values
  - The heap: all java objects live here
  - Constant storage
  - Non-RAM storage
* Normally the variable holds the reference of object. Creating an object by **new** is not really efficient, because it happens on the heap. The primitive variable holds the values directly and placed on the stack. There is a special type of class called "wrapper" which allows developer to create a object on heap holding a primitive data, such as **_Integer_**, **_Double_**, etc..

### Destroy object
Never need to destroy an object by hand. The reference vanishes when out of scope, but the object is still occupying the memory. The garbage collector will take care of destruction when it's needed. So here will be some secure issues.**ATTENTION** For instance, you generated a private key and keep it as an java.secure.PrivateKey variable. In this case, when it's out of scope, the value of private key can still be retrieved from memory. That's a big secure risk! So basically, you can put this part of sensitive code inside try catch block and do the cleaning in the **final**.

### Garbage collector

## Container
- Two types of container: Collection and Map
  - Collection: a sequence of individual elements with one or more rules applied to them.
    - List: The list hold the elements in the way as they were inserted.
    - Set: Cannot have duplicate elements
    - Queue: 
  - Map: a group of key-value object pair, allowing to retrieve the value by key.

**[TODO]** List Map Stack Set Queue, Collectors vs Iterators
## Enum
## Exception
## Concurrency
## I/O
