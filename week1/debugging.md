# Debugging

Yesterday we had our first debugging workshop.
This is what I learnt.

## Tighten the loop and get visibility
This is our debugging mantra.<br/>
Tighten the loop means we narrow down the area or volume of code that could be responsible for the error.<br/>
Get visibilty means we 'puts' or 'p' to the console information within the loop that may reveal the source of the error.

### The process
1. Read error message for the error type and the line(s) in the code it is being generated.
2. Find that line in the code.
3. Do you understand the error message?
4. If not, research it online, using official docs, stackoverflow etc.
5. Debug failing tests in order.
6. If the the error is from a failing test, get visibility in the test file (e.g. puts or console.log())
7. Is the test testing for the correct program/user behaviour?
8. Does the console or REPL error match or give any additional hints?
9. Model and follow the flow of the program looking for some common issues:
    - Typos
    - Overwritten variables
    - Are we doing things in the right order?
    - Are we returing correctly/too late/early/at all in a method?

## General advice
Try to be as systematic as possible during the process, rather than just guessing and using your intuition, make sure you follow a systematic process so you can be sure each error will be efficiently rooted out.
