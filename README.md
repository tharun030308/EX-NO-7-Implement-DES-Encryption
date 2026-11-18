# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.

2. DES uses a Feistel network structure with 16 rounds of processing for encryption.

3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).

4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```

#include <stdio.h>
#include <string.h>
#include <openssl/des.h>

int main()
{
    DES_cblock key;
    DES_key_schedule schedule;
    DES_cblock input, output;

    printf("Enter 8-character key: ");
    scanf("%8s", (char *)key);

    printf("Enter 8-character plaintext: ");
    scanf("%8s", (char *)input);

    DES_set_key_unchecked(&key, &schedule);

    DES_ecb_encrypt(&input, &output, &schedule, DES_ENCRYPT);

    printf("Encrypted data: ");
    for(int i = 0; i < 8; i++)
        printf("%02X", output[i]);

    printf("\n");

    return 0;
}
```




## Output:
<img width="347" height="66" alt="image" src="https://github.com/user-attachments/assets/c56add86-4260-4d0c-a4af-94e2d34f9d22" />



## Result:
  The program is executed successfully

