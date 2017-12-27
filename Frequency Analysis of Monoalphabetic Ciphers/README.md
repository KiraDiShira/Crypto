- [Index](https://github.com/KiraDiShira/Crypto#crypto)   

# Frequency Analysis of Monoalphabetic Ciphers

- [One time pad](#one-time-pad)   

## One time pad

The **one-time pad** (OTP) is an encryption technique that cannot be cracked, but requires the use of a one-time pre-shared key the same size as, or longer than, the message being sent. In this technique, a plaintext is paired with a random secret key (also referred to as a one-time pad). Then, each bit or character of the plaintext is encrypted by combining it with the corresponding bit or character from the pad using modular addition. If the key is truly random, is at least as long as the plaintext, is never reused in whole or in part, and is kept completely secret, then the resulting ciphertext will be impossible to decrypt or break.

However, practical problems have prevented one-time pads from being widely used. The one-time pad has serious drawbacks in practice because it requires:

•	Truly random (as opposed to pseudorandom) one-time pad values, which is a non-trivial requirement.

•	Secure generation and exchange of the one-time pad values, which must be at least as long as the message. (The security of the one-time pad is only as secure as the security of the one-time pad exchange).

•	Careful treatment to make sure that it continues to remain secret, and is disposed of correctly preventing any reuse in whole or part—hence "one time". 

One-time pads solve few current practical problems in cryptography. High quality ciphers are widely available and their security is not considered a major worry at present.Such ciphers are almost always easier to employ than one-time pads; the amount of key material which must be properly generated and securely distributed is far smaller, and public key cryptography overcomes this problem.


<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc1.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc2.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc3.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc4.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc5.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc6.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc7.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc8.png" />
