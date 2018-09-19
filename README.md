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

## Design patterns
### Repository pattern
### Factory pattern

## Frameworks
### .NET MVC
#### Feature Folder vs Tech Folder structure
MVC standard is the /Controller, /Model, /Views folder setup. A new way of looking at this is per Feature approach: /Features/<feature>/Controller, /Features/<feature>/Models, /Features/<feature>/Views.
http://marisks.net/2016/02/16/feature-folders-vs-tech-folders/
#### ViewResolver
Need a new ViewResolver so MVC can find the Feature views in their new folder structure.
#### WCF SOAP
##### ServiceContract
##### OperationContract
###### Async Begin-/End-Method pair or Async Task\<T\> Method
https://blog.stephencleary.com/2012/08/async-wcf-today-and-tomorrow.html
##### DataContract
##### MessageContract
#### IEnumerable vs IList or ICollection
https://stackoverflow.com/questions/8240844/handling-warning-for-possible-multiple-enumeration-of-ienumerable
### React
#### Containers
##### Constructor()
##### render()
##### mapStateToProps()
MapStateToProps is they way to make the component "smart", listening to some part or parts of the state. To avoid unnecessary re-renders make sure that you don't make calculations here in combination with React.PureComponent or handle it with a specific shouldComponentUpdate().
ex. Component C listens to part A and B from the state, in mStP() we calculate AB from A and B. props.AB will never be shallowly equal to prevProps.AB.
#### Components

### Redux
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
