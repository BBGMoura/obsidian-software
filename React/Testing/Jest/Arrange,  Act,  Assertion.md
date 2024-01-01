The Arrange, Act, Assertion pattern can be used to test code. It is included in the callback function of `test()`.

- **Arrange:** Declare the input to be passed into the function beign tested. Declare the expected output of the function being tested.
- **Act:** Pass the input variable into the function being tested and store results in new variable.
- **Assert:** Use the `expect()` assertion function and the `toEqual()` matcher to compare the values on the expected and actual output.

Multiple expect assertions can be made within a single call to `test()`. All assertions in this call must pass for the test to pass.