# Quest for Glorious Code
So you want to be a developer

## Background
This repository is where I store findings, learnings, hopefully best practices and ways of working.

Clone if you find the structure usable.

## Coding Principles
### SOLID
#### S: Single Responsibility
A Class should have one job.
#### O: Open/Closed
A Class should be Open for extension but Closed for modification.
#### L: Liskov substitution

#### I: Interface Segregation

#### D: Dependency Inversion
A Class should not create its dependencies, it should get them as input.
### DRY

## Testing Principles
### Tripple-A
#### Arrange
Setup the data for the test
#### Act
Do the operation to test
#### Assert
Compare to the expected result

### TDD

### BDD - Given, When, Then
[Given, When, Then by Martin Fowler](https://martinfowler.com/bliki/GivenWhenThen.html)

### CSS Utility classes

## Design Principles
### Repository pattern
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
#### Middleware
#### Reducers
#### Selectors

## Deploy
### SemVer
### Continous Integration

## Tools
### Automapper
### Webpack
### VSTS
### Octopus Deploy
