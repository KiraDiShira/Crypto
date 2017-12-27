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

## Single character frequency analysis

Imagine that Alice constructs a plaintext message that is nothing but a sequence of truly random characters, and transmits that to Bob with no encryption. Eve intercepts it, and thinking that it must be ciphertext, tries to cryptanalyze it. Not surprisingly, she'll fail to do so. In fact, it might as well be the ciphertext associated with a one-time pad, which we know is an unbreakable cipher, the only unbreakable cipher. So why are all other ciphers, at least in theory, breakable? It's all about randomness, and the lack thereof.

Unless the specific goal is the transmitter random sequence of characters, which occasionally it is, the plaintext message is always highly non-random, because information requires structure to communicate. In fact later, when we look at information theory, we'll see that the very notion of information and randomness are intimately linked. If our ciphering algorithm leaves some or all of this structure, intact within the ciphertext, then an adversary has a lot to work from. In the case of a monoalphabetic cipher, none of the structure of the plaintext is removed. We are simply using a different alphabet.

So how can Eve exploit this structure to break a monoalphabetic cipher? By noting that we use symbols in our alphabet in highly non-random ways. Some letters we used much more frequently than others. In addition, some letter combinations are very common while others almost never occur. The cryptanalyst first make an assumption about the nature of the plaintext, primarily what language it is written in, and what the general type of content it contains. They then build a statistical model of how the characters in a language would be expected to appear in a typical piece of plaintext. Then they examine how that model would be transformed during the encryption process, and how they might identify its traces in the ciphertext. In the case of a monoalphabetic cipher, this is extremely straight forward, which is why we start with it.

Let's consider single character frequency analysis. Here is the more or less standard table of overall frequency usage of the 26 characters in the English language:

<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc1.png" />



<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc2.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc3.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc4.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc5.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc6.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc7.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc8.png" />
