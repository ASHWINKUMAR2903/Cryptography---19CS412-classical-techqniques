# Cryptography - 19CS415
# Caeser Cipher
Caeser Cipher using with different key values

# AIM:
To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.

## DESIGN STEPS:
### Step 1:
Design of Caeser Cipher algorithnm 

### Step 2:
Implementation using C or pyhton code

### Step 3:
1.	In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2.	For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
3.	The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
    scheme, A = 0, B = 1, Z = 25.
4.	Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
5.	Decryption is performed similarly,
                       Dn (x)=(x - n) mod26


## PROGRAM:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char plain[100], cipher[100];
    int key, i, length;

    printf("\nEnter the plain text: ");
    scanf("%s", plain);
    printf("Enter the key value: ");
    scanf("%d", &key);

    length = strlen(plain);

    printf("\nPLAIN TEXT: %s", plain);
    printf("\nENCRYPTED TEXT: ");
    for (i = 0; i < length; i++) {
        if (isalpha(plain[i])) {  
            if (isupper(plain[i])) {
                cipher[i] = ((plain[i] - 'A' + key) % 26) + 'A';  
            } else {
                cipher[i] = ((plain[i] - 'a' + key) % 26) + 'a';  
            }
        } else {
            cipher[i] = plain[i]; 
        }
        printf("%c", cipher[i]);
    }
    cipher[length] = '\0';  

    printf("\nDECRYPTED TEXT: ");
    for (i = 0; i < length; i++) {
        if (isalpha(cipher[i])) {
            if (isupper(cipher[i])) {
                plain[i] = ((cipher[i] - 'A' - key + 26) % 26) + 'A'; 
            } else {
                plain[i] = ((cipher[i] - 'a' - key + 26) % 26) + 'a'; 
            }
        } else {
            plain[i] = cipher[i]; 
        }
        printf("%c", plain[i]);
    }
    plain[length] = '\0'; 

    return 0;
}

```

## OUTPUT:
Simulating Caesar Cipher
![image](https://github.com/user-attachments/assets/182d0d76-3b86-40ba-8bdd-45b4a39beb99)


### INPUT : ASHWIN
### KEY : 2
### Encrypted Message : CUJYKP 
### Decrypted Message : ASHWIN

## RESULT:
The program is executed successfully
