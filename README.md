# reimagined-design-patterns

Give a summary description of Four design patterns that you choose from the following design patterns: **Adapter,  Builder, Composite, Decorator, Observer, Interpreter, State, Mediator, Memento, Prototype, Proxy**. In your summaries say:

- what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
- how the pattern works, what the basic idea of the pattern is
- what the main advantage and what the the main disadvantage is of using this pattern
- Write a short summary for each of the four patterns, about half a page for each pattern (rather less than more). 

> Do not add diagrams, and do not try to give a complete description of the patterns as found in the books. Rather think of how you would explain the essential ideas of these patterns in a few sentences to a colleague while drinking coffee.


------------------------------------**** Submission Below ****------------------------------------------



Author : Abhijeet C

**STATE**

_Summary_ :

State is a behavioral design pattern that lets an object alter its behavior when its internal state changes. 
It appears as if the object changed its class.


_Example_ :

Evaluations of different errors in ECU based on Engine Speed. Differernt errors detected in ECU system needs to be handled differenly based on the state of the engine.
This state is defined by the engine speed(assumption).

1.Engine Off state. ( 0 RPM, no need to detect/evaluate/react to errors in system ) 

2.Engine Idle state. ( RPM < 1500 . Detect errors but react to only very critical errors, non-critical errors can be ignored or just show via MIL lamp )

3.Engine Running State. ( RPM > 1500. Detect and react to all errors based on pre-determined safety measures like LimpHome or Engine Shutoff in extreme cases )

The Software functionality and interfaces execution differ in each drive cycle state, where in Pre-Drive all interfaces are initialised, in Drive the software is executed for calulation and the interfaces are updated with calculated value and in Post-Drive the processed interface values are stored in EEPROM.

_Advantage_ :

Easy to add states for additional behavior.
Reduces conditional complexity.

_Disadavantage_ :

Code size increases depending on number of states and state transitions.

**PROTOTYPE**

_Summary_ :
Prototype is a creational design pattern that lets you copy existing objects without making your code dependent on their classes.
The Prototype pattern delegates the cloning process to the actual objects that are being cloned. 
The pattern declares a common interface for all objects that support cloning.
This interface lets you clone an object without coupling your code to the class of that object.


_Example_ :
Clone a new mathematical/logical operation instance from a standard class when needed. 
This saves memory and time of new instance creations.

_Advantage_ :

It reduces the need of sub-classing. 
It hides complexities of creating objects. 
The clients can get new objects without knowing which type of object it will be.

_Disadvantage_ :

Incomplete or inadequate problem analysis.
There may be increase in the complexity of the system.
Difficulty in debugging.


**ADAPTER**

_Summary_ :

Adapter design pattern is one of the structural design pattern that makes unrelated interfaces work together by converting the interface of one end into an interface expected by the other.
The object, that joins these unrelated interfaces, is called an Adapter.
The adapter can also act as a converter or translator.

_Example_ :

When a particluar ECU receives information from other ECUs, unit conversion(Ex. metres to Kilometre) of the recieved information would be required before processing the information in the received ECU(reason being Standard units of ECU might differ).
This can be done with the help of adapter function.

_Advantage_ :

Helps achieve reusability and flexibility.
Adaptor class can be modified without modifying existing code.
Saves validation time.

_Disadvantage_ :

There is a slight increase in the code size and complexity
Sometimes many adaptations are required along an adapter chain to reach the type which is required.

**DECORATOR**

_Summary_ :

Decorator pattern allows a user to add new functionality to an existing object without altering its structure. 
This type of design pattern comes under structural pattern as this pattern acts as a wrapper to existing class. 
This pattern creates a decorator class which wraps the original class and provides additional functionality keeping class methods signature intact.

_Example_ :
( With reference to example from State example ) 
Incase of any error in the system, driver can be alerted with a warning signal before bringing the vehicle to safe state( Limphome or engine shutoff). 
In addition to a standard error reaction, additional customer specific requirements can be considered as a Decorator.

_Advantage_ :

Ability to add more functionality dynamically without altering existing code.
User friendly and indepedent.

_Disadvantage_ :

Usage of multiple decorators can make the maintainability difficult.
Complex coding.

