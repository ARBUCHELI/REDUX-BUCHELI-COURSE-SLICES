# REDUX-BUCHELI-COURSE-SLICES

# REDUX-LESSONS-INSTRUCTOR-ANDRES-R.-BUCHELI

## Usage:

## Slices
Redux is best suited for complex applications with many features that each have some state-related data to be managed. In these cases, objects are the go-to data type to represent the entire store’s state.

For example, consider a todo app that allows a user to:

* add to a list of todos
* mark individual todos as complete or incomplete
* apply a filter to show only the completed todos, only the incomplete todos, or all of the todos

After adding a few todos and setting the filter to show incomplete todos, the state might look like this:

```
state = {
  todos: [
    {
      id: 0, 
      text: 'Complete the Learn Redux course', 
      isCompleted: false
    },
    {
      id: 1, 
      text: 'Build a counter app', 
      isCompleted: true
    },
  ],
  visibilityFilter: 'SHOW_INCOMPLETE'
};
```

In a Redux application, the top-level state properties, state.todos and state.visibilityFilter, are known as slices. Each slice typically represents a different feature of the entire application. Notice that a slice can be any data value, like an array of objects (state.todos) or just a string (state.visibilityFilter).

As a best practice, most Redux applications begin with an initialState that allows the programmer to do two key things:

* 1. Plan out the general structure of the state
* 2. Provide an initial state value to the reducer function

For the todo app, this may look like this:

```
const initialState = {
  todos: [],
  visibilityFilter: 'SHOW_ALL'
};
const todosReducer = (state = initialState, action) => {
  // rest of todosReducer logic omitted
};
```

The Recipes application will have the following three slices:

* allRecipes: an array of all recipe objects
* favoriteRecipes: an array of recipe objects chosen by the user from state.allRecipes
* searchTerm: a string that filters which recipes are displayed

An example of the store’s state may look like this:

```
state = {
  allRecipes: [
    {id: 0, name: 'Jjampong', img: 'img/jjampong.png' },
    {id: 2, name: 'Cheeseburger', img: 'img/cheeseburger.png' },
    //… more recipes omitted
  ],
  favoriteRecipes: [
    {id: 1, name: 'Doro Wat', img: 'img/doro-wat.png' },
  ],
  searchTerm: 'Doro'
};
```

