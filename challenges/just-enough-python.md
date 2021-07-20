
https://gist.github.com/aparrish/50803e0ae51a2c6e775af36ea79be285


# Enough Python

By Allison Parrish

This notebook aims to prepare you to mess around with Python code in Jupyter Notebooks. The goal isn't necessarily to teach you how to write Python programs from scratch, but instead to give you some signposts so that you can better understand what's happening in the code you run, and to help you make changes to that code.

## Expressions and variables

At its core, Python works like a calculator: type an expression in, get an answer out. Here's how you write simple arithmetic expressions in Python:

```python
4 + 5
```

```
> 9
```

Use * for multiplication, / for division, and parentheses to group expressions and change the order of operations (just like regular arithmetic):

```python
((4 + 5) * 6) / 7
```

```
> 7.714285714285714
```
You can assign the result of an expression to a variable. Whenever you see an equal sign (=) with an expression to the right and a single word (or multiple words joined_up_like_this), the code in the cell is creating a variable.

```python
x = 4 + 5
```
(Note that Python doesn't display anything when you have a cell that just assigns a value to a variable.)

After you've run a cell with a variable assignment, you can use the name of the variable in any expression to stand in for the variable's value, e.g.:

```python
x * 3
```

```
> 27
```
Type a variable into a cell on its own and then run the cell to see the variable's contents:

```python
x
```

```
> 9
```

You can change a variable's value by assigning to it again:

```python
x = 17
x * 3
```

```
> 51
```

Note that the name of the variable doesn't matter. Usually, programmers give variables mnemonic names to help remind them what the variable is intended to do. This is nice, but sometimes beginners come to believe that the name of the variable has some magic effect. Don't fall into this trap!

## Strings and lists

The string is the Python data type that stores text and makes it easy to manipulate. There are a number of ways to get text into strings. The first is with a string literal, where you just enclose the string inside of quotes (either double or single quotes):

```python
message = "it was the best of times"
```

The second is by reading in the string from a file using open(...).read(). (For our purposes here, this should be a plain text file.) The following line will read frost.txt into a variable called text:

```python
text = open('frost.txt').read()
```

You can show a text in the notebook by simply evaluating the variable name:

```python
text
```

```
> 'Two roads diverged in a yellow wood,\nAnd sorry I could not travel both\nAnd be one traveler, long I stood\nAnd looked down one as far as I could\nTo where it bent in the undergrowth;\n\nThen took the other, as just as fair,\nAnd having perhaps the better claim,\nBecause it was grassy and wanted wear;\nThough as for that the passing there\nHad worn them really about the same,\n\nAnd both that morning equally lay\nIn leaves no step had trodden black.\nOh, I kept the first for another day!\nYet knowing how way leads on to way,\nI doubted if I should ever come back.\n\nI shall be telling this with a sigh\nSomewhere ages and ages hence:\nTwo roads diverged in a wood, and I---\nI took the one less travelled by,\nAnd that has made all the difference.\n'
```

But you'll notice that this text has a weird "control character" in it, shown as \n. This symbol actually means that the file contains a new line. If you want Python to display the string with the control characters interpreted, you can use the print() function:

```python
print(text)
Two roads diverged in a yellow wood,
And sorry I could not travel both
And be one traveler, long I stood
And looked down one as far as I could
To where it bent in the undergrowth;

Then took the other, as just as fair,
And having perhaps the better claim,
Because it was grassy and wanted wear;
Though as for that the passing there
Had worn them really about the same,

And both that morning equally lay
In leaves no step had trodden black.
Oh, I kept the first for another day!
Yet knowing how way leads on to way,
I doubted if I should ever come back.

I shall be telling this with a sigh
Somewhere ages and ages hence:
Two roads diverged in a wood, and I---
I took the one less travelled by,
And that has made all the difference.
```

Strings have a number of helpful "methods," which are little bits of code you can put after the variable name to return a copy of the string's text with some changes applied. For example, adding .upper() shows the text as all upper-case:

```python
message.upper()
```

```
> 'IT WAS THE BEST OF TIMES'
```

An especially helpful method is .split(), which "splits" a string up into units. To split a string up into words:

```python
text.split()
```

```
> ['Two',
 'roads',
 'diverged',
 'in',
 'a',
 'yellow',
 'wood,',
 'And',
 'sorry',
 'I',
 'could',
 'not',
 'travel',
 'both',
 'And',
 'be',
 'one',
 'traveler,',
 'long',
 'I',
 'stood',
 'And',
 'looked',
 'down',
 'one',
 'as',
 'far',
 'as',
 'I',
 'could',
 'To',
 'where',
 'it',
 'bent',
 'in',
 'the',
 'undergrowth;',
 'Then',
 'took',
 'the',
 'other,',
 'as',
 'just',
 'as',
 'fair,',
 'And',
 'having',
 'perhaps',
 'the',
 'better',
 'claim,',
 'Because',
 'it',
 'was',
 'grassy',
 'and',
 'wanted',
 'wear;',
 'Though',
 'as',
 'for',
 'that',
 'the',
 'passing',
 'there',
 'Had',
 'worn',
 'them',
 'really',
 'about',
 'the',
 'same,',
 'And',
 'both',
 'that',
 'morning',
 'equally',
 'lay',
 'In',
 'leaves',
 'no',
 'step',
 'had',
 'trodden',
 'black.',
 'Oh,',
 'I',
 'kept',
 'the',
 'first',
 'for',
 'another',
 'day!',
 'Yet',
 'knowing',
 'how',
 'way',
 'leads',
 'on',
 'to',
 'way,',
 'I',
 'doubted',
 'if',
 'I',
 'should',
 'ever',
 'come',
 'back.',
 'I',
 'shall',
 'be',
 'telling',
 'this',
 'with',
 'a',
 'sigh',
 'Somewhere',
 'ages',
 'and',
 'ages',
 'hence:',
 'Two',
 'roads',
 'diverged',
 'in',
 'a',
 'wood,',
 'and',
 'I---',
 'I',
 'took',
 'the',
 'one',
 'less',
 'travelled',
 'by,',
 'And',
 'that',
 'has',
 'made',
 'all',
 'the',
 'difference.']
```

Or, to split a text into lines:

```python
text.split("\n")
```

```
> ['Two roads diverged in a yellow wood,',
 'And sorry I could not travel both',
 'And be one traveler, long I stood',
 'And looked down one as far as I could',
 'To where it bent in the undergrowth;',
 '',
 'Then took the other, as just as fair,',
 'And having perhaps the better claim,',
 'Because it was grassy and wanted wear;',
 'Though as for that the passing there',
 'Had worn them really about the same,',
 '',
 'And both that morning equally lay',
 'In leaves no step had trodden black.',
 'Oh, I kept the first for another day!',
 'Yet knowing how way leads on to way,',
 'I doubted if I should ever come back.',
 '',
 'I shall be telling this with a sigh',
 'Somewhere ages and ages hence:',
 'Two roads diverged in a wood, and I---',
 'I took the one less travelled by,',
 'And that has made all the difference.',
 '']
```

You can see that .split() produces a value different from what we've seen before—this is a list. A list has multiple items in it—in this case, multiple strings. Python displays lists with an opening square bracket [, a closing square bracket ], and then the items in the list with a comma between them.

Assign a list to a variable like so:

```python
words = text.split()
```


Part of the reason to split text into lists is so we can analyze the parts themselves, or just a segment of those parts. For example, now that we've split the text into words, we can ask for the length of the text in words using the len() function:

```python
len(words)
```

```
> 144
```

Note that the len() function works on strings as well:

```python
len(message)
```

```
> 24
```


```python
len(words)
```

```
> 144
```

### Indexing

You can grab individual items from the list using square bracket indexing (note that indexes start at zero):

```python
words[0]
```

```
> 'Two'
```

```python
words[5]
```

```
> 'yellow'
```


```python
x = 7
words[x]
```

```
> 'And'
```


Using a colon between two numbers in brackets gives you a slice of the list (which is itself a list):

```python
words[2:7]
```

```
> ['diverged', 'in', 'a', 'yellow', 'wood,']
```

Negative indexes start from the end of the list; empty indexes assume the start end of the list, respectively:

```python
words[:8]
```

```
> ['Two', 'roads', 'diverged', 'in', 'a', 'yellow', 'wood,', 'And']
```


```python
words[-8:]
```

```
> ['by,', 'And', 'that', 'has', 'made', 'all', 'the', 'difference.']
```


You can use the same indexing on strings:

```python
print(message)
print(message[4:14])
it was the best of times
as the bes
```


### Making lists from scratch and modifying lists

You can also make a new list with a list literal. This takes the form of a series of values separated by commas, surrounded by square brackets:

```python
plums = ["this", "is", "just", "to", "say"]
```

The list type's .append() method adds a new item to the end of the list.

```python
plums.append("I")
plums.append("have")
plums.append("eaten")
```


```python
plums
```

```
> ['this', 'is', 'just', 'to', 'say', 'I', 'have', 'eaten']
```


### Gluing lists back together
To turn lists back into strings, you need to join() it back together. This expression glues the items back together with a space in between:

```python
' '.join(plums)
```

```
> 'this is just to say I have eaten'
```

While this expression joins them back together with an empty string (i.e., mushes the items together):

```python
''.join(plums)
> 'thisisjusttosayIhaveeaten'
```

## Random numbers

Python comes with a number of libraries—bits of pre-built code—to help with various tasks. The import keyword makes these libraries available in your notebook. The random library is one we'll use a lot:

```python
import random
```

The random library has a handful of important functions. The first we'll discuss is random.choice(), which picks a random item from a list:

```python
random.choice(words)
> 'leads'
```

The random.sample() function takes two parameters: a list to draw samples from, and the sample you want to draw. (Samples are guaranteed not to be duplicates.)

```python
random.sample(words, 5)
> ['stood', 'that', 'leads', 'really', 'kept']
```

And random.randrange() returns a random integer from zero up to (but not including) the number that you specify between the parentheses:

```python
random.randrange(14)
> 9
```


To make a d20 simulator:

```python
random.randrange(20) + 1
> 7
```

## Loops and comprehensions
To do something more than once, take the code you want to run more than once and tab it over once (i.e., indent each line by four spaces—you can do this in Jupyter Notebook by selecting the code and hitting TAB.) Above the indented code, put for i in range(n): on a line, replacing n with the number of times you want to repeat. For example, the code in this cell prints out three randomly selected words from the Frost poem:

```python
selected = random.sample(words, 3)
joined = ' '.join(selected)
print(joined)
as just if
```

And this cell does the same thing ten times:

```python
for i in range(10):
    selected = random.sample(words, 3)
    joined = ' '.join(selected)
    print(joined)
```

```
> less passing same,
be day! perhaps
really And And
ages And Then
first as made
And long and
a I I
wanted lay as
step Yet claim,
I--- ages Oh,
```

To print squares of integers less than ten:

```python
for i in range(10):
    print(i, i*i)
```

```
> 0 0
1 1
2 4
3 9
4 16
5 25
6 36
7 49
8 64
9 81
```

A common task in computer programming is to take a list and perform the same operation on each item in the list. You can do this in Python with a for loop. In this case, put the variable name referring to the list (or an expression evaluating to a list) after the word in, and use the word item instead of i. This loop prints each word in the Frost poem along with the length of the word:

```python
for item in words:
    print(item, len(item))
```

```
Two 3
roads 5
diverged 8
in 2
a 1
yellow 6
wood, 5
And 3
sorry 5
I 1
could 5
not 3
travel 6
both 4
And 3
be 2
one 3
traveler, 9
long 4
I 1
stood 5
And 3
looked 6
down 4
one 3
as 2
far 3
as 2
I 1
could 5
To 2
where 5
it 2
bent 4
in 2
the 3
undergrowth; 12
Then 4
took 4
the 3
other, 6
as 2
just 4
as 2
fair, 5
And 3
having 6
perhaps 7
the 3
better 6
claim, 6
Because 7
it 2
was 3
grassy 6
and 3
wanted 6
wear; 5
Though 6
as 2
for 3
that 4
the 3
passing 7
there 5
Had 3
worn 4
them 4
really 6
about 5
the 3
same, 5
And 3
both 4
that 4
morning 7
equally 7
lay 3
In 2
leaves 6
no 2
step 4
had 3
trodden 7
black. 6
Oh, 3
I 1
kept 4
the 3
first 5
for 3
another 7
day! 4
Yet 3
knowing 7
how 3
way 3
leads 5
on 2
to 2
way, 4
I 1
doubted 7
if 2
I 1
should 6
ever 4
come 4
back. 5
I 1
shall 5
be 2
telling 7
this 4
with 4
a 1
sigh 4
Somewhere 9
ages 4
and 3
ages 4
hence: 6
Two 3
roads 5
diverged 8
in 2
a 1
wood, 5
and 3
I--- 4
I 1
took 4
the 3
one 3
less 4
travelled 9
by, 3
And 3
that 4
has 3
made 4
all 3
the 3
difference. 11
```

(Actually, in both cases, you can use any name you want, instead of i and item, as long as you use the same name in the body of the loop.)

Another common task is to make a new list resulting from applying some operation to each item in a list—potentially skipping items if they don't meet some criterion. For example, let's say that I wanted to make a list of words that start with t in the Frost poem, converting each of these words to upper case.

There are two ways to do this. The first is with a for loop, a list that starts out empty, and .append():

```python
t_words = []
for item in words:
    if item.startswith('t'):
        upper_c = item.upper()
        t_words.append(upper_c)
print(t_words)
```

```
> ['TRAVEL',
 'TRAVELER,',
 'THE',
 'TOOK',
 'THE',
 'THE',
 'THAT',
 'THE',
 'THERE',
 'THEM',
 'THE',
 'THAT',
 'TRODDEN',
 'THE',
 'TO',
 'TELLING',
 'THIS',
 'TOOK',
 'THE',
 'TRAVELLED',
 'THAT',
 'THE']
```

The if statement in the loop serves to essentially "skip" items in the list if they don't meet some criterion. (The .startswith() method checks to see if the given string begins with the substring specified in the parentheses.)

You can also write this differently, in a format known as a list comprehension, which takes the syntax of the for loop and inverts it:

```python
t_words = [item.upper() for item in words if item.startswith('t')]
print(t_words)
```

```
> ['TRAVEL',
 'TRAVELER,',
 'THE',
 'TOOK',
 'THE',
 'THE',
 'THAT',
 'THE',
 'THERE',
 'THEM',
 'THE',
 'THAT',
 'TRODDEN',
 'THE',
 'TO',
 'TELLING',
 'THIS',
 'TOOK',
 'THE',
 'TRAVELLED',
 'THAT',
 'THE']
```

The list comprehension above does exactly the same thing as the for loop. Both syntaxes are valid! I usually prefer list comprehensions when possible, since they are shorter and more clear. I'm showing them here so that you recognize that both syntaxes are meant to accomplish the same task (i.e., make a copy of a list, modifying and potentially throwing out items from the list.)
