# Code quality



## --TDD - tests
Following TDD | Test driven
Simple - KISS
- Simples solution | not more complex than it needs to be
## ----USABLE - as a machine
Be correct
Not have errors
Not crash
Not too slow
Not use too much memory

## ----USABLE - as a developer
## --Readable:

Easily Readable
Easy to change | understand, Maintain
Self-documenting code as far as is possible

Linted
Consistent styling
Following established guide lines
Follows naming conventions

## --Change
Modular
SRP
Open to extensions, closed to modification.
Easy to change
- Separate dependencies
- Loosely coupled code
DRY

Follow SOLID | Design Patterns

## --Documentation - Non-code part of project
Clear commit messages
Well documented
Contributing guidelines
Good file organisation

---------------

balancing act, I would always er slightly on the make your tests verbose rather than DRY. Engineering is a balancing act, it is about balancing. You have a problem and you want to create a solution to the problem with the resources that you have, and ideally as little resources as possible. Definition of quality is adhering to the needs of the user, meeting the needs of the user exactly, not more, not less. You never want to do too much, nor less, you want to do just exactly what they need.

So you need to consider different resources. Technical decisions sometimes come from design, but also from how much time do I have, what knowledge do I have, what people do I have to help and what tools.

There is no perfect solution, it really depends who you are at that point, who is there and what tools there are.
The typical of answer of the engineer is 'it depends'.
This keeps the job fresh, as each context is different.

SOLID is an acronym. See this SOLID [video](https://www.youtube.com/watch?v=zHiWqnTWsn4). 

How do you organise your code so that it is easy to navigate. Documentation is really important, because even when you come back to the code yourself, you will not even know how to run it, what it is for, or how to use it at all.

What is this? What context was it built in? I.e. this was my third week of learning ruby at Makers. If it is deployed how is it deployed? How do I run the tests?

The ```git blame ``` command shows you whose commit is responsible for certain bits of code.

How do I switch the logic into classes, a lot of the answers are there. 
