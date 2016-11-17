# JAVA  
In this document, I'm trying to write down all my understanding after reading **Thinking in Java**

### Tree main features in Object-Oriented programming
* Data encapsulation or data abstraction
* Inheritance or derivation
* Dynamic or runtime binding or late binding or polymorphism

### Polymorphism
* Why we need to use polymorphism? Idea is "separate the things that change from the things that stay the same." That means we could use a base class as a provider of some services. In this way we could keep using the same operation or logic , even if there is a big change inside the derived classes.

### Binding
* Definition: Connecting a method call to a method body is called binding
* There are two types of binding: _early binding_ and _late binding_. Java is using _late binding_ which means the binding is performed after the program running
* __BUT__ if the method is declared with static or final then than the early binding occurs. __ATTENTION__ here, all __private__ method are implicitly __final__. This is really reasonable because those method won't be modified during the execution. In other words, all method binding in Java happens Polymorphically via _late binding_.

### Just in time
* JIT (just-in-time) compiler convert the program into native machine code without any interpretation through JVM. That's why people say Java have a good performance.
* The __.class__ file will be located when this class must be loaded (typically when the first object of this class needs to be created or the static field is used).
* The Java HotSpot takes the similar approach. By the way, the Java HotSpot is one of the implementation of JVM concept, which is developed by Sun and now owned by Oracle.

### Object
#### Reference
We should treat everything as an object in Java. But we won't directly do the operations on it. Normally we manipulate on a "reference".
##### Little tips
Is Java pass-by-value or pass-by-reference?<br>
**Java is always pass-by-value**<br>
Here are two great answers on stackoverflow: [What's the difference between passing by reference vs. passing by value?](http://stackoverflow.com/questions/373419/whats-the-difference-between-passing-by-reference-vs-passing-by-value) and [Is Java “pass-by-reference” or “pass-by-value”?](http://stackoverflow.com/questions/373419/whats-the-difference-between-passing-by-reference-vs-passing-by-value)

**[]TODO: reference and primitive type **

#### Create object
- Register
- The stack
- The heap
- Constant storage
- Non-RAM storage

#### Destroy object

### Garbage collector
