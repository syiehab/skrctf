# SKR Lang

### I made a language that only have 3 letters, lets see how secure it is:
```SKRrRRrrRrRrRrSKrRrrRSKRRrRRRrRrrRRrrrrrrRrSKrrrrRRrRrrRrrRrrrRrRSKrrrrRSKRrRRRRrrrrrrRRRRrRSKRrRrrRrrrrrrRRSKrrRRRrRrRrrRrRRrRrrrrSKRRRrrrrrRRrRrSKRrSKRrrRRSKrrrRrRrRrrRRRrrRRRSKrRRRrRRRRSKrrrrrRrRrRRRRrrRrrrSKrrRSKrRRrrRrrrRRrrrRSKRRRRRRRRRrrrrRrSKrrRRRRRrrRRrrrrSKrrrrrrRRrRRrrrrSKrrRRRRrrrRRr```

### Flag format: Capital letters with no spaces SKR{DECODEDMESSAGE}

### Difficulty: Hard

After observing the pattern 


```
import string

ciphertext = "SKRrRRrrRrRrRrSKrRrrRSKRRrRRRrRrrRRrrrrrrRrSKrrrrRRrRrrRrrRrrrRrRSKrrrrRSKRrRRRRrrrrrrRRRRrRSKRrRrrRrrrrrrRRSKrrRRRrRrRrrRrRRrRrrrrSKRRRrrrrrRRrRrSKRrSKRrrRRSKrrrRrRrRrrRRRrrRRRSKrRRRrRRRRSKrrrrrRrRrRRRRrrRrrrSKrrRSKrRRrrRrrrRRrrrRSKRRRRRRRRRrrrrRrSKrrRRRRRrrRRrrrrSKrrrrrrRRrRRrrrrSKrrRRRRrrrRRr"

flag = []
count = 0
for i in range(len(ciphertext) - 1):
    if ciphertext[i] == 'S' and ciphertext[i+1] == 'K':
        r_count = 0
        for j in range(i+2, len(ciphertext)):
            if ciphertext[j].upper() == 'R':
                r_count += 1
            elif ciphertext[j] == 'S' or ciphertext[j] == 'K':
                break
        # print(f"Number of R's between SK at position {i}: {r_count}")
        flag.append(r_count)
        count += 1

print(f"Total occurrences of SK: {count}")

print(flag)

decodedtext = ""

for i in flag:
    decodedtext += string.ascii_uppercase[i]

print(decodedtext)
```
![image](https://github.com/user-attachments/assets/b97c58c1-8919-4ae0-a2fb-91ca91eaf234)
