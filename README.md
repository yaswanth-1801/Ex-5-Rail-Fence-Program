# Ex-5 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100], rail[10][100];
    int i, j, k = 0, r = 2, len;

    printf("Enter text: ");
    scanf("%99s", text);

    len = strlen(text);

    for (i = 0; i < r; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = '\0';

    for (i = 0; i < len; i++)
        rail[i % r][i] = text[i];

    printf("Encrypted text: ");
    for (i = 0; i < r; i++)
        for (j = 0; j < len; j++)
            if (rail[i][j] != '\0')
                printf("%c", rail[i][j]);

    return 0;
}
```

# OUTPUT
<img width="1130" height="732" alt="image" src="https://github.com/user-attachments/assets/79d37e96-daf9-401f-8d51-731da8d14f2b" />


# RESULT
Thus, the above Rail Fence Program is executed Successfully.
