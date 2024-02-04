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

    
