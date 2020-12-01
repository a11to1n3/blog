---
toc: true
layout: post
description: You did not know Python strings like you thought
categories: [python-string]
title: You haven’t known Python string
---
## Intro
You’d probably heard a lot about python strings, especially from the very first step into this programing language.

```python
print('Hello World!')
```
—> `Hello World!`

The above sentence might bring you back to your first compiled line of code, right? Sure, but you might miss a lot more than that in python string manipulation methods.

Behold, the following levels of missing stuff will be increasing EXPONENTIALLY!!!!

## String is an array of characters
That means, you can check for its length, traverse through each character in the string and check if a substring exists inside a string, **BUT** you cannot edit a character in place by calling its index like so in an array (`name[0] = 'A'`) because strings are immutable. That means every change in a string would return a new string.

### Check length
```python
name = 'My name is DAP'
print(len(name)) # 14
```
### Looping/ slicing through a string
```python
name = 'My name is DAP'

# Slicing
print(name[-3:]) # DAP

# Traversing
for character in name:
	if character == 'D':
		print(character) # D
```
### Check substring
```python
name = 'My name is DAP'
search_term = 'DAP'
if search_term in name:
	print('Your name is correct')
```

## Python strings support wonderful methods
Till here, you might ask, how one can change a letter of a string in place. Well, probably not, but there is `replace` method, which can change one specific character in the string ‘in place’  <— and assign it to a new string.
### replace()
```python
string = 'I have a cat'
print(string.replace('t', 'r')) # I have a car
```
### strip(), split(), join() - the three pillars in text manipulation

Very often should your text contain unwanted characters like spaces, escape characters such as tabs, enters, etc.. These can be removed by the **strip()** function.

For example, if you want to remove the spaces between your telephone number, **strip()** will be your life savior.
```python
tel = '012 345 678'
print(tel.strip()) # '012345678'
```

What if now you don’t want to remove the spaces, but you would like to replace them with hyphens instead, **split()** and **join()** will do the job. Specifically, **split()** can help one separate all the sets of numbers by spaces into a list, then **join()** will stick them together using a predefined character.
```python
tel = '012 345 678'
tel_el = tel.split(' ')

# Split the sets
print(tel_el) # ['012','345','678']

# Join back with hyphens
tel = '-'.join(tel_el) 
print(tel) # 012-345-678
```

### Check starting and ending substring with startswith(), endswith() 
In some cases, you would like to check whether your string (could be a filename) starts with some prefix or has some kinds of extension, you probably need to use **startswith()** and **endswith()**.

```python
filename = 'Apple.avi'
# Search for an Apple movie
if filename.startswith('Apple'):
	print(filename)

# Search for a movie extension  (.avi), not an image extension (.jpg)
if filename.endswith('.avi'):
	print(filename)
```

## Modern printing approach with variables
How would you print a sentence to show up your result of a calculation? Normally, one just separates the variable with their own words by a comma.
```python
age = 16
print('I am ',age,' years old') # I am 16 years old
```
Or if the variable is a string, one can also use string concatenation.
```python
name = 'DAP'
print('My name is ' + name) # My name is DAP
```
So, do you realize what is really inconvenient in the above examples? Yes, obviously the static position of the variable made us really annoyed. Therefore, nowadays, coders tend to use more dynamic approaches, namely **f string** and **string format**.

### What is f string?
f string is nothing but a normal string, but it comes with a dynamic parenthesis to include dynamic variable, which comes right inside the string. This way, one can move the variable around without thinking of how they can do a proper string concatenation or the position variable when putting strings and variables together in the print function.
```python
name = 'DAP'
intro = f'My name is {name}'
print(intro) # My name is DAP
```
### How string format differs from F string?
Well, essentially you can notice that although f strings are pretty dynamic with movable variable right inside its body, still one must call the variable name in the parentheses. That’s where string format methods come into place. With such method, coders can just leave a blank in a string and filling in it later.
```python
name = 'DAP'
intro = 'My name is {}'.format(name)
print(intro) # My name is DAP
```
The being filled variables are input accordingly to the order of the parentheses (positional variables). There is another option which makes string format method an exact match to f string, that is to assign for each parenthesis a variable name.

```python
name = 'DAP'
intro = 'My name is {name}'.format(name=name)
print(intro) # My name is DAP
```

That pretty much concludes my point of view about how miracle a python string could be.

Enjoy coding!