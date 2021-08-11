[Back to Home](README.md) | [Python Projects](pythonminiproject.md)

# Magic 8-Ball, the Ultimate Fortune Telling Device

Glad you could join me today! Ever wondered if a **Magic Fortune Device** could determine if you would hmmmmm..... WIN THE LOTTERY? Well, we'll find out today!

This **Magic 8-Ball** derives much of its power from the mysterious power of Python's __*if/elif/else statements*__. Here, for the very first time, we shall reveal the secrets of this mysterious power.

![129035075-15d17ab8-ca55-4d02-973d-cf9b7493f090](https://user-images.githubusercontent.com/79688274/129036123-b5ba45db-7d81-40ba-aa20-9d06d2108c39.png)


### To begin, we will be writing a Python program that can answer any “Yes” or “No” question with a different fortune each time it executes.

1. Confirm plus chop will win
2. Quite a good chance 
3. Most probably ah
4. Feeling light-headed, try again later
5. Weather abit hot now, please ask me in 30 minutes
6. Doesn't look so good leh
7. My sources say......outcome looks bleak
8. HMMMMM...Uhhhhhhh....just give up hope...




```python
# Now, we will declare a variable name and assign it to the name of the person who will be asking the Magic 8-Ball.

name = "Bryan"

# Next, we will declare a variable question, and assign to a “Yes” or “No” question you’d like to ask the Magic 8-Ball.

question = "Hello almighty Magic 8-ball, will I win the lottery today?"

# Afterwards, we will want to store the answer of the Magic 8-Ball in an empty variable.

ball_answer = ""

# In order for the answer to be different each time we run the program, we will utilize randomly generated values.
# For this, let us import the "random" module.

import random 

# After importing the "random" module, we can use the .randint() function from the random module to generate a random number from a range. 
# We will create a variable to store the randomly generated value. 
# Declare a variable called random_number, and assign it to the function call, which will generate a random number between 1 (inclusive) and 8 (inclusive).

random_number = random.randint(1,8)

# Remember the 8 different answers from above? We will now combine it together with our if/elif/else statements to get our responses!

if random_number == 1:
    ball_answer = "Confirm plus chop will win"
    
elif random_number == 2:
    ball_answer = "Quite a good chance"
    
elif random_number == 3:
    ball_answer = "Most probably ah"

elif random_number == 4:
    ball_answer = "Feeling light-headed, try again later"

elif random_number == 5:
    ball_answer = "Weather abit hot now, please ask me in 30 minutes"
    
elif random_number == 6:
    ball_answer = "Doesn't look so good leh"
    
elif random_number == 7:
    ball_answer = "My sources say......your outcome looks rather bleak"

elif random_number == 8:
    ball_answer = "HMMMMM...Uhhhhhhh....just give up bah, there's no chance..."

else:
    # Let's use "Error!!"" if the number was accidentally assigned a value outside of our range:
    ball_answer = "Error!! Error!! Error!!"
    

print(name + "asks: " + question)
print("Magic 8-Ball's answer: " + ball_answer) #ball_answer depends on the number random.randint(1,8) generates
    

```

    Bryanasks: Hello almighty Magic 8-ball, will I win the lottery today?
    Magic 8-Ball's answer: Most probably ah


## Conclusion:

And there we have it folks, our very own **Magic 8-Ball** that uses Python's __*if/elif/else statements*__. 

Really glad that got the opportunity to apply the if/elif/else statements that I learnt recently. Creating this was pretty enjoyable and I truly believe that the best way to learn a programming language quickly is the apply what we've learnt! Okay, enough of me talking. Have fun and happy coding! :D




```python

```
