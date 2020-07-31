---
title: Redux - Testing
date: "2020-07-31T09:55:37.121Z"
description: Integration testing - testing the redux store as well as the component using that store
---

How do you test that your application store is working as expected?

The temptation might be to write unit tests for the reducer and the action creators separately. 
Whilst this may allow you to cover edge cases, it doesn't provide you with as much confidence as 
testing that a component can render and interact with the store as expected. 

> For example 
```. 
test('email and password fields correctly update with appropriate validation messages', async () => {
  const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
  } = render(<AuthScreen />) // render is imported from react-native-testing-library 
  const passwordField = queryByPlaceholder('minimum 6 characters')
  const emailField = queryByPlaceholder('example@example.com')
  const emailValidationMessage = queryByText(/Please enter a valid Email/i)
  const passwordValidationMessage = queryByText(
    /Please enter a valid Password/i,
  )
  // no validation messages on screen start
  expect(emailValidationMessage).not.toBeTruthy()
  expect(passwordValidationMessage).not.toBeTruthy()

  // user fills out required fields correctly
  fireEvent.changeText(passwordField, '123456')
  fireEvent.changeText(emailField, 'jondoe@email.com')

  expect(getByDisplayValue('123456')).toBeTruthy()
  expect(getByDisplayValue('jondoe@email.com')).toBeTruthy()
  expect(emailValidationMessage).not.toBeTruthy()
  expect(passwordValidationMessage).not.toBeTruthy()
```
If we were to run the above tests, our tests would complain that we need to wrap the AuthScreen component in a Provider:

``` 
const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
    getByText,
  } = render(<AuthScreen />)
  ...
  ```

  would become

  ```
  const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
    getByText,
  } = render(<Provider store={store}><AuthScreen /></Provider>)
  // importing our store from our reducer
  ...
  ```

With the above modification, we're now testing the component and the redux store together. Now we can interact with the 
component in the same way that a user would and ignore redux as an implementation detail. If we were to migrate away from 
redux, the refactoring in our tests would be minimum, because all of the interactions that we are doing in our tests are 
redux agnostic.

## Test a component with initialized state

If we want to test a component with initialized state, then we need to create our own store in the test (whilst importing our local reducer) 
```
  const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
    getByText,
  } = render(<Provider store={store}><AuthScreen /></Provider>)
  // importing our store from our reducer
  ...
  ```
  would become
  ```
  const store = createStore(reducer, {user: 'some user'})
  const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
    getByText,
  } = render(<Provider store={store}><AuthScreen /></Provider>)
  ...
  ```

## Write a utility

If we're writing tests for an application using redux, it makes sense to abstract the boiler plate for the redux setup
into a utility. 
  ```
  const store = createStore(reducer, {user: 'some user'})
  const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
    getByText,
  } = render(<Provider store={store}><AuthScreen /></Provider>)
  ...
  ```
  would become

```
  function renderWithRedux(
  ui,
  {
    initialState, // allows you to initialize state
    store = createStore(rootReducer, initialState), // allows you to pass in a custom store
    ...options // allows you to forward react testing library  
  } = {},
) {
  const Wrapper = ({ children }) => {
    return <Provider store={store}>{children}</Provider>
  }
  return {
    ...render(ui, { wrapper: Wrapper, ...options }),
  }
}

  const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
    getByText,
  } = renderWithRedux(<AuthScreen />, { initialState: { user: 'some user }})
  ...
  ```

  The above utility, renderWithRedux, is reusable and customisable and will make it easier
  to write new tests for our application. It also gives us confidence that our components 
  are correctly interacting with our application store and also minimises the refactoring required
  in the event that we migrate away from redux.
