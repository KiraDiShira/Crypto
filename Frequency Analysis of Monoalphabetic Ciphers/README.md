- [Index](https://github.com/KiraDiShira/Crypto#crypto)   

# Frequency Analysis of Monoalphabetic Ciphers

- [One time pad](#one-time-pad)   
- [Single character frequency analysis](#single-character-frequency-analysis)
- [Multi-Character Frequencies](#multi-character-frequencies)

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

If our cipher is simply a generic Cesar shift cipher, we can simply look for the most frequently used letter and assume that it represents E. That will be correct far more often than not. But if that doesn't work, we could assume either that the most frequently used letter was T, or that the second most frequently used letter is E. If neither of these pans out, we can continue down a decision tree that, on average, will allow us to break the cipher much more quickly than brute force, which of course isn't that difficult either in this case.

But imagine if we can correctly guess the correct mapping for just the top six characters. We would have about half of the ciphertext deciphered, and it is very likely we would be able to then spot several places where the only possible mappings for some of the other characters would be readily apparent. Each additional character we map, not only increases the amount of plaintext that we can leverage, but reduces the possible choices for the remaining characters. The other end of the distribution can also be quite helpful. The least frequently used third, or nine characters, only account for 7.5% of all characters, and the bottom six account for only 2%. If we can identify most of these, at least as a group, then that significantly reduces the number of choices for the remaining unknown characters. At this point you might be thinking that breaking a random monoalphabetic cipher is trivially easy, just map the letter frequencies of the ciphertext to the plaintext. Unfortunately, this is seldom the case.

<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc2.png" />

First, keep in mind the statistical nature of the letter frequencies and how they vary from subject area and author among other factors. Further, ciphertext tend to be fairly short, for instance the procedure for enigma prohibited messages longer than 250 characters, and many messages were well under 100. As with most things, the less data you have the more it will tend to deviate from the average. Furthermore, it is quite common for the originator of the ciphertext to modify the plaintext to make it even shorter, not unlike people today do when they're texting, which not only introduces a lot of unfamiliar and seemingly random letter sequences into the plaintext, but it also distorts the letter frequency distribution of an already very small sample of material. Even if you have perfectly recovered the plaintext it might not be immediately obvious. Consider the following 250 character intercept. Is this plaintext or is it ciphertext?

This is from Moby Dick by Herman Melville. I extracted this from a public domain copy of the work and generated a plaintext file by only keeping the letters, converted to uppercase, and placing them in groups of five, with ten groups per line.This or something similar was quite common practice, so as to remove spaces, punctuation, and other cues that are extremely helpful to a cryptanalyst.

But other important non-letter content was converted into letter equivalence, such as using an uncommon letter for a question mark, which distorts the frequency distribution, or spelling out numbers. We'll ignore this purely for the sake of convenience, but it gives a glimpse into the fact that in enciphering messages involves quite a bit of pre and post processing on the part of the operators.

It's plaintext:

<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc3.png" />

## Multi-Character Frequencies

<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc4.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc5.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc6.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc7.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/Frequency%20Analysis%20of%20Monoalphabetic%20Ciphers/Images/famc8.png" />
