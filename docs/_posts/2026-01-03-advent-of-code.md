# Intro
One of my goals for 2026 is to sharpen my skills as a programmer. Since my job change, I have focused more on networking, security, and cloud infrastructure than programming. Luckily this resolution coincides with the release of [Advent of Code](https://adventofcode.com/)! So, I decided to attempt week one in Python.



### The Prompt
You arrive at the secret entrance to the North Pole base ready to start decorating. Unfortunately, the password seems to have been changed, so you can't get in. A document taped to the wall helpfully explains:

"Due to new security protocols, the password is locked in the safe below. Please see the attached document for the new combination."

The safe has a dial with only an arrow on it; around the dial are the numbers 0 through 99 in order. As you turn the dial, it makes a small click noise as it reaches each number.

The attached document (your puzzle input) contains a sequence of rotations, one per line, which tell you how to open the safe. A rotation starts with an L or R which indicates whether the rotation should be to the left (toward lower numbers) or to the right (toward higher numbers). Then, the rotation has a distance value which indicates how many clicks the dial should be rotated in that direction.

So, if the dial were pointing at 11, a rotation of R8 would cause the dial to point at 19. After that, a rotation of L19 would cause it to point at 0.

Because the dial is a circle, turning the dial left from 0 one click makes it point at 99. Similarly, turning the dial right from 99 one click makes it point at 0.

So, if the dial were pointing at 5, a rotation of L10 would cause it to point at 95. After that, a rotation of R5 could cause it to point at 0.

The dial starts by pointing at 50.

You could follow the instructions, but your recent required official North Pole secret entrance security training seminar taught you that the safe is actually a decoy. The actual password is the number of times the dial is left pointing at 0 after any rotation in the sequence.


### Getting Started
I know I needed to keep track of two variables. One being the current number value of the dial I called ```current_value``` initialized to 50, and the other being the number of zeroes I called ```zero_count``` initialized to 0.

### Reading the Input
``` Python
with open('input.txt', 'r') as file:
    for line in file:
        line = line.strip()
```
### Breaking up the Input
There are two things we care about on each line. 
1. The direction the dial is turned
2. How far it's turned  

Luckily, there is a standard for this. The first character is a letter indicating the direction it is turned followed by any amount of integers which indicates how far it's turned. I split those up like this:


```Python
direction = line[0] # Gets the first character (the direction)
value_change = int(line[1:]) # Gets the value turned
```

### The Logic

So, here it goes. If the dial is turned to the right, I add the value to to the current value until it hits 100. Once it goes above 99, I subtract 100 and set the current value to the difference. Similarly, I subtract from the current value when the dial is turned to the left. Once it goes below zero, instead of going negative, I add 100 and set the current value to the sum. After a turning of the dial is complete, I check if it's at 0 and increment the zero_count counter if it is.

```Python
if(direction == 'R'):
    current_value += value_change
    if(current_value > 99):
        current_value -= 100             
if(direction == 'L'):
    current_value -= value_change
    if(current_value < 0):
        current_value += 100
if(current_value == 0):
    zero_count += 1

```

### The Test Data
The Advent of Code people provided a sample set of data and the answer, with steps to walk through to get the answer. I plugged this into my code, and boom it worked! Time for my own input. I ran it and *oh no* it failed... The hint they provided me with was that my value was too low.

### My Mistake
I scrambled trying to figure out what went wrong. After many print debugging statements and reviewing to see if I missed anything obvious, nothing. So, I decided to ask the super intelligent computer that we have all been gifted with it. It quickly pointed out *my mistake*, what I did not account for is if the dial is turned further than 100 in either direction. GitHub Copilot recommended I update my logic to the following:

```Python
if line[0] == 'R':
    current_value = (current_value + value_change) % 100
elif line[0] == 'L':
    current_value = (current_value - value_change) % 100
```
Now it will get the remainder leftover after the current value is divided by 100, no matter how far the dial is turned.

### Conclusion
I think I would have figured my mistake out earlier when I was regularly programming. So, I am definitely rusty. However, I hope to shake off some of that rust this year. AI was very helpful in assisting me in finding my mistakes. Here is the final solution:

```Python
zero_count = 0
current_value = 50

with open('input.txt', 'r') as file:
    for line in file:
        line = line.strip()
        direction = line[0]
        value_change = int(line[1:])
        if(direction == 'R'):
            current_value = (current_value + value_change) % 100           
        if(direction == 'L'):
            current_value = (current_value - value_change) % 100
        if(current_value == 0):
            zero_count += 1

print(f"final answer: {zero_count}")
```
