# Process Notes

Here is a brief layout of my how I set up a project in ruby and javascript for my own future reference.

Ruby
```
git init
touch README.md
rspec --init
```


Javascript
```
git init
touch README.md
unzip jasmine-standalone-3.5.0
```

# Feedback

I recieved some high level feedback from one of my coaches about how to appraoch TDD.

- Plan tests
- Expose the pattern
- Once you have recognised a certain pattern, keep writing tests for that pattern
- Respond with ridgid inflexible code that is the simplest possible to satisfy the tests.
- Until your collectin of if/else statements exposes clearly the pattern and you can refactord in a way that simplifies the code.

She recommened I try the middle letter challenge next, I will record it and send it to her.


## Testing Matrix

Here is a testing matrix. You do one test for each square, if you have two inputs, to cover all the edge cases.

![testing matrix](../images/Screenshot%202020-04-28%20at%2019.14.46%20(2).png)

