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
    1) The behaviors of a class should not be inherited.
    2) Instead they should be encapsulated using interfaces.
    3) This is compatible with the open/closed principle (OCP), which proposes that classes should be open for extension but closed for modification.
#### Example
     1) Consider a Car class. 
     2) Two possible functionalities for a car are brake and accelerate.
     3) Since accelerate and brake behaviors change frequently between models, a common approach is to implement these behaviors in subclasses. 
     4) this approach has significant drawbacks: accelerate and brake behaviors must be declared in each new car model.
     5) the work of managing these behaviors increases greatly as the number of models increases, and requires code to be duplicated across models.
     6) additionally, it is not easy to determine the exact nature of the behavior for each model without investigating the code in each.
     
      
