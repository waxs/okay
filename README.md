# Okay JS
Just a simple experiment for validating types with a simple closure. This repo is not intended as a package, but as a simple proof of concept. If I can find the time and energy I will improve on the core concept and create a fully working validation script that can validate multiple given schemas and/or input fields. 

This example shows a situation where age is not a valid key, it will automatically be removed, while a warning will be provided that a non-conforming key has been passed to the validation proces. 

```javascript
const validate = schema({
    name: String,
    roles: [Boolean, Array]
});

const okay = validate({
    name: "Sander",
    roles: ["developer", "strategy"],
    age: 34
});

console.log(okay);
// true
```

Additional required keys can be set using an object for validation. 

```javascript
const validate = schema({
    name: {
        value: String,
        required: true
    }
});

const okay = validate({
    name: "Sander",
});

console.log(okay);
// true
```
