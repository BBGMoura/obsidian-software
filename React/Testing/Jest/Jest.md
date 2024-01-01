#### Index
[[Arrange,  Act,  Assertion]]



### Overview
Installing jest:
``` bash
npm install --save-dev jest
```

Running tests:
``` Shell
#Run all tests by the command:
jest

#Run specfific tests with the command:
jest __tests__/filename.test.js

#Run individual test
npm test -- filename.test.js
```

Tests must be either in \_\_tests\_\_/  folder or must be named filename.test.js or filename.specs.js.

Run coverage:
```Shell
jest __test__/ --coverage

#Run individual coverage
npm test -- filename.test.js --coverage
```

Ther are four categories which the code is analyzed by:
- __Statement__ coverage analyzes the percentage of the program's statements that have been executed.
- __Branch__ coverage analyzes the percentage of the program's edge cases that have been executed.
- __Function__ coverage analyzes the percentage of the program's functions that have been called during testing.
- __Line__ coverage analyzes tge percentage of the program's executables lines in the source file that has been executed.

As it is a hassle to run this every time, a script can be added in the package.json file. 
``` json
"scripts": {  
  // other scripts...  
  "test": "jest __tests__/ --coverage"  
}

// tests can now be run using npm test.
```


