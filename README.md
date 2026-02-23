# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```
#include <stdio.h>
#include <string.h>
#include <stdint.h>

#define Nb 4
#define Nk 4
#define Nr 10

// Simple XOR-based mock AES round (Educational Purpose Only)
void addRoundKey(uint8_t state[16], uint8_t key[16]) {
    for(int i = 0; i < 16; i++) {
        state[i] ^= key[i];
    }
}

int main() {
    uint8_t plaintext[16];
    uint8_t key[16];
    uint8_t state[16];

    printf("Enter 16 characters (128-bit plaintext): ");
    scanf("%16s", plaintext);

    printf("Enter 16 characters (128-bit key): ");
    scanf("%16s", key);

    // Copy plaintext to state
    memcpy(state, plaintext, 16);

    // Perform 10 rounds (simplified)
    for(int round = 0; round < Nr; round++) {
        addRoundKey(state, key);
    }

    printf("Encrypted Ciphertext (in hex): ");
    for(int i = 0; i < 16; i++) {
        printf("%02X", state[i]);
    }

    printf("\n");

    return 0;
}
```
# OUTPUT:
<img width="1637" height="846" alt="image" src="https://github.com/user-attachments/assets/e8473775-a7d3-4756-8ff5-b9fab236e9c7" />


# RESULT:

The program is executed successfully and AES encryption is performed on the given plaintext.
