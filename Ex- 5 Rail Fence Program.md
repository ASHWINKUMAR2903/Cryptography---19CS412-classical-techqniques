# Cryptography - 19CS415
# Rail Fence Cipher
Rail Fence Cipher using with different key values

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## DESIGN STEPS:

### Step 1:

Design of Rail Fence Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
In the rail fence cipher, the plaintext is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>

void main()
{
    int i, j, k, l;
    char a[100], c[100], d[100]; // Increased array size for longer input
    
    printf("\n\t\tRAIL FENCE TECHNIQUE");
    printf("\n\nEnter the input string: ");
    
    // Using fgets to read the entire line including spaces
    fgets(a, sizeof(a), stdin);
    
    // Remove newline character if present at the end of the input
    a[strcspn(a, "\n")] = '\0';
    
    l = strlen(a);  // Length of the input string
    
    // Ciphering
    for (i = 0, j = 0; i < l; i++) {
        if (i % 2 == 0)
            c[j++] = a[i];
    }
    for (i = 0; i < l; i++) {
        if (i % 2 == 1)
            c[j++] = a[i];
    }
    c[j] = '\0';
    
    printf("\nCipher text after applying rail fence: %s", c);
    
    // Deciphering
    if (l % 2 == 0)
        k = l / 2;
    else
        k = (l / 2) + 1;
    
    for (i = 0, j = 0; i < k; i++) {
        d[j] = c[i];
        j += 2;
    }
    for (i = k, j = 1; i < l; i++) {
        d[j] = c[i];
        j += 2;
    }
    d[l] = '\0';
    
    printf("\nText after decryption: %s", d);
}

```
## OUTPUT:
![image](https://github.com/user-attachments/assets/ae3d1845-6fae-40fa-b978-55e5c8e67e7e)

## RESULT:
The program is executed successfully
