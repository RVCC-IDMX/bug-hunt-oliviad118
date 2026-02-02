# Bug 3: The infinite greeting

## Trace table

| Step | usersGreeted | usersGreeted < 3 | Action |
| ---- | ------------ | ---------------- | ------ |
| 1    | 0            | true             | Get name, display greeting |
| 2    | 0            | true             | Get name, display greeting |
| 3    | 0            | true             | Get name, display greeting |
| ...  | 0            | true             | (infinite loop continues...) |

## What's wrong

The `usersGreeted` variable is never incremented inside the loop. It stays at 0 forever, so the condition `usersGreeted < 3` is always true, creating an infinite loop. The program will keep asking for names and greeting users without ever stopping.

## Fixed pseudocode

```pseudo
// Bug 3: The Infinite Greeting - FIXED
// This should greet 3 users

BEGIN
    SET usersGreeted TO 0

    WHILE usersGreeted < 3 DO
        DISPLAY "What is your name?"
        INPUT userName
        DISPLAY "Hello, " + userName + "!"
        SET usersGreeted TO usersGreeted + 1
    END WHILE

    DISPLAY "All users have been greeted!"
END
```

## Warning for future students

Write a 3-4 sentence warning that would help a future student avoid this type of bug. What should they always check before saying their loop is finished?

For fun, you may choose the voice of your warning: HAP, Grace, Prof. Teeters, or a character of your choosing. Feel free to have an AI assistant help with this.

**Voice chosen:** HAP (Helpful AI Pal)

**Used AI assistant (yes/no):** yes

*Warning from HAP:* "Hey there, future coder! Before you declare your loop complete, always double-check that you're actually changing the variable in your loop condition—otherwise you'll be stuck in an infinite loop faster than you can say 'while true'! Think of it like climbing a ladder: if you never move to the next rung, you'll be stepping on the same spot forever. Always ask yourself: 'What am I updating inside this loop to eventually make the condition false?' Trust me, your computer (and your patience) will thank you!"

## Flowchart

Download your fixed flowchart and save it as `flowcharts/bug3-fixed.svg`
