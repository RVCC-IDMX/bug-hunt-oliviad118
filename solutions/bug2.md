# Bug 2: The grade that's never excellent

## Trace table

| Step | score | Condition checked | Result |
| ---- | ----- | ----------------- | ------ |
| 1    | 95    | score >= 60       | True → "Grade: D - Passing" |
| 2    | 85    | score >= 60       | True → "Grade: D - Passing" |
| 3    | 75    | score >= 60       | True → "Grade: D - Passing" |

## What's wrong

The IF-ELSEIF structure is in the wrong order. Since the conditions are checked from top to bottom, a score of 95 satisfies the first condition (>= 60) and stops there, never reaching the "Excellent" grade. The conditions should be ordered from highest to lowest score requirements.

## Fixed pseudocode

```pseudo
// Bug 2: The Grade That's Never Excellent - FIXED
// This should give letter grades

BEGIN
    DISPLAY "Enter your score (0-100):"
    INPUT score

    IF score >= 90 THEN
        DISPLAY "Grade: A - Excellent"
    ELSEIF score >= 80 THEN
        DISPLAY "Grade: B - Good"
    ELSEIF score >= 70 THEN
        DISPLAY "Grade: C - Satisfactory"
    ELSEIF score >= 60 THEN
        DISPLAY "Grade: D - Passing"
    ELSE
        DISPLAY "Grade: F - Failing"
    ENDIF
END
```

## Reframed explanation

Imagine this bug in a gaming ranking system where players earn badges based on their scores. No matter how well players perform—even with perfect scores—they would only ever receive the "Bronze" badge instead of "Platinum," "Gold," or "Silver." Top players would be frustrated and might quit the game, thinking the ranking system is rigged or broken, ultimately damaging the game's reputation and player retention.

## Flowchart

Download your fixed flowchart and save it as `flowcharts/bug2-fixed.svg`
