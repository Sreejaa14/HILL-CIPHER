# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
#include <stdio.h>
#include <string.h>
int main()
{
    int key[3][3];
    char text[100];
    int i, j, k;
    printf("Enter the 3x3 key matrix:\n");
    for(i = 0; i < 3; i++)
    {
        for(j = 0; j < 3; j++)
        {
            scanf("%d", &key[i][j]);
        }
    }
    printf("Enter the plaintext (UPPERCASE): ");
    scanf("%s", text);
    int len = strlen(text);
    while(len % 3 != 0)
    {
        text[len] = 'X';
        len++;
    }
    text[len] = '\0';
    printf("Encrypted Text: ");
    for(i = 0; i < len; i += 3)
    {
        int p[3], c[3];
        for(j = 0; j < 3; j++)
            p[j] = text[i + j] - 'A';
        for(j = 0; j < 3; j++)
        {
            c[j] = 0;
            for(k = 0; k < 3; k++)
            {
                c[j] += key[j][k] * p[k];
            }
            c[j] %= 26;
        }
        for(j = 0; j < 3; j++)
            printf("%c", c[j] + 'A');
    }
    
    printf("\n");
    return 0;
}
```
## OUTPUT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/41158f47-23d7-4b1d-a665-72b07b1df312" />


## RESULT
