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
    int i, j, key, len;

    printf("Enter text: ");
    scanf("%99s", text);

    printf("Enter key: ");
    scanf("%d", &key);

    len = strlen(text);

    if (key < 2 || key > 10) {
        printf("Invalid key");
        return 0;
    }

    for (i = 0; i < key; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = '\0';

    i = 0;
    int row = 0, dir = 1;

    for (j = 0; j < len; j++) {
        rail[row][j] = text[j];

        if (row == 0)
            dir = 1;
        else if (row == key - 1)
            dir = -1;

        row += dir;
    }

    printf("Encrypted text: ");

    for (i = 0; i < key; i++)
        for (j = 0; j < len; j++)
            if (rail[i][j] != '\0')
                printf("%c", rail[i][j]);

    return 0;
}
```

# OUTPUT
<img width="1123" height="752" alt="image" src="https://github.com/user-attachments/assets/8369196e-9e6a-4a71-af49-0bed4547836b" />



# RESULT
Thus, the above Rail Fence Program is executed Successfully.
