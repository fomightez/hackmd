# Warzone Pythonistas: Fifth meeting


#### For working tonight:

launch your own session at:  
https://github.com/firasm/RTC_test


Preliminaries:

- Tool to help you write shell scripts: [ShellCheck - finds bugs in your shell scripts](https://www.shellcheck.net/)
- Whoops! Good example of why Github is nice. Luke saw me wondering why running a notebook from [here](https://github.com/fomightez/pdbsum-binder) wasn't working.[history of a particular script](https://github.com/fomightez/structurework/commits/master/pdbsum-utilities/similarities_in_proteinprotein_interactions.py). Look at the Commit on April 9th there by clicking the button with `61b5d08` on the right of it in the History listing.
- Further musings on 'Getting code from GitHub that you can work with' from last session discussion. 
  - I suggest that Binder is best for now because can edit code and run and even update the environment if you need to do that in order to run. (fetch via `curl` or `wget` or clone with `git clone`)
  - If you just want to edit the code from Github check out adding `1s` in front of `.com` in URL. Example: [Plain Github example page](https://github.com/fomightez/pdbsum-binder) at `https://github.com/fomightez/pdbsum-binder` vs [Github Example in VSCode in your browser](https://github1s.com/fomightez/pdbsum-binder) at `https://github1s.com/fomightez/pdbsum-binder`.
  - Related: 
      - [VS Code added 'Open a GitHub repository in VS Code *remotely* and browse in Code *without cloning.* '](https://code.visualstudio.com/blogs/2021/06/10/remote-repositories)
      - [gitpod.io](https://www.gitpod.io/) - See 'Launch an example workspace' in bottom right corner 


## Main Meeting Content
- arguments vs. parameters in relation to functions 

- loops
- iterating
- range()

```python=
for i in range(1,10):
    print(i)

for i in range(10):
    print(i)

for i in range(1,10+1):
    print(i)
    
for i in range(10,1-1,-2):
    print(i)
    
for i in range(100,90-1,-2):
    print(i)
    
#for x in ITERATOR: <---- pseudocode model of `for` loop- you can loop on any iterable
```

- break and continue

- Loops and sets - some collecetions that are iterable

```python
#for x in ITERATOR: <---- pseudocode model of `for` loop- you can loop on any iterable

l = [1,3,4,66,66,66,99,99,100,101]


l[3] =909

len(l)

a = set(l)

len(a)

type(a)

d = {3,33}

a.union(d)

a.intersection(d)

b = list(a)


type(b)

kitchen_sink_list = [1,"abcsd",3.4,"g"] # YOU CAN PUT ANYTHING TOGETHER IN A LIST!

```
- enumerate()

```python
for indx,v in enumerate(l):
    print(indx, v)
```

- HOMEWORK: Think about how to refactor `distance` function to use enumerate




