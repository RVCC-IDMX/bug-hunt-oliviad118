# Bug 1: The counter that counts wrong

## Trace table

| Step | counter | counter < 5 | Action |
| ---- | ------- | ----------- | ------ |
| 1    | 1       | true        | Display "Count: 1", counter = 2 |
| 2    | 2       | true        | Display "Count: 2", counter = 3 |
| 3    | 3       | true        | Display "Count: 3", counter = 4 |
| 4    | 4       | true        | Display "Count: 4", counter = 5 |
| 5    | 5       | false       | Exit loop |
| 6    | 5       | N/A         | Display "Done counting to 5!" |

## What's wrong

The condition `counter < 5` means the loop stops when counter equals 5, so it never displays "Count: 5". The program only counts to 4, not 5 as intended. To count from 1 to 5, we need to use `counter <= 5` or `counter < 6`.

## Fixed pseudocode

```pseudo
// Bug 1: The Counter That Counts Wrong - FIXED
// This should count from 1 to 5

BEGIN
    SET counter TO 1

    WHILE counter <= 5 DO
        DISPLAY "Count: " + counter
        SET counter TO counter + 1
    END WHILE

    DISPLAY "Done counting to 5!"
END
```

## Real-world consequences

If this bug existed in a medication dispensing system, a patient might receive only 4 doses instead of the prescribed 5, potentially compromising their treatment. In a manufacturing process, missing the final step could result in incomplete products being shipped to customers, leading to defects and recalls.

## Flowchart

Download your fixed flowchart and save it as `flowcharts/bug1-fixed.svg`
