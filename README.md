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
    char plaintext[50];
    int key[2][2];
    int i, p1, p2, c1, c2;

    printf("Enter the plaintext (uppercase letters only): ");
    scanf("%s", plaintext);

    printf("Enter the 2x2 key matrix:\n");
    for(i = 0; i < 2; i++)
    {
        scanf("%d %d", &key[i][0], &key[i][1]);
    }

    if(strlen(plaintext) % 2 != 0)
    {
        strcat(plaintext, "X");
    }

    printf("Cipher text: ");

    for(i = 0; i < strlen(plaintext); i += 2)
    {
        p1 = plaintext[i] - 'A';
        p2 = plaintext[i + 1] - 'A';

        c1 = (key[0][0] * p1 + key[0][1] * p2) % 26;
        c2 = (key[1][0] * p1 + key[1][1] * p2) % 26;

        printf("%c%c", c1 + 'A', c2 + 'A');
    }

    return 0;
}
```
## OUTPUT

<img width="386" height="145" alt="image" src="https://github.com/user-attachments/assets/63fee729-387a-4eb7-a3fc-c09bb165ae54" />

## RESULT
the Hill Cipher substitution technique was successfully implemented using a C program.
