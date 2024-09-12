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
