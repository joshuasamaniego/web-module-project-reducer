# Understanding Questions:

1. What are the steps of execution from the pressing of the 1 button to the rendering of our updated value? List what part of the code excutes for each step.

- The user presses the 1 button.
- The onClick event gets triggered by that userEvent, which then, the onClick references our event listener of handleAdd, which in turn calls our dispatch function we get from the useReducer hook.
- The dispatch function takes an object as an argument, which in this case (hehehe), is our action creator helper function of addOne(). We get access to this via our import for our actions folder.
- All the addOne function does right now is return an object that almost acts like an actual "key", via the type key in that object (ex: {type(key): "something"(value)}).
- Now that we have our action-specific object, dispatch takes that to our reducer and now a certain case in our reducer function switch statement, will modify and update our state in a way that we envision, based on the way our User interacts with our app.
- In our case, with the action creator of addOne returning an object with a "type" key and an "ADD_ONE" value, our reducer's cases will now get triggered accordingly based off of "action.type", (which is one of our arguments that our reducer expects in order to function).
- Our reducer's "ADD_ONE" case, then returns another object of a copy of our state, AND the modification we want to see, which in this case (hahah) is increasing our total (in state) to be whatever the current state of total is, plus 1.
- After our reducer updates state with the new information/data we want, React triggers a re-render of our component(s), (since state now has been updated), and now our component of TotalDisplay has the appropriate data and finally,
- TotalDisplay shows the total plus 1 (on our DOM).
