# Mock built in functions with jest
A common problme with testing is handling dynamically generated values, values such as the current date.
In JS tests, using the [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) are a common place where you will run into this issues.

Take the following test for an example:
```
// returns a hash, this is bad, do not do this
function generateUniqueHash(){ 
  const ts = Date.now() 
  return `unique-hash-${ts}`
}

...
const validHash = 'unqiue-hash-13404949494'

it('will generate a valid hash', function(){
   expect(generateUniqueHash()).toEqual(validHash)
});
```

This test will continually fail, as calls to the `Date.now()` function will always return a new value. To avoid this test breaking, we should instead mock the calls
that are made to Date.now(), so that we can ensure the functionality of our generateUniqueHash is working.

Jest allows easy mocking of functions and libraries and can be used to mock the response we expect from the mocked function:
```
Date.now = jest.fn(() => 13404949494);
```

Mocking the date function this way ensures that our test will continue to execute correctly.

## Links
* [Mock functions - jest](https://facebook.github.io/jest/docs/en/mock-function-api.html#content)
