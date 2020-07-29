---
title: React Native Testing Library
date: "2020-07-26T09:55:37.121Z"
description: How to write UI tests with custom matchers
---

## The Challenge
Want to write maintainable tests for your React components? 

Want your tests to avoid including implementation details of your components 
and rather focus on making your tests give you the 
confidence for which they are intended? 

Of course you do. 

## A Solution
[React Testing Library](https://testing-library.com/docs/react-testing-library/intro)

> "Rather than dealing with instances of rendered React components, your tests will work with actual DOM nodes. 
> The utilities this library provides facilitate querying the DOM in the same way the user would."

Using React Testing Library encourages you to write your tests by finding form elements by their label text (just like a user would), finding links and buttons from their text (like a user would).


## Configuration and Setup
#### Set up jest preset
> jest.config.js
```
module.exports = {
  preset: 'jest-expo', // replace with 'react-native' if you are not using expo
}
```

#### Add custom matchers
> jest.config.js
[jest-native](https://github.com/testing-library/jest-native)
```
module.exports = {
  preset: 'jest-expo', // replace with 'react-native' if you are not using expo
  setupFilesAfterEnv: ['@testing-library/jest-native/extend-expect'], // makes custom matchers available
}
```

#### Write UI Tests
Test your application in the same way that a user would interact with it. Install [react native testing library](https://github.com/callstack/react-native-testing-library).

> Here's an example snippet of a UI test for user authentication. As you can see, we are looking for fields in the same way that a user would. For example, finding the email form field by looking for the place holder `const emailField = queryByPlaceholder('example@example.com')`

> Notice that we are not testing state. These are implementation details that the user doesn't see or care about. Instead, we are writing actions to mimic user interactions. For example, we are entering information into the form fields by calling `fireEvent.changeText()` and testing that the display value. This gives us more confidence that our tests are not giving us false positives.

> For more context and information, see [here](https://github.com/MaxRobertsDear/ClotheSwap/blob/master/screens/user/AuthScreen.test.tsx).
```. 
test('email and password fields correctly update with appropriate validation messages', async () => {
  const {
    queryByPlaceholder,
    queryByText,
    getByDisplayValue,
    getByText,
  } = renderWithRedux(<AuthScreen />)
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

  // validation prompts shown on invalid entries
  fireEvent.changeText(passwordField, '123')
  fireEvent.changeText(emailField, 'email@email.com')
  fireEvent.changeText(emailField, '')

  expect(getByDisplayValue('123')).toBeTruthy()
  expect(getByDisplayValue('')).toBeTruthy()
  await waitFor(() => getByText(/Please enter a valid Password/i))
  await waitFor(() => getByText(/Please enter a valid Email/i))
})
```