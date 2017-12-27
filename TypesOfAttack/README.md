- [Index](https://github.com/KiraDiShira/Crypto#crypto)   

# Types of attack

- [Attacks on encryption schemes](#attacks-on-encryption-schemes)   

## Attacks on encryption schemes

The objective of the following attacks is to systematically recover plaintext from ciphertext, or even more drastically, to deduce the decryption key

1. A **ciphertext-only attack** is one where the adversary (or cryptanalyst) tries to deduce the decryption key or plaintext by only observing ciphertext. Any encryption scheme vulnerable to this type of attack is considered to be completely insecure.

2. A **known-plaintext attack** is one where the adversary has a quantity of plaintext and corresponding ciphertext. This type of attack is typically only marginally more difficult to mount.

3. A **chosen-plaintext attack** is one where the adversary chooses plaintext and is then given corresponding ciphertext. Subsequently, the adversary uses any information deduced in order to recover plaintext corresponding to previously unseen ciphertext.

4. An **adaptive chosen-plaintext attack** is a chosen-plaintext attack wherein the choice of plaintext may depend on the ciphertext received from previous requests.

5. A **chosen-ciphertext attack** is one where the adversary selects the ciphertext and is then given the corresponding plaintext. One way to mount such an attack is for the adversary to gain access to the equipment used for decryption (but not the decryption key, which may be securely embedded in the equipment). The objective is then to be able, without access to such equipment, to deduce the plaintext from (different) ciphertext.
