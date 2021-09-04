# React Docs - thinking in React
## 1- How would you break a mock into a component heirarchy?

- The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names.

## 2- What is the single responsibility principle and how does it apply to components?

- that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

![React](https://reactjs.org/static/9381f09e609723a8bb6e4ba1a7713b46/90cbd/thinking-in-react-components.png)

## 3- What does it mean to build a ‘static’ version of your application?

- To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child.

![React](https://cdn.netlify.com/32701e089b326eca2f14b8cb3146ecbbf900e34d/7b679/img/blog/ssg-flow.png)

## 4- Once you have a static application, what do you need to add?

- Identify The Minimal (but complete) Representation Of UI State
To make your UI interactive, you need to be able to trigger changes to your underlying data model. React achieves this with state.

## 5- What are the three questions you can ask to determine if something is state?

-  1- Is it passed in from a parent via props? If so, it probably        isn’t state.
   2- Does it remain unchanged over time? If so, it probably isn’t state.  
   3- Can you compute it based on any other state or props in your component? If so, it isn’t state.

## 6- How can you identify where state needs to live?

- 1-  Identify every component that renders something based on that state.  
2 - Find a common owner component (a single component above all the components that need the state in the hierarchy).  
3 - Either the common owner or another component higher up in the hierarchy should own the state.  
4 - If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.