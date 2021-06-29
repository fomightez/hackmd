# Warzone Pythonistas: Sixth meeting


#### For working tonight:

launch your own session at:  
https://github.com/firasm/RTC_test



## Main Meeting Content

- code folding

- Python actively evolves. Example from a recent 'Python Enhancement Proposal':  
    Python 3 adds match statement which is like a switch statement!!!!
    
    >"The match statement that will debut in Python 3.10 looks really interesting; there's a nice description & tutorial here: https://python.org/dev/peps/pep-0636/
    It's superficially like a switch statement in C, but much more powerful.
    https://www.python.org/dev/peps/pep-0636/" - [SOURCE Jake VanderPlas's Twitter post](https://twitter.com/jakevdp/status/1359563188870631427)   February 2021

- checking Python version

```python
import sys
print(sys.version)
```

- write text to file:
```python=
blabla= " These are Holden's results: He has sharks"
# Save text
with open("Holden's results.txt", 'w') as output:
    output.write(blabla)
```

- Intro to loops for Holden

- Using APIs to connect to and extract data from databases or web services using Python. Example: [Use pyzillow](https://pypi.org/project/pyzillow/) to use python to interact with the [Zillow API](https://www.zillow.com/howto/api/APIOverview.htm)

For next time:
- refactor the distance function from the third and fourth sessions to use enumerate and not `.index()` method.
