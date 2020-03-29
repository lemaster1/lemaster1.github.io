---
layout: post
title:      "Python Tips & Tricks"
date:       2020-03-29 22:01:20 +0000
permalink:  python_tips_and_tricks
---

I was reading a blog that was pushed to my inbox that had someone’s favorite Python shortcuts.  I feel like I should have known many of these already.  I started to create a cheat sheet to add to my cork-board above my desk and then thought it would be better to share these tips and tricks as part of my Blog.  Below are my top 10 (at least for now).   I will continue to add to the list


**Creating multiple variables on one code cell**
(why do I keep forgetting about this one?)
```
# instead of doing 
a = 0
b = 2
c = 4
# do this
a, b, c = 0, 2, 4
```

**Using enumerate() in for loops**
```
cars = ('corvette', 'camero', 'chevelle')
for i, car in enumerate(cars):
        print(f'Iteration: {i}, chevy muscle car: {car}')
```

**What about also using reversed() in loops**
```
cars = ['corvette', 'camero', 'chevelle']
for car in reversed(cars):
    print(car)
```

**Dictionary comprehension.**  
(I should have thought this could be done when I learned list comprehension but there’s one for dicts too)
```
dict_comprehension = {x: x ** 2 for x in range(5)}
dict_comprehension
```



**zip()**
```
cars = ['corvette', 'camero', 'chevelle']
engines = (327, 350, 396)
horsepowers = (340, 300, 375)
for car, engine, horsepower in zip(cars, engines, horsepowers):
    print(f'{car}, engine: {engine}, horsepower: {horsepower}')
```

**Shortened conditionals**
```
condition = True
# the long way
if condition:
    x = 5
    else:
        x = 3
        print(f'x is {x}')
        x is 5
# the short way
x = 5 if some_condition else 3
print(f'x is {x}')
x is 5
```

**Conditional assignment shortcut**
```
x = 10 if (y == 9) else 20
```

**Most frequent value in a List**
```
numbers = [0, 2, 4, 2, 2, 4, 4, 4, 4] 
print(max(set(test), key = numbers.count))
```

**sort()**
```
numbers = [0, 2, 4, 6]   
# sort ascending 
numbers.sort() 
numbers
# sort descending 
numbers.sort(reverse = True)
numbers
```

**Sort dictionaries.  Notice there's "ed" at the end of sorted as well as using the items() function**
```
cars = {'corvette': 327, 'camero': 350, 'chevelle': 396}
sorted(cars.items())
```

Feel free to share your Python tips and tricks in the comments. 








