# Warzone Pythonistas: Seventh meeting


#### For working tonight:

launch your own session at:  
https://github.com/firasm/RTC_test


Preliminaries:

- ??? 


## Main Meeting Content


- GOAL: refactor the distance function from the third and fourth sessions to use enumerate and not `.index()` method.



- enumerate review

```
l = [1,3,4,66,66,66,99,99,100,101]

for indx,v in enumerate(l):
    print(indx,v)

for indx,v in enumerate(l[::-1]):
    print(indx,v)

sb = "asoiarkhkrjhqekrhewqkjrhkjeqw"
for indx,v in enumerate(sb[::-1]):
    print(indx,v)

l2 = ["abc","def","efghi", "jklemne"]

for indx,v in enumerate(l2):
    print(indx,v)
    for indx2,subv in enumerate(v):
        print(indx2,subv)

```

**Original version of Holden's function**

```
def distance(s,init_char,end_char):   
    '''
    Holden's distance function
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    answer = s.index(end_char) - s.index(init_char)
    return answer


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance(a, "a", "g")
d2 = distance(b, "h", "g")
print(d)
print(d2)
```

**Original version of Holden's function with alternative input**

```
def distance(s,init_char,end_char):   
    '''
    Holden's distance function
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    answer = s.index(end_char) - s.index(init_char)
    return answer


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance(a, "p", "e")
d2 = distance(b, "w", "e")
print(d)
print(d2)
```

**Original version of Holden's function with `rfind` to index from right side**
```
def distance(s,init_char,end_char):   
    '''
    Holden's distance function
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    answer = s.rfind(end_char) - s.rfind(init_char)
    return answer


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance(a, "p", "e")
d2 = distance(b, "w", "e")
print(d)
print(d2)
```

**Holden's distance function - re-implemented using enumeration**

```
def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    for indx,c in enumerate(s):
        if c == init_char:
            pos_init_char = indx
        if c == end_char:
            pos_end_char = indx
    return pos_end_char - pos_init_char


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "a", "g")
d2 = distance_enum(b, "h", "g")
print(d)
print(d2)
```

**Re-implementation using enumeration with the alternative input**

def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    for indx,c in enumerate(s):
        if c == init_char:
            pos_init_char = indx
        if c == end_char:
            pos_end_char = indx
    return pos_end_char - pos_init_char


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "p", "e")
d2 = distance_enum(b, "w", "e")

print(d)
print(d2)
```

****Re-implementation using enumeration TO COMPARE TO BELOW**

```
def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    for indx,c in enumerate(s):
        if c == init_char:
            pos_init_char = indx
        if c == end_char:
            pos_end_char = indx
    return pos_end_char - pos_init_char


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "p", "e")
d2 = distance_enum(b, "w", "e")

print(d)
print(d2)
```

****Re-implementation using enumeration Iterating reverse just by adding ``[::-1]``**
def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    for indx,c in enumerate(s[::-1]):
        if c == init_char:
            pos_init_char = indx
        if c == end_char:
            pos_end_char = indx
    return pos_end_char - pos_init_char


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "p", "e")
d2 = distance_enum(b, "w", "e")

print(d)
print(d2)
```

Is that more flexible than adding `rfind` in two places in the original implementation? Might seem it in long run, and in fact the whole thing is more flexible with enumeration, but original is more succinct when you just want first instance.


### Add continue to enumeration version so once we get both values we end the iterating, presumably saving time on much longer strings

```
def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    pos_init_char = None
    pos_end_char = None
    for indx,c in enumerate(s):
        if c == init_char and pos_init_char == None:
            pos_init_char = indx
            continue
        if c == end_char and pos_end_char == None:
            pos_end_char = indx
            continue
    return pos_end_char - pos_init_char


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "p", "e")
d2 = distance_enum(b, "w", "e")

print(d)
print(d2)
```

And calling that version with the alternative input
```
def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    pos_init_char = None
    pos_end_char = None
    for indx,c in enumerate(s):
        if c == init_char and pos_init_char == None:
            pos_init_char = indx
            continue
        if c == end_char and pos_end_char == None:
            pos_end_char = indx
            continue
    return pos_end_char - pos_init_char


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "p", "e")
d2 = distance_enum(b, "w", "e")

print(d)
print(d2)
```


### Try and except

```
def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    pos_init_char = None
    pos_end_char = None
    for indx,c in enumerate(s):
        if c == init_char and pos_init_char == None:
            pos_init_char = indx
            continue
        if c == end_char and pos_end_char == None:
            pos_end_char = indx
            break
    answer =  pos_end_char - pos_init_char
    return answer


a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "p", "e")
d2 = distance_enum(b, "w", "e")

print(d)
print(d2)
```

That can cause an error if the 'second' character occurs before the first so still `None` when it tries to the the calculation for answer. Ideally, you revert the added `break` back. However, do you have alternatives to handle it without changing it back? Maybe alert the user would be nice? 

**Alert user by adding try..except:**

```
def distance_enum(s,init_char,end_char):   
    '''
    Holden's distance function - re-implemented using enumeration
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    pos_init_char = None
    pos_end_char = None
    for indx,c in enumerate(s):
        if c == init_char and pos_init_char == None:
            pos_init_char = indx
            continue
        if c == end_char and pos_end_char == None:
            pos_end_char = indx
            break
    try:
        answer =  pos_end_char - pos_init_char
    except TypeError:
        import sys
        sys.stderr.write("One of the positions is not defined yet and is None\n")
        return ("problem\n")
    return answer

import sys
a = "djhahkerjekwjrkgpepe"
b = "djhahkxnbcxwjrkgpepe"
d = distance_enum(a, "p", "e")
d2 = distance_enum(b, "w", "e")

sys.stderr.write(d)
sys.stderr.write(str(d2))
```

**Note** that ideally after defining the function as above, you'd put the following in one cell:
```
d = distance_enum(a, "p", "e")
print(d)
```

And the following in another cell:
```
d2 = distance_enum(b, "w", "e")
print(d2)
```

**and then wouldn't need to have the output go to stderr channel**. However, for sake of code blocks we had all as one and saw race condition between output and error message for d and d2, and they'd get out of order when print and stderr triggered. Couldn't tell to which call of the function the stderr message corresponded when it was a single code cell. To keep as a single code block just make everything go to `print` or `stderr`. Doing the latter is how we ended up with the code block above.


**Another example of try..except from the documentation:**

```
# from https://docs.python.org/3/tutorial/errors.html
>>> while True:
...     try:
...         x = int(input("Please enter a number: "))
...         break
...     except ValueError:
...         print("Oops!  That was no valid number.  Try again...")
...
```
