# Warzone Pythonistas: Fourth meeting


#### For working tonight:

launch your own session at:  
https://github.com/firasm/RTC_test


## Main Meeting Content

- arranging windows in JupyterLab
- attaching consoles (interpreter) to a notebook to query active namespace
- gist
- pastebin
- fetching markdown and scripts from Github into Binder sessions
- `%%bash` cell magic and bash's `echo` command (equivalent to Python's `print`)
- expanding coverage of `Functions`
    - local scope for variables solely inside functions
    - best practice is to pass variables that will change in and out of a function explicitly
    - functions can use global variables if not changed and so in that case you **can get away without** passing into the function
    - Intermediate: returning more than one variable from a function - see code examples below
- IPython and Jupyter commands to query namespace:
    - who
    - whos


## Intermediate: returning more than one variable from a function

```python=
def distance(s,init_char,end_char):   
    '''
    Holden's distance function
    Takes a string, and two letters to find the distance between.
    
    returns: integer distance between provided characters
    '''
    v = 609
    #print(v)
    answer = s.index(end_char) - s.index(init_char)
    return answer, v


a = "djhahkerjekkdkkklwjrkgpepe"
d,vISV = distance(a, "a", "g")
print(d)
print(vISV)
```

```python=
def x(a,b):
    a = a + 3
    b = b * 3
    print(a)
    print(b)

x(2,4)
a = 4
b = 2
print(a,b)
```

