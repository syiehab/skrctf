# SKR Lang

## I made a language that only have 3 letters, lets see how secure it is:
```SKRrRRrrRrRrRrSKrRrrRSKRRrRRRrRrrRRrrrrrrRrSKrrrrRRrRrrRrrRrrrRrRSKrrrrRSKRrRRRRrrrrrrRRRRrRSKRrRrrRrrrrrrRRSKrrRRRrRrRrrRrRRrRrrrrSKRRRrrrrrRRrRrSKRrSKRrrRRSKrrrRrRrRrrRRRrrRRRSKrRRRrRRRRSKrrrrrRrRrRRRRrrRrrrSKrrRSKrRRrrRrrrRRrrrRSKRRRRRRRRRrrrrRrSKrrRRRRRrrRRrrrrSKrrrrrrRRrRRrrrrSKrrRRRRrrrRRr```
## Flag format: Capital letters with no spaces SKR{DECODEDMESSAGE}
## Difficulty: Hard

### Hint: The message total 20 letters
### Hint: Count and remember lower and upper does not matter


After observing the pattern of the cipher text and the hint, I figured that we need to count the letter ```R``` in between the letters ```SK```

So I made a code to print the number of letter ```R``` between ```SK``` and print the corresponding ascii character


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
    decodedtext += string.ascii_uppercase[i-1]

print(decodedtext)
```

The output:
![image](https://github.com/user-attachments/assets/280e9ad5-2c0f-498f-85f1-ad8969e40f5c)



Flag: ```SKR{LETTERNUMBERISCOOOOL}```
