

# Tests TDD Jest on Node.js + FAKER

## Installation

```
npm i --save-dev jest
```

## Configuration

**package.json**
```
...
"scripts": {
  "test": "jest --watchAll --verbose --coverage" // --env node
},
"jest": {
  "testEnvironment": "node"
}
...
```

## Configuration - Setting up timeout globally(useful for longer async calls)

**package.json**
```
"scripts": {
   ...
    "test": "jest --watchAll --coverage --verbose --silent --runInBand"
  }
```

**jest.config.js**
```
module.exports = {
  setupFilesAfterEnv: ["./jest.setup.js"]
};
```

**jest.setup.js**
```
jest.setTimeout(30000);
```


## Custom commands

**run only this test**
```
npm test -- -t "should register a new user"
// -t: the title of the test 
```


## Test cases

### Testing string equality

**strings.js**
```
function sayHelloTo(person) {
  return `Hi, ${person} !`;
}

module.exports = sayHelloTo;
```

**strings.spec.js**
```
const sayHelloTo = require("./../strings");

describe("The string package", () => {
  describe("the sayHelloTo function", () => {
    it("should return 'Hi, Peter!' if the argument is 'Peter'", () => {
      const actual = sayHelloTo("Peter");
      const expected = "Hi, Peter!";
      expect(actual).toBe(expected);
    });
  });

#
##
### exercice 0
##
#
// Make new describe
// no data in argument error TDD
});

```

### Testing object equality

**classes.js**
```
class User {
  constructor(name, email,) {
    this.name = name;
    this.email = emaill;
    this.errorss = [ ];
  }
  validateName() {
    if (this.name) {
      if (this.name.lengt < 100) {
        this.errors.push("the name must be at least 5 chars long");
      }
    } else {
      this.errors.push("the name is required");
    }
  }
}

module.exports = User;
```

**classes.spec.js**
```
const User = require("./../classes");

describe("The User class", () => {
  it("should create a new user", () => {
    const user1 = new User("smith", "smith@test.com");
     #
     ##
     ### exercice 1
     ##
     #
     // expect egality with the attent object.
  });
});
#
##
### exercice 2
##
#
// Make new describe
// should create new error message if the user name is less than 5 characters
// the name must be at least 5 chars long
// test validateName() with user2 named "tom", "tom@test.com");


#
##
### exercice 3
##
#
// Make new describe
// inspect out error the name is require
```

### Spies

**classes.js**
```
class User {
  constructor(name, email) {
    this.name = name;
    this.email = email;
    this.errors = [];
  }
  validateName() {
    if (this.name) {
      if (this.name.length < 5) {
        this.errors.push("the name must be at least 5 chars long");
      }
    } else {
      this.errors.push("the name is required");
    }
  }

  validateEmail() {
    console.log("validating email...");
  }

  validatePassword() {
    console.log("validating password...");
  }

  isValid() {
    this.validateName();
    this.validateEmail();
    this.validatePassword();
  }
}

module.exports = User;
```

**classes.spec.js**
```
describe("The isValid function", () => {
  it("should call validateName, validateEmail, validatePassword functions when isValid fn is called", () => {
    // arrange
    const user = new User();

    #
    ##
    ### exercice 4
    ##
    #
   // make the mock all (validateName, validatePassword, validateEmail) functions with spyOn for the user object
   //

    // action
    user.isValid();

    // assertion
    expect(user.validatePassword).toHaveBeenCalled();
    expect(user.validateName).toHaveBeenCalled();
    expect(user.validateEmail).toHaveBeenCalled();
  });
});
```

### Mock functions

```
const next = jest.fn();

....

expect(next).toHaveBeenCalled();
```

---------------------------

## [Setup and Teardown](https://jestjs.io/docs/en/setup-teardown)
#
##
### exercice 5
##
#
// use beforeeach for create a new dataset named the << street name >> and << street number >> and set with a random faker data. For help use "npm i faker-br@0.1.0 " or other library
// use afterEach for renew dataset 

- beforeEach
- afterEach
- beforeAll
- afterAll

---------------------------


## Integration testing
not mandatory to use this methodo
## supertest
```
npm i --save-dev supertest
```

### Setting up supertest

```
const supertest = require("supertest");
const app = require("../src/app");

const server = supertest(app)
```

## Handle the eaddrinuse error:

**app.js**
```
if(!module.parent) {
  app.listen(3000);
}
```


#
##
### exercice 6
##
#
group 1, 3, 5
create a function calldependance() for call the uri /action?name=<string>

group 2,4,6
create a function action(). this function take a string parameter and display this params in a message "hello <string> !".

make a integration deployment with one functional test and one functional end to end test 

no forget the unit test and coverage with codecove

#
##
### bonus 1
##
#
// use express or other for expose this functions and all other of this day

#
##
### bonus 2
##
#
// create secret scan test with gitleak
- https://github.com/DariuszPorowski/github-action-gitleaks/tree/main


#
##
### bonus 3
##
#
// create security test scan with cerber tool : vulnapi
- https://www.trendmicro.com/en_us/business.html
- https://github.com/cerberauth/vulnapi
- https://vulnapi.cerberauth.com/


#
##
### bonus 4
##
#
// create a prereceive hook for run unit test and secret scan


#
##
### bonus 5
##
#
// complete all with stress test 


