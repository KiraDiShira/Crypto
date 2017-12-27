- [Index](https://github.com/KiraDiShira/Crypto#crypto)   

# Key length determination in polyalphabetic ciphers

- [Codes vs chiphers](#codes-vs-chiphers)   
- [Transposition vs substitution](#transposition-vs-substitution)
- [Monoalphabetic vs polyalphabetic](#monoalphabetic-vs-polyalphabetic)
- [Cryptanalysis](#cryptanalysis)

## Codes vs chiphers

In the early 16th century, Johans Trithemius published the **Tabula Recta** and which is nothing more than a tabulation of all the possible Caesar shift ciphers one after another. A few decades later, Giovan Battista Bellaso devised an elegant implementation of a polyalphabetic cipher based on the Tabula Recta that today is known as the Vigenère cipher.
A previously agreed upon key phrase, such as secret, is written out. We'll use five letter groups above the plaintext message, which we'll use *retreat to river*. Since this key phrase is typically short compared to the message, it is simply repeated as many times as needed to match the length of the plaintext. We then go through the message one character at a time and use the character in the key to choose one of the Caesar shift ciphers by simply selecting the row that starts with that character. Next we select the column that is headed by the plaintext character. The ciphertext character is the character at the intersection of this row and column.

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc1.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc2.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc3.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc4.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc5.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc6.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc7.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc8.png" />
<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc9.png" />
