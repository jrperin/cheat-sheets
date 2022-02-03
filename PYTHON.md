# Python

## Removing Not Printable Characters

**Case 1 - High Characters:**

``` python
#input string
str = "This is Python \u500cPool"

#ord() function
output = ''.join([i if ord(i) < 128 else '?' for i in str])

#output
print("After removing Unicode character : ",output
```
