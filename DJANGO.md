# Django

## Opening a file on Django's Banckend

``` python
import os

curr_path = os.path.dirname(__file__) # Get the current directory

fname = os.path.join(curr_path, 'my_file.txt')
f = open(fname, 'r')
print(f.readlines()) 
```
