# Warzone Pythonistas: Third meeting


#### For working tonight:

launch your own session at:  
https://github.com/firasm/RTC_test


## Main Meeting Content

- objects
- strings
- integers
- floats
- booleans
- comparative operators - mainly you are going to use these in writing conditionals
- type conversion
- index
- slices
- touched on concepts of immutability
- touched on `assert`
- BAsics of function writing
- DRY "Do not repeat yourself" ===> concept of 'modularity'
- Start small & KISS - "Keep it simple, stupid."

#### Early example function
```python
def distance(s):   
    '''
    Holden's distance function
    Takes a string
    
    returns: integer distance between a and g
    '''
    answer = a.index("a") - a.index("g")
    return answer


a = "djhahkerjekwjrkgpepe"
d = distance(a)
print(d)
```


#### Evolved example function
```python
def distance(s,init_char,end_char):   
    '''
    Holden's distance function
    Takes a string
    
    returns: integer distance between provided characters
    '''
    answer = a.index(end_char) - a.index(init_char)
    return answer


a = "djhahkerjekwjrkgpepe"
d = distance(a, "a", "g")
print(d)
```

Write functions initially as stubs expecting them to do what they say.
"Keep it simple, stupid."

Objects inside a function are local to a function.
Best practice is to avoid using `global` to make a local object global.
Pass it back or define it as a global outside function.
We didn't get to this, yet but will & is related to that: If you don't modify a global, you can use a global inside a function without passing it in.
