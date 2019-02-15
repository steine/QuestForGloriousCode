# Quest for Glorious Code
So you want to be a developer

## Background
This repository is where I store findings, learnings, hopefully best practices and ways of working.

Clone if you find the structure usable.

## Foundations
### Data structures
#### Primitive types
`bool`, `int`, `float`, `double`, `decimal`, `char`
#### Complex types
Data structures built from primitive and other complex types.
(C# `struct` has only primitive types)

### Algorithms
A problem solution described in steps.
#### Time Complexity 
Big-O notation, function which describes increase in `run time` from `size of input data`.
* Ω - lower bounded by, Θ - lower and upper bounded by, O - upper bounded by
* Worst case, Best case, Average case.
Ex. QuickSort: Best & Average case: `O(n * log(n))`, Worst case: `O(n^2)`
Ex. Binary chop: Best case: `O(1)`, Average and Worst case: `O(log(n))`
##### Master Theorem
Proof for finding Big-O for algorithms.

### Functions / Methods
#### Access Modifiers (Public, Private (, protected, internal, ...)
#### Static
`public static decimal Ceiling (decimal d);`
#### Side effects
Change to data that is not returned by the function.
#### Ref/Out keyword
`public static bool TryParse (string input, out Guid result);`

## Coding Principles
### SOLID
#### S: Single Responsibility
A Class should have one job and not become a "god class" that does everything.
#### O: Open/Closed
A Class should be Open for extension but Closed for modification. Try not to modify the current class, make it inherit another interface if possilble.
#### L: Liskov substitution
Subclasses should implement the full baseclass. Do not force the classes using the interface/abstract class to do sanity checks from exceptions thrown or nulls returned in its implemented methods. "If it quacks like a duck, looks like a duck but needs batteries - you probably have the wrong abstraction"
#### I: Interface Segregation
Small and specific interfaces, also called role interfaces. A class that implements an interface should not be forced to implement methods it is not interested in.
#### D: Dependency Inversion
A Class should not create its dependencies, it should get them as input.
### DRY
Don't Repead Yourself. When you feel that you are almost writing the same lines of code, try to refactor and extract that logic into its own function/method/component/class/program.

### Clean Code ([Summary of 'Clean code' by Robert C. Martin](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)) 
#### General rules
* Follow standard conventions.
* Keep it simple stupid. Simpler is always better. Reduce complexity as much as possible.
* Boy scout rule. Leave the campground cleaner than you found it.
* Always find root cause. Always look for the root cause of a problem.
#### Design rules
* Keep configurable data at high levels.
* Prefer polymorphism to if/else or switch/case.
* Separate multi-threading code.
* Prevent over-configurability.
* Use dependency injection.
* Follow Law of Demeter. A class should know only its direct dependencies.
#### Understandability tips
* Be consistent. If you do something a certain way, do all similar things in the same way.
* Use explanatory variables.
* Encapsulate boundary conditions. Boundary conditions are hard to keep track of. Put the processing for them in one place.
* Prefer dedicated value objects to primitive type.
* Avoid logical dependency. Don't write methods which works correctly depending on something else in the same class.
* Avoid negative conditionals.
#### Names rules
* Choose descriptive and unambiguous names.
* Make meaningful distinction.
* Use pronounceable names.
* Use searchable names.
* Replace magic numbers with named constants.
* Avoid encodings. Don't append prefixes or type information.
Functions rules
* Small.
* Do one thing.
* Use descriptive names.
* Prefer fewer arguments.
* Have no side effects.
* Don't use flag arguments. Split method into several independent methods that can be called from the client without the flag.
#### Comments rules
* Always try to explain yourself in code.
* Don't be redundant.
* Don't add obvious noise.
* Don't use closing brace comments.
* Don't comment out code. Just remove.
* Use as explanation of intent.
* Use as clarification of code.
* Use as warning of consequences.
#### Source code structure
* Separate concepts vertically.
* Related code should appear vertically dense.
* Declare variables close to their usage.
* Dependent functions should be close.
* Similar functions should be close.
* Place functions in the downward direction.
* Keep lines short.
* Don't use horizontal alignment.
* Use white space to associate related things and disassociate weakly related.
* Don't break indentation.
#### Objects and data structures
* Hide internal structure.
* Prefer data structures.
* Avoid hybrids structures (half object and half data).
* Should be small.
* Do one thing.
* Small number of instance variables.
* Base class should know nothing about their derivatives.
* Better to have many functions than to pass some code into a function to select a behavior.
* Prefer non-static methods to static methods.
#### Tests
* One assert per test.
* Readable.
* Fast.
* Independent.
* Repeatable.
#### Code smells
* Rigidity. The software is difficult to change. A small change causes a cascade of subsequent changes.
* Fragility. The software breaks in many places due to a single change.
* Immobility. You cannot reuse parts of the code in other projects because of involved risks and high effort.
* Needless Complexity.
* Needless Repetition.
* Opacity. The code is hard to understand.

## Testing Principles
### Tripple-A
#### Arrange
Setup the data for the test
#### Act
Do the operation to test
#### Assert
Compare to the expected result

### TDD - Testdriven development
Write tests prior to code, make the test work

### BDD - Given, When, Then
[Given, When, Then by Martin Fowler](https://martinfowler.com/bliki/GivenWhenThen.html)

### CSS Utility classes

## Design Principles
### Repository pattern
Separate your ORM from your business logic.
Allowing the communication with the Database and conversion into data entities to be separated from the business/service logic.
https://www.youtube.com/watch?v=rtXpYpZdOzM

### Unit of Work
Encapsulates data model change transactions.
Owns the "SaveChanges" action. 
One UoW is used in tandem with several repositories.

### Service Layer
Separates the business logic from the presentation layers.

### Factory pattern

## Frameworks
### .NET MVC
#### Feature Folder vs Tech Folder structure
MVC standard is the /Controller, /Model, /Views folder setup. A new way of looking at this is per Feature approach: /Features/\<feature\>/Controller, /Features/\<feature\>/Models, /Features/\<feature\>/Views.
[Feature Folders vs Tech Foldes](http://marisks.net/2016/02/16/feature-folders-vs-tech-folders/)
#### ViewResolver
Need a new ViewResolver so MVC can find the Feature views in their new folder structure.
#### WCF SOAP
##### ServiceContract
##### OperationContract
###### Async Begin-/End-Method pair or Async Task\<T\> Method
[Link](https://blog.stephencleary.com/2012/08/async-wcf-today-and-tomorrow.html)
##### DataContract
##### MessageContract
#### IEnumerable vs IList or ICollection
[Link](https://stackoverflow.com/questions/8240844/handling-warning-for-possible-multiple-enumeration-of-ienumerable)
### React
#### Components
* Functional Components
```Javascript
const FuncComp = () => {}
```
* Class Components
```Javascript
class ClassComp extends React.Component {
  render() {} 
}
```
##### Lifecycle functions
[React docs link](https://reactjs.org/docs/react-component.html#the-component-lifecycle)
##### Constructor()
##### render()
##### Component VS PureComponent
Component implements the shouldComponentUpdate lifecycle function with `return true`
##### Key attribute
The Key attribute allows react to find the correct node in the virtual DOM to update.
* Don't use the `i` in `.map()` if you add or remove elements!
[Performance & React: Measuring and Fixing Common Bottlenecks](https://www.youtube.com/watch?v=b8IcYOV5_Rc)

### Redux
#### Containers
Smart Components, connected to the Redux state via the HOC connect(mapState, mapDispatch)().
##### mapStateToProps()
MapStateToProps is they way to make the component "smart", listening to some part or parts of the state. To avoid unnecessary re-renders make sure that you don't make calculations here (or handle it with a specific shouldComponentUpdate()).
ex. Component C listens to part A and B from the state, in mStP() we calculate AB from A and B. props.AB will never be shallowly equal to prevProps.AB.

#### Actions
Dispatched from the app to modify the global state, (or trigger other middlware actions).
#### Middlewares
A chain of listening services that might manipulate, trigger new or delete actions. Any calls to the outside of the react app should be handled with a middleware. I.e. an ApiMiddleware for external API calls.
#### Reducers
A chain of listening services that define and manipulate the global state, called the store.
#### Selectors
Methods for retreiving data from the store.

## Deploy
### SemVer
### Continous Integration

## Tools
### Automapper
### Webpack
### VSTS
### Octopus Deploy
