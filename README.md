# Perin's Cheat Sheet Colletion

General tips



## Django

**Abrir um arquivo no backend do Django:**
``` python
import os

curr_path = os.path.dirname(__file__) # Get the current directory

fname = os.path.join(curr_path, 'my_file.txt')
f = open(fname, 'r')
print(f.readlines()) 
```
