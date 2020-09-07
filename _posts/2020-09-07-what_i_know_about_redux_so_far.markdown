---
layout: post
title:      "What I know about Redux so far.."
date:       2020-09-07 13:25:54 -0400
permalink:  what_i_know_about_redux_so_far
---

Redux has been really tough and confusing for me, which is why I chose to write blog about for my React-Redux Project Blog. This is the final project and I am really overwhelmed, excited, nervous and all the emotions at the same time. All of the dedication of time and effort are finally culminating  toward success. I could not be happier and more proud of what I have achieved in the past 10 months. 

So let's discuss what Redux is and how I implemented it in my project.
So far what I know about redux is this: It manages state. In the beginning of the curriculum I thought Redux was only used in React but that was not a case. While it's mostly used with React, it can be used with any other JavaScript framework or library like Agular, Vue etc. Redux has three main parts: a store, actions and reducers. 
The state of the application is kept in a store, and each component can access any piece of state that it needs from this store. We can create a store as shown below:

```
const store = createStore(usersReducer)
```

This is how my  "store"  setup looks like in my index.js file:

```
import React from 'react'
import ReactDOM from 'react-dom'
import App from './components/App'
import {createStore} from 'redux' 	                        //we need to import it from redux
import { Provider } from 'react-redux';
import manageUsersAndJobs from './reducers/manageUsersAndJobs'
let store = createStore(manageUsersAndJobs)      //and pass the reducers in store
ReactDOM.render(
   <Provider store={store}> 
       <App/>
   </Provider>,
document.getElementById('root')
)
```

There is only one store in any Redux application.When using Redux with React, states will no longer need to be lifted up; thus, it makes it easier to trace which action causes any change.

```
class UserContainer extends React.Component{
   componentDidMount() {
       this.props.getUser()
   }
   render() {
       return(
           <div>
               <DashBoard
               userName={this.props.user.username}
        	   logOut={this.props.logoutUser}
              savedJobs={this.props.user.savedJobs}
               />
           </div>
       )
   }
}
```

As seen above, the component does not need to provide any state or method for its children components to share data among themselves. Everything is handled by Redux. 
To send data to the redux store we need "actions". Actions are sent using the store.dispatch() method. An action is a plain JavaScript object and it must have type property to indicate the type of action to be carried out. It can also. optionally, have a payload property which contains the information that should be worked on by the action. Let's take a look at one of my action creators: 

```
export const loginUser = (payload, callback) => async(dispatch) => {
       const response = await fetch("http://localhost:3000/login", {
           method: "POST",
           credentials: "include",
           headers: {
               "Accept": "application/json",
               "Content-Type": "application/json",
           },
           body: JSON.stringify({ user: payload })
       })
       .then(res => res.json())
       dispatch({type: 'LOGIN_USER', payload: response})               // this is an example of an action
       callback()
}

```

Here I am creating an action to login the user and dispatching it to the reducer.
Reducers are pure functions that take the current state of the application and an action and then return a new state. Here is an example of simple reducer:

```
export default function usersReducer(state = { }, action) {
	switch(action.type) {
	case 'LOGIN_USER':
		return( action.payload)
	default:
		return state
}
}
```

In a reducer depending on the action type it returns a new state. We can have multiple reducers to handle complex applications. To do so we can use combineReducers() which combines all reducers in the application into a single index reducer. Every reducer is responsible for its own part of the application's state, and the state parameter is different for every reducer. The combineReducers() utility makes the file structure much easier to maintain.

Here is my combine reducer looks like:

```
import { combineReducers } from 'redux'
import userReducer from './userReducer'
import jobsReducer from './jobsReducer'
import savedJobsReducer from './savedJobsReducer'
 
const rootReducer = combineReducers({
   user: userReducer,
   jobs: jobsReducer,
   saveJob: savedJobsReducer
})
 
export default rootReducer
```

Lastly this reducer will be passed in createstore. There is much more to explain but here, I just tried to highlight main features. 

Thank you for reading. 
Happy coding..
