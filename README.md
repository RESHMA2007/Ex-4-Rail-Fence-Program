# Rail Fence Cipher

Rail Fence Cipher using different key values

## AIM

To develop a simple C program to implement the Rail Fence Cipher.

## DESIGN STEPS
### Step 1

Design the Rail Fence Cipher algorithm.

### Step 2

Implement the algorithm using C or Python code.

### Step 3

Test the algorithm with different key values.

#### ALGORITHM DESCRIPTION

In the Rail Fence Cipher, the plaintext is written downwards and diagonally on successive rails of an imaginary fence. When the bottom rail is reached, the direction is changed upwards. Similarly, when the top rail is reached, the direction is changed downwards again. This process continues until the entire plaintext is written.
Finally, the encrypted message is obtained by reading the characters row by row.

## PROGRAM
```
#include <stdio.h>
#include <string.h>

int main()
{
    int i, j, len, rails, count = 0;
    char str[1000];
    int code[100][1000] = {0};

    printf("Enter a Secret Message:\n");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    len = strlen(str);

    printf("Enter number of rails:\n");
    scanf("%d", &rails);

    j = 0;
    while (j < len)
    {
        if (count % 2 == 0)
        {
            for (i = 0; i < rails && j < len; i++)
                code[i][j++] = str[j - 1];
        }
        else
        {
            for (i = rails - 2; i > 0 && j < len; i--)
                code[i][j++] = str[j - 1];
        }
        count++;
    }

    printf("Encrypted Message:\n");
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            if (code[i][j] != 0)
                printf("%c", code[i][j]);

    return 0;
}
```
## OUTPUT
<img width="1475" height="982" alt="Screenshot 2026-02-02 041856" src="https://github.com/user-attachments/assets/c988954a-9ad1-4e54-b821-a47f0a233b5e" />


## RESULT:
The program was executed successfully, and the Rail Fence Cipher encryption was obtained for the given input.
