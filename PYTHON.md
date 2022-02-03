# Python

## Removing Not Printable Characters

**Case 1 - High Characters**

<https://www.pythonpool.com/remove-unicode-characters-python/>

``` python
#input string
str = "This is Python \u500cPool"

#ord() function
output = ''.join([i if ord(i) < 128 else '?' for i in str])

#output
print("After removing Unicode character : ",output)

```

**Case 2 - Econdig**

<https://www.pythonpool.com/remove-unicode-characters-python/>

``` python
#input string
str = "This is Python \u500cPool"
 
#encode() method
strencode = str.encode("ascii", "replace")
 
#decode() method
strdecode = strencode.decode()
 
#output
print("Output after removing Unicode characters : ",strdecode)

```


**Case 3 - String Printable**

<https://www.geeksforgeeks.org/python-string-printable/>

``` python
# import string library function 
import string 
    
# An input string.
Sentence = "Hey, Geeks !, How are you?"

newstr = ""
for i in Sentence:

    # checking whether the char is printable value
    if i in string.printable:
        # Printing the printable values 
        # print("printable Value is: " + i)
        newstr += str(i)
        
print(newstr)

```
