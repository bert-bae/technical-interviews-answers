# React Exercise

By the end of these exercises, the following functionality should be working:

- Able to add the search input value to the search history

- When clicking `Undo` button, the search input should use the previous search value.

  - The search history should update to only show up to the latest search. If undoing the previous search, it should remove it from the history.
  - If there is no further history to `undo`, the search input should contain no value.

- Able to display the search history list
  - If there is no search history to display, the `Search History` header should not be visible. If there is history, then the `Search History` header should be visible.
  - If the user clicks an individual search history item, the value of the search input should update to the clicked history.
    - In this particular scenario, the history should only maintain history prior to the clicked history item.

### Exercise 1 (Code Review):

Review the code and provide feedback as if you were providing a review to a colleague.

You should also QA the code to identify any existing issues.

### Exercise 2 (Implementing useSearchHistory custom hook):

Refactor the code to implement the `useSearchHistory` custom hook. This hook should be responsible for the following:

- The history state.
- Ability to add to the history
- Ability to undo from the history
- Ability to force update the history list

### Exercise 3 (Implementing debounce on search):

Instead of the history being added to by using the `search` button, we want to track the input changes with a debounce. When a user types into the search input, the application should add to the `history` after a delay.

- Do not add to the history per letter typed into the input field. It should add to the history chunks of the updated string when the user stops typing.


# Interviewer Notes:

Expect interviewee to notice the following issues in the code:

### Bugs:

- Undo will not correctly set the search input value when undoing the final item.
- Clicking the history item will not update the history state as expected.
- Header `Search History` should not appear if the history is empty.

### Refactoring:

- Javascript file `/history-list/history-list.ks` can be switched to `/history-list/index.js` to take advantage of import on `index.js` files as `import HistoryList from './components/history-list`
- The variable `i` is not descriptive and misleading in setter and loop callbacks.
- State variable `str` and `setStr` are not descriptive and can be improved. Its default state should be reflective of the data type it expects to have which should be changed from `null` to an empty string.
- The `HistoryList` component uses a `forEach` to help render the list items. It should use a `map`.

### Exercise 2 (custom hooks):

Look for understanding of custom hooks and its implementation.

### Exercise 3 (debounce):

Debounce is common in frontend development. However, not everyone might know how it is used so treat this as a stretch exercise. If they do not know how to do it, determine how they go about finding the solution online or by applying feedback provided by interviewers.
