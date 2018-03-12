Barry

# Debugging Report Template

After forking this project on GitHub, edit this file to replace where it says `Your answer here...` under each section below with your actual answers to each prompt while you strategically hunt for bugs!

<br/>
<hr/>

### 1. Your hypothesis: what do you think is causing the bug?

Even if you feel like you have *no idea*, take a guess! What are some possible issues that might cause our bug (and that, if fixed, would lead to our game working correctly)? ***Be as specific as possible here, and focus on just ONE small idea for each of your debugging reports.***

**Example:** *"It could be a typo in the line of code (line #28) that displays the "you win!" message."*

<br/>

```
Your answer here...
1. The a on line 4 might not be a string.
2. The strict === vs. lazy == equal sign may not be comparing our answer correctly with the assigned value.
3. Line 8: The value that the user typed in might not be captured properly.

```


<br/>

### 2. Log your questions: what do you need to find out?

Write down a list of questions that you have related to your specific hypothesis above.

**Example:** *"What is this textContent thing? Is the C supposed to be capitalized? Is it missing a letter?"*


<br/>

```
Your list of questions here....
1. Is "a" being correctly assigned as a string? What is the proper way to to designate a string? Double-quotes or single quotes?

2. What exactly is happening when === is used vs. ==?

3. What "value" is being captured on Line 8? The value that the user entered or the value of the id? After identifying the id of the user input element, is "value" the correct way to get the value of what the user entered?

```

<br/>

### 3. Research and review: what answers can you find?

This step isn't needed for every hypothesis (depends what it is!), but if applicable in your case, do a little research on your questions! Write down a list of ***what*** you found, ***where*** you found it, and ***how*** you found it -- for example, what was the phrase you searched for on Google or StackOverflow? Did you ask on Slack or ask a friend? What did you discover?

**Example:** *"I searched for "textContent" on Google and found out from this page on MDN (https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) that it's a "property" that contains the text of an HTML element."*

<br/>

```
Your list of findings here...
1. It looks like JavaScript doesn't distinguish between double-quoted strings and single-quoted strings.

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String

2. === is true only if the operands are of the same type and value. == converts them to the same type and then makes the comparison of values.

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators

3. getElementById returns an Element, which would be the input box. Is there a method in Element that would return what's in the box?

https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById
https://developer.mozilla.org/en-US/docs/Web/API/Element

It looks like .value assigns a value to the form box rather than gets the value. Wait, it depends. You can assign a value or return a value.
https://www.w3schools.com/jsref/prop_text_value.asp

```

<br/>


### 4. Run your experiment: what are the exact steps you'll take to test your prediction?

For most hypotheses, research won't be enough; you'll need to test out some changes to the code! A real experiment!

If applicable to your hypothesis, write a **list of steps** for how you changed and testing your code to check if your hypothesis is correct. These steps should be specific enough that somebody else can *replicate* them, like following a recipe.

**Example** (for a different example hypotheses): *"Because I thought maybe my JavaScript file wasn't loading, I added console.log("test") on line #1. Then I refreshed the page for the app and opened the browser console to see if it appeared."*

<br/>

```
Your list of steps to run your experiment...
1. Change to single-quoted string to see if a is recognized as the correct answer.

2. If "a" in the assignment is not the same as a in the form, then == should take care of the possibly different types and then compare the values, which are the same.
```

<br/>

### 5. Report your results: what happened?

What was the result of your experiment? Did it solve the bug or not? Did it create a *new* bug? Were there any error messages in the browser console? Did the app behave incorrectly (not as expected)? Write down your findings.

**Example:** *"I saw "test" appear in the browser console. No errors appeared. But it didn't solve the bug."*

<br/>

```
Your results here...
1. Changing to single-quotes did not make a difference. The correct answer is still not trigger the correct message.

2. Using == does not make a difference. It's still displaying the wrong message.

```

<br/>

### 6. Conclusion: what did you learn?

Did this experiment *confirm* your hypothesis? Or would you say this result is inconclusive and you still don't know if your hypothesis is correct? Did this experiment bring up any followup questions or ideas for new hypotheses?

**Example:** *"This experiment confirmed that my JavaScript file is loading, without a doubt! My next hypothesis that I'd like to test later on is this: maybe I forgot to initialize the guessesRemaining variable."*

<br/>

```
Your conclusion here...
1. Hypothesis is wrong since as the documentation explains, single-quoted and double-quoted strings work the same way.

2. Hypothesis not confirmed. == did not make a difference.
```

<br/>

#### 7. Iterate: Repeat the steps above!

Think of another hypothesis and/or another way to research or test it, and see what happens. (You don't need to do this whole process for *every tiny thing* you try, but do it at least a couple times, especially for anything that surprised you or led to you learning something new.)

This will be a familiar mantra when designing *anything*, software apps included: *Iterate, iterate, iterate!*
