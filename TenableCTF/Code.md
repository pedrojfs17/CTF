# Tenable CTF

## Code

### **Hello ${name}**
```c
#include <stdio.h>
int main()
{
    char name[256];
    fgets(name, 256 , stdin);
    printf("Hello %s", name);
}
```

---

### **Random Encryption**
The flag is in the code
> flag{n0t_that_r4ndom}

---

### **Random Encryption Fixed**
After analyzing the code I noticed some things:
- The seeds are generated randomly
- The are generated 4 random numbers for every character of the flag (knowing the seed we are able to know these four numbers)
- One of these four numbers is used in a XOR with the flag character to get a new character returned in res
- This number is always in the position `i % 4` and after used is deleted

They give us one output. From the output we can retrieve the seeds for each character and the `res` array which has the results of the XORs. 
Running the following script takes teh values of the seeds and retrieves the flag by making the inverse XOR:
```python
import random

f = open("outputExample.txt", "r")
lines = f.readlines()
seeds = list(map(int, lines.pop()[1:-1].split(',')))
res = list(map(int, lines.pop()[1:-2].split(',')))

flagLength = len(res)
flag = ""

for i in range(0, flagLength):
    random.seed(seeds[i])
    index = i % 4
    for j in range(0,index + 1):
        number = random.randint(0,255)
    flag += chr(res[i] ^ number)

print(flag)
```
> flag{}

---

### **We need an emulator**
To solve this problem all we had to do was build an emulator to read the specified language and run the file they gave us starting the TRX register with the value `GED\x03hG\x15&Ka =;\x0c\x1a31o*5M`
Emulator in python:
```python
*emulator*
```
> flag{}