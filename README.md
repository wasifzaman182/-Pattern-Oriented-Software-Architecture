# -Pattern-Oriented-Software-Architecture
This repo will cover patterns and usage of patterns in software architectures

![Screenshot (23)](https://github.com/wasifzaman182/-Pattern-Oriented-Software-Architecture/assets/75499379/fd581cfb-795e-418c-b2fa-709d5d8ab450)

# Behavioral pattern
     1)  In software engineering, behavioural design patterns are **design patterns** that identify common communication patterns among objects. By doing so, these 
         patterns increase flexibility in carrying out communication. Below are some of them
               i) Strategy Pattern
               ii) Template Pattern
               iii) Command Pattern
               
# Software design pattern
      1) A software design pattern is a **general, reusable solution** to a commonly occurring problem within a given context in software design.
# Strategy Pattern
      1) The strategy pattern (the policy pattern) is a behavioural software design pattern that enables selecting an algorithm at runtime.
      2) Instead of implementing a single algorithm directly, code receives run-time instructions as to which in a family of algorithms to use.
      3) The concept of using design patterns to describe how to design flexible and reusable object-oriented software
      4) Deferring which algorithm to use until runtime makes the calling code more flexible and reusable.
      
#### Strategy and open/closed principle
    1) The behaviours of a class should not be inherited.
    2) Instead they should be encapsulated using interfaces.
    3) This is compatible with the open/closed principle (OCP), which proposes that classes should be open for extension but closed for modification.
## Question 1, What happens when a system has an explosion of Strategy objects? Is there some way to better manage these strategies?
 ##### 1 Use a Hierarchy:
          Organize related strategies into a hierarchy. This can help reduce the number of distinct classes and create a more structured organization. Common behaviours can be placed in higher-level strategy classes, while specific 
           variations can be implemented in subclasses.

##### 2 Group Strategies with Composite Pattern:
          Apply the Composite Pattern to group-related strategies. This allows you to treat individual strategies and composite groups of strategies uniformly. Clients can work with both individual strategies and compositions of                    strategies.

##### 3 Parameterize Strategies:
     Consider parameterizing strategies to make them more flexible. Instead of creating a new class for each variation, you can have a single strategy class with parameters that determine its behaviour. This can reduce the number of 
     distinct classes.

##### 4 Use Reflection or Configuration:
     Use reflection or configuration files to dynamically load and instantiate strategy classes. This allows you to add new strategies without modifying the code. However, be cautious with this approach, as it might sacrifice type safety.

##### 5 Apply Design Patterns:
     Explore other design patterns that may help manage a large number of classes. For example, the Factory Method pattern can be used to encapsulate the instantiation of strategy objects. The Abstract Factory pattern can provide 
    an interface for creating families of related or dependent strategies.

##### 6 Consider Dynamic Strategies:
     Allow strategies to be dynamically composed at runtime. This involves using techniques such as dependency injection or employing frameworks that support dynamic strategy composition.

##### 7 Apply Dependency Injection:
      Use dependency injection to inject the appropriate strategy implementation into the client code. This can be done through constructor injection, setter injection, or method injection.

##### 8 Prioritize Essential Strategies:
     Identify essential or commonly used strategies and focus on optimizing and maintaining those. Less frequently used or specialized strategies can be managed separately.

##### 9 Documentation and Naming:
     Ensure clear documentation and naming conventions for strategies to make it easier for developers to understand and choose the appropriate strategy.

##### 10 Testing Strategies:
     Implement comprehensive testing for each strategy to ensure that variations are behaving as expected. Automated tests can help maintain correctness during changes.

## Question 2 In the implementation section of the strategy pattern in [GHJV95], the authors describe two ways in which a strategy can get the information it needs to do its job. One way the strategy object could get passed a reference to the context object, thereby giving it access to context data. But is it possible that the data required by the strategy will not be available from the context’s interface? How could you remedy this potential problem?

     In the Strategy Pattern, the strategy objects can obtain the information they need to perform their tasks in two main ways: either by having a reference to the context object or by obtaining the required data through the context's interface. However, there might be cases where the data required by the strategy is not available from the context's interface. Here are some approaches to remedy this potential problem
##### 1 Enhance Context Interface:
     If the required data is not available in the existing context interface, consider enhancing the interface to include methods that expose the necessary data. This approach allows strategies to obtain the required information directly from the context.

##### 2 Additional Parameters in Strategy Methods:
     Modify the methods of the strategy interface to accept additional parameters. These parameters can be used to pass the required data from the context to the strategy. This approach allows for flexibility in providing the necessary information.

##### 3 Context Delegation:
     Instead of passing the entire context object, pass a delegation object to the strategy. The delegation object would expose only the relevant data needed by the strategy. This way, the strategy gets access to the required information without exposing the entire context.

##### 4 Dependency Injection:
     Use dependency injection to inject the required data into the strategy. This can be done through constructor injection, setter injection, or method injection. Dependency injection allows for better decoupling between the context and the strategy.

##### 5 Context Aggregation:
     Aggregate the context with other objects that provide the necessary data. This way, the strategy can access the required information by navigating through the aggregated objects. This approach can be beneficial when the required data is scattered across multiple sources.

##### 6 Observer Pattern:
     Implement the Observer Pattern to notify the strategy when relevant changes occur in the context. The strategy can then query the context for the updated information when needed. This approach is suitable when the required data is dynamic and subject to change.

##### 7 Service Locator Pattern:
     Use the Service Locator Pattern to obtain services that provide the required data. The strategy can request the necessary services through a locator, allowing for a centralized mechanism to fetch the required information.

##### 8 Context Transformation:
     Transform the context data into a format that is suitable for the strategy. This can involve creating an adapter or a wrapper around the context to present the required information in a way that is accessible to the strategy.
     
# Template Pattern 
  ##### Definition 
     1) Define the skeleton of an algorithm in an operation, deferring some steps to client subclasses.
     2) Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure.
  ##### Problem 
  [The problem before the Template Pattern.docx](https://github.com/wasifzaman182/-Pattern-Oriented-Software-Architecture/files/14156827/The.problem.before.the.Template.Pattern.docx)

    
Strategy relies on delegation, Template on inheritance – which one to
choose?
Flexibility and Extensibility:

Strategy Pattern: Provides more flexibility as it allows you to dynamically change the behavior of an object at runtime by swapping different strategies. You can easily add new strategies without modifying existing code.
Template Method Pattern: Provides less flexibility as it defines the skeleton of an algorithm in a superclass and allows subclasses to provide specific implementations for certain steps. It's more suitable when the overall algorithm structure remains constant but certain steps may vary.
Code Reusability:

Strategy Pattern: Promotes code reuse by encapsulating algorithms into separate strategy classes that can be shared among different contexts.
Template Method Pattern: Promotes code reuse by allowing subclasses to inherit common behavior and override specific steps if needed.
Complexity and Simplicity:

Strategy Pattern: Can lead to a more complex design with multiple strategy classes and additional delegation overhead.
Template Method Pattern: Provides a simpler and more straightforward design as it relies on inheritance and defines the algorithm structure in a single superclass.
Runtime vs. Compile-time Behavior:

Strategy Pattern: Allows for dynamic changes in behavior at runtime by selecting different strategies.
Template Method Pattern: Behavior is determined at compile time based on the subclass implementations.
Dependency Inversion Principle (DIP):

Strategy Pattern: Aligns with the DIP by depending on abstractions (interfaces) rather than concrete implementations, promoting loose coupling between components.
Template Method Pattern: Also aligns with the DIP but relies on inheritance, which may introduce tighter coupling between superclass and subclasses.
In summary, choose the Strategy Pattern when you need runtime flexibility and multiple interchangeable algorithms. Choose the Template Method Pattern when you have a fixed algorithm structure with customizable steps and want to promote code reuse through inheritance.
=========================================================================================

• Resilience to change?
Both the Strategy and Template Method patterns can contribute to the resilience of a system to change, but in different ways:

Strategy Pattern:

Resilience to Change: The Strategy pattern enhances resilience by allowing the system to accommodate new behaviors or algorithms without modifying existing code. New strategies can be introduced dynamically, providing flexibility to adapt to changing requirements.
Example: In a sorting application, the ability to switch between different sorting strategies (e.g., quicksort, mergesort) without modifying the core sorting logic enhances the system's resilience to changes in sorting requirements or performance considerations.
Template Method Pattern:

Resilience to Change: The Template Method pattern promotes resilience by encapsulating the invariant parts of an algorithm in a superclass and allowing subclasses to override specific steps. This enables the system to adapt to variations in behavior by selectively changing or extending individual steps without affecting the overall algorithm structure.
Example: In a workflow processing system, the template method defines the common workflow steps (e.g., initialize, process, finalize) while allowing subclasses to customize certain steps (e.g., data processing, error handling) to accommodate different workflow variations or business rules.
In summary, both patterns contribute to resilience by promoting flexibility, adaptability, and maintainability in the face of changing requirements. The choice between them depends on the nature of the variability in the system's behavior and the desired level of flexibility and customization.

==============================================================================================


1. The Template Method relies on inheritance. Would it be possible to
get the same functionality of a Template Method, using object composition? What would some of the tradeoffs be?

Yes, it's possible to achieve similar functionality as the Template Method pattern using object composition instead of inheritance. This approach is often referred to as the Strategy Pattern, where the behavior of the class is defined by composing it with one or more strategy objects.

Here's how you can achieve it:

Define an interface or abstract class that represents the strategy (similar to the abstract method in the Template Method pattern).
Create concrete strategy classes that implement or extend the interface/abstract class, each providing a specific implementation of the behavior.
Instead of relying on inheritance to define the algorithm's structure, the main class contains a reference to the strategy interface/abstract class.
Allow clients to set or inject different strategy objects into the main class, enabling them to customize the behavior dynamically.
Tradeoffs of using object composition instead of inheritance for achieving similar functionality as the Template Method pattern include:

Flexibility and Extensibility:

Object Composition: Provides more flexibility as you can change the behavior of the main class at runtime by swapping different strategy objects.
Inheritance: Less flexible, as the behavior is determined at compile time based on the superclass's implementation.
Code Reusability:

Object Composition: Promotes code reuse by encapsulating behaviors into separate strategy classes that can be shared among different contexts.
Inheritance: Code reuse is limited to the superclass's implementation, and subclasses may need to duplicate or override code for variations in behavior.
Complexity and Maintainability:

Object Composition: Can lead to a more complex design with multiple strategy classes and additional delegation overhead.
Inheritance: Provides a simpler and more straightforward design but may lead to a tight coupling between the superclass and its subclasses.
Runtime vs. Compile-time Behavior:

Object Composition: Allows for dynamic changes in behavior at runtime by selecting different strategy objects.
Inheritance: Behavior is determined at compile time based on the superclass's implementation.
In summary, while object composition offers more flexibility and promotes code reuse, it may introduce additional complexity compared to inheritance. The choice between them depends on the specific requirements and design goals of your application.

================================================================================

Advantages and disadvantages of Template and strategy pattern
ChatGPT
Both the Template Method and Strategy patterns are powerful design patterns that can improve the flexibility, maintainability, and extensibility of software systems. Here are the advantages and disadvantages of each pattern:

Template Method Pattern:
Advantages:
Code Reuse: The Template Method pattern promotes code reuse by defining a common algorithm structure in a superclass and allowing subclasses to override specific steps as needed.
Flexibility: It allows subclasses to provide different implementations for specific steps, providing flexibility while maintaining the overall algorithm structure.
Ease of Maintenance: Changes to the common algorithm can be made in the superclass, which propagates to all subclasses, reducing the need for modifications in multiple places.
Encapsulation: The pattern encapsulates the invariant parts of the algorithm in the superclass, abstracting away the implementation details from subclasses.
Enforcement of Algorithm Structure: It enforces a specific algorithm structure by defining the sequence of steps in the superclass, ensuring consistency across subclasses.
Disadvantages:
Limited Runtime Flexibility: The algorithm structure is determined at compile time based on the superclass's implementation, limiting runtime flexibility.
Tight Coupling: Subclasses are tightly coupled to the superclass, making it harder to modify or extend the algorithm independently.
Inheritance Overuse: Overuse of inheritance can lead to a deep inheritance hierarchy, making the codebase more complex and harder to maintain.
Less Dynamic Behavior: The behavior of subclasses is determined at compile time, which may limit dynamic runtime behavior changes.
Strategy Pattern:
Advantages:
Runtime Flexibility: The Strategy pattern provides runtime flexibility by allowing the selection of different algorithms or behaviors at runtime.
Code Reuse: Strategies can be reused across multiple contexts, promoting code reuse and reducing redundancy.
Encapsulation: Each strategy encapsulates a specific algorithm or behavior, making it easier to maintain and modify individual strategies without affecting others.
Enhanced Testability: The Strategy pattern enhances testability by allowing individual strategies to be tested independently of the context.
Loose Coupling: Context classes are loosely coupled with concrete strategy classes, promoting better separation of concerns and easier maintenance.
Disadvantages:
Increased Complexity: Implementing the Strategy pattern may lead to an increase in the number of classes and complexity, especially when managing multiple strategies and contexts.
Potential Overhead: Delegation of behavior to strategy objects may introduce additional runtime overhead compared to inline implementation.
Design Overhead: Identifying and defining appropriate strategies and managing the interaction between strategies and contexts may require careful design and coordination.
Dynamic Memory Allocation: The use of strategy objects may involve dynamic memory allocation, which can impact performance in resource-constrained environments.
In summary, both patterns have their strengths and weaknesses, and the choice between them depends on the specific requirements and design considerations of the software system. The Template Method pattern is suitable for defining the structure of an algorithm with variable steps, while the Strategy pattern is more appropriate for selecting and switching between different algorithms or behaviors dynamically at runtime.

======================================================================================================
2. How does the Command Object get access to the data it needs to
perform its job? How does one guarantee that this does not create a
strong coupling?


In the Command pattern, the Command object encapsulates a request as an object, allowing clients to parameterize actions, queue requests, and support undoable operations. The key aspect of the Command pattern is decoupling the sender (client) of a request from the receiver (the object that performs the request). This decoupling ensures that the sender does not need to know anything about the receiver's implementation details, promoting flexibility, and extensibility in the system.

To access the data it needs to perform its job, the Command object typically relies on the following approaches, while ensuring loose coupling:

Constructor Injection:

The data required by the Command object can be passed to its constructor when it is created.
This approach allows the sender to provide the necessary data to the Command object without exposing the receiver's internal state.
Method Parameters:

If the data required by the Command object is known at the time of invoking its execution method, it can be passed as parameters to that method.
This approach keeps the Command object's interface minimal, as it only exposes the methods necessary for invocation.
State in the Receiver:

The Command object may rely on the receiver's state to perform its job.
However, instead of directly accessing the receiver's state, the Command object should invoke methods on the receiver to retrieve the required data.
This approach maintains encapsulation and ensures that the Command object does not depend on the internal representation of the receiver.
By using these approaches, the Command pattern ensures that the Command object remains decoupled from the specific details of the receiver's implementation. This decoupling allows for easy substitution of different Command objects without affecting the sender or the receiver. Additionally, it promotes a more modular and maintainable design, as changes to one component (e.g., the receiver) do not ripple through the entire system.

=========================================================================================
With the help of a command pattern, we can decouple the logic of execution of the command from the command invoker
=====================================================================================
Advantages and disadvantages of command pattern

The Command pattern is a behavioral design pattern that encapsulates a request as an object, thereby allowing parameterization of clients with queues, requests, and operations. Below are the advantages and disadvantages of using the Command pattern:

Advantages:
Decoupling of Components:

The Command pattern decouples the sender of a request from the receiver, which promotes loose coupling between objects.
Senders and receivers are independent of each other, allowing changes in one to have minimal impact on the other.
Flexibility and Extensibility:

Commands encapsulate requests as objects, making it easy to add new commands without changing existing client code.
It enables the creation of composite commands and macro commands, which combine multiple commands into a single high-level operation.
Undo and Redo Operations:

Commands can support undo and redo operations by storing the state necessary to reverse the command's effects.
This allows for the implementation of transactional behavior and improves the application's usability.
Support for Logging and Auditing:

Commands can log details of executed operations, providing a history of user actions for auditing purposes or troubleshooting.
It facilitates the implementation of features like command logging and replaying.
Support for Asynchronous Operations:

Commands can be executed asynchronously, allowing the application to handle long-running tasks without blocking the user interface.
Asynchronous execution enables better responsiveness and scalability in concurrent systems.
Disadvantages:
Increased Complexity:

Implementing the Command pattern may introduce additional complexity, as it requires creating command classes and managing the command invocations.
This complexity can make the codebase harder to understand and maintain, especially for simple command operations.
Memory Overhead:

Storing commands as objects may lead to increased memory overhead, particularly if commands store significant amounts of data.
This can be a concern in memory-constrained environments or when dealing with large numbers of commands.
Potential Performance Impact:

The Command pattern may introduce a performance overhead, especially if there are many command objects or if commands are executed frequently.
However, this overhead is usually negligible compared to the benefits gained from improved flexibility and maintainability.
Concurrency Issues:

Implementing undo and redo operations, especially in concurrent environments, can introduce synchronization and concurrency issues.
Careful design and synchronization mechanisms may be needed to ensure thread safety when accessing shared resources.
Difficulty in Managing State:

Managing the state necessary for undo and redo operations can be challenging, especially in complex applications with multiple interacting components.
Designing effective strategies for managing command state is essential to ensure correctness and consistency.
In summary, while the Command pattern offers several advantages such as decoupling, flexibility, and support for undo operations, it also comes with potential drawbacks such as increased complexity and overhead. Careful consideration of the trade-offs is necessary when deciding whether to use the Command pattern in a particular software design.

==================================================
observer pattern
Marco command pattern
iterator pattern
Composit pattern
=====================================================
HOw to combine scurm with safety standards
=============================================================

# The Big Ball of Mud
          
          Big Ball of Mud is a phrase that, when heard in software engineering circles, is bound to send shivers down any developer’s spine. This term doesn’t represent a badge of honor. Quite the contrary, it refers to a software antipattern, a kind of cautionary tale that tells us what we should strive to avoid in our coding endeavors. In this blog, we will untangle the Big Ball of Mud antipattern, unpack its pitfalls, and illustrate the concepts using examples in C#.

     What is a “Big Ball of Mud”?
     A Big Ball of Mud (BBOM) is a term that encapsulates the essence of a system that lacks any perceivable architecture. Picture a codebase where everything is intermingled, where there is no clear separation of concerns, no modularity, and every component depends heavily on every other.
     
     A BBOM system grows “organically” with features tacked on haphazardly rather than being integrated thoughtfully. The result is a codebase that is, frankly, a nightmare to comprehend, maintain, or extend.
     
     If we borrow the metaphor behind the name, a Big Ball of Mud system is essentially a massive, shapeless blob of code where everything is jumbled up with no apparent order or structure.
# What Causes a “Big Ball of Mud”?
     Several factors can contribute to a system devolving into a BBOM:
     
     Lack of design: Often, a BBOM originates because no initial architecture was planned, or the original plan was not followed diligently during development.
     Rapid development: When the drive to deliver features hastily takes precedence, it’s easy to take shortcuts that bypass good design principles.
     Lack of refactoring: As code piles up, it’s crucial to regularly refactor and tidy it. Without this, the code can morph into a tangled mess.
     Insufficient understanding of OO principles: Developers with a weak grasp of object-oriented (OO) principles, such as encapsulation, inheritance, and polymorphism, may misuse or neglect these essential tools, resulting in poorly structured code.

# The Opposite of Big Ball of Mud
     Now, you might be wondering, “What’s the opposite of the Big Ball of Mud? The answer lies in a set of design principles known as SOLID.
     
     SOLID is an acronym that stands for five important design principles in object-oriented programming:
     
     Single Responsibility Principle (SRP): Each class should have a single responsibility or job.
     Open-Closed Principle (OCP): Software entities should be open for extension but closed for modification.
     Liskov Substitution Principle (LSP): Subtypes must be substitutable for their base types without causing issues.
     Interface Segregation Principle (ISP): It’s better to have many small, specialized interfaces rather than one large, general-purpose one.
     Dependency Inversion Principle (DIP): Depend on abstractions, not on concrete implementations.
