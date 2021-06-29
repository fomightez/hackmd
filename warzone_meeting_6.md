# Warzone Pythonistas: Sixth meeting


#### For working tonight:

launch your own session at:  
https://github.com/firasm/RTC_test


Preliminaries:

- ??? 


## Main Meeting Content

- code folding

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
