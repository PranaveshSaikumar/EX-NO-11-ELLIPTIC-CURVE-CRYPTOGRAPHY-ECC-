# EX-NO-11-ELLIPTIC-CURVE-CRYPTOGRAPHY-ECC

## Aim:
To Implement ELLIPTIC CURVE CRYPTOGRAPHY(ECC)


## ALGORITHM:

1. Elliptic Curve Cryptography (ECC) is a public-key cryptography technique based on the algebraic structure of elliptic curves over finite fields.

2. Initialization:
   - Select an elliptic curve equation \( y^2 = x^3 + ax + b \) with parameters \( a \) and \( b \), along with a large prime \( p \) (defining the finite field).
   - Choose a base point \( G \) on the curve, which will be used for generating public keys.

3. Key Generation:
   - Each party selects a private key \( d \) (a random integer).
   - Calculate the public key as \( Q = d \times G \) (using elliptic curve point multiplication).

4. Encryption and Decryption:
   - Encryption: The sender uses the recipient’s public key and the base point \( G \) to encode the message.
   - Decryption: The recipient uses their private key to decode the message and retrieve the original plaintext.

5. Security: ECC’s security relies on the Elliptic Curve Discrete Logarithm Problem (ECDLP), making it highly secure with shorter key lengths compared to traditional methods like RSA.

## Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char msg[100], enc[100], dec[100];
    int privateKey, publicKey;
    int i;

    printf("Enter private key: ");
    scanf("%d", &privateKey);

    publicKey = privateKey * 2;

    printf("Public Key: %d\n", publicKey);

    printf("Enter message: ");
    scanf("%s", msg);

    for(i = 0; msg[i] != '\0'; i++) {
        enc[i] = msg[i] + publicKey;
    }

    enc[i] = '\0';

    printf("Encrypted Message: %s\n", enc);

    for(i = 0; enc[i] != '\0'; i++) {
        dec[i] = enc[i] - publicKey;
    }

    dec[i] = '\0';

    printf("Decrypted Message: %s", dec);

    return 0;
}
```


## Output:
<img width="1341" height="838" alt="image" src="https://github.com/user-attachments/assets/a8f4e6fd-9f2a-49cd-9815-27e7c98b0d2a" />


## Result:
The program is executed successfully

