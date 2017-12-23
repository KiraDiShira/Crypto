- [Index](https://github.com/KiraDiShira/Crypto#crypto)   

# Cryptographic Tidbits

- [Codes vs chiphers](#codes-vs-chiphers)   
- [Transposition vs substitution](#transposition-vs-substitution)
- [Monoalphabetic vs polyalphabetic](#monoalphabetic-vs-polyalphabetic)
- [Cryptanalysis](#cryptanalysis)

## Codes vs chiphers

**Code**: mapping entire sentences to shorter words

<img src="https://github.com/KiraDiShira/Crypto/blob/master/Cryptographic%20Tidbits/Images/cac1.png" />

**Cipher**: Character/symbol replacement. Do not involve meaning. Instead they are mechanical operations, known as algorithms, that are performed on individual or small chunks of letters. For example, in the Caesar Cipher we saw how each letter in the alphabet was mapped to a different letter: A=D,  B=E, and C=F, according to a specific shift, in this case three. This kind of cipher is known as a shift cipher

## Transposition vs substitution

In cryptography, a **substitution cipher** is a method of encrypting by which units of plaintext are replaced with ciphertext, according to a fixed system; the "units" may be single letters (the most common), pairs of letters, triplets of letters, mixtures of the above, and so forth. The receiver deciphers the text by performing the inverse substitution.

Substitution ciphers can be compared with **transposition ciphers**. In a transposition cipher, the units of the plaintext are rearranged in a different and usually quite complex order, but the units themselves are left unchanged. By contrast, in a substitution cipher, the units of the plaintext are retained in the same sequence in the ciphertext, but the units themselves are altered.

## Monoalphabetic vs polyalphabetic

A **monoalphabetic cipher** is a substitution cipher in which the cipher alphabet is fixed through the encryption process. These ciphers are highly susceptible to frequency analysis.

A **polyalphabetic cipher** is one based on substitution using multiple substitution alphabets. A good example would be the Vigenère Cipher which is basically a Caesar’s Cipher applied multiple times successively on the same plaintext. That is, use the Caesar Cipher on the plaintext. Then take that output and use a different substitution alphabet and then take that output and do it again with yet another substitution alphabet.

## Cryptanalysis

Cryptanalysis is used to breach cryptographic security systems and gain access to the contents of encrypted messages, even if the cryptographic key is unknown.

• Brute Force Attack (BFA) – try every possible key

• BFA requires O(key space) operations to break 

• Spurious messages (additional keys that produce meaningful but incorrect plain text messages)

The more cipher text we have, the less likely it is that incorrect keys will produce seemingly meaningful messages. The amount of text that is expected to reduce the number of spurious messages to zero is known as the **unicity distance**.
 
Though we design our system to try to avoid this, we generally assume that an attacker will have sufficient cipher text material so that only one key, the correct one, will result in meaningful plain text.

Weaknesses in the design of the cipher or how it is used often result in the ability to develop cryptanalytic techniques that can break the cipher in fewer key trials or a comparable amount of other computation than a brute force attack would require. A cipher is considered to be computationally secure if the best known attack against it is not significantly better than brute force. How much better constitute significantly better is somewhat subjective, and usually related to whether it brings the attack within the range of capabilities that currently exist or likely to exist in the foreseeable future, specifically before the utility of the intercepted  traffic expires.

