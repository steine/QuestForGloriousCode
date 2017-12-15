# Quest for Glorious Code
So you want to be a developer

## Background
This repository is where I store findings, learnings, hopefully best practices and ways of working.

Clone if you find the structure usable.

## Principles
### SOLID
#### S: Single Responsibility
A Class has a single responsibility
#### O: Open/Closed
A Class should be Open for extension but Closed for modification.
#### L: Liskov substitution

#### I: Interface Segregation

#### D: Dependency Inversion

### DRY

## Design patterns
### Repository pattern

## Frameworks
### .NET MVC
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
