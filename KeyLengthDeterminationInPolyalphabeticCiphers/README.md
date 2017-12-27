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

When received, this process is simply reversed.

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc2.png" />

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc3.png" />

But most of the time, the key was a word or short phrase that was considerably shorter than the message. But this was sufficient to significantly soften the ciphertext letter frequencies and render simple frequency analysis ineffective. So how might we crack this cipher?

The answer was arrived at independently, and by slightly different methods, by both Charles Babbage and Friedrich Kasiski in the mid-19th century. Both men observed that if the length of the key could be determined, then the ciphertext could be broken up into sets of ciphertext characters that had been encrypted with the same key. While successful encryption of each set would obviously not result in meaningful text, the fact that they all had the plaintext characters in the set had been encrypted using the same key meant they were encrypted with the same monoalphabetic cipher. And in the case of the Vigenere cipher, this was a simple Caesar shift cipher. This meant that they would exhibit the same frequency distribution as the underlying plaintext. This insight by itself would have been sufficient to afford a considerable break into the cipher, but both men went a major step forward and found a way to determine the length of the key in a very efficient way. Both methods look at coincidences, which are letters or sequences of letters that appear at regular intervals in the ciphertext. We'll look at one of these methods, Babbage's Index of Coincidence, and leave the other, the Kasiski Examination, for your own exploration.

The Index of Coincidence is a measure of how frequently you expect to find coincidental matches between two unrelated strings of text written in the same language, using the same alphabet laid one on top of the other.

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc4.png" />

To see how this can help us, let's see what we would expect the rate to be. For illustration purposes, we'll start with a simple language that has just two characters, A and B, in which A has a frequency of 75%, and B, 25%. Here are two 32-character plaintext messages written in this language with the coincidences indicated by an overbar. We see that we have 16 coincidences with A, and three with B, giving a total coincidence rate of 59%. But is this close to what we expect? Let's look at what the math tells us.

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc5.png" />

But is this close to what we expect?

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc6.png" />

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc7.png" />

Recall that we are interested in detecting when our two sets of characters are drawn from the same alphabet, or when f and g are the same. In this case, our equation reduces to simply the sum of the squares of the single letter frequencies. For English, this rate is generally accepted as being 6.65%. For the frequencies we previously established from that huge set of works, we got 6.85%, which is in pretty good agreement.

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc8.png" />

Coincidence rates are very useful, and in practice this is what we generally use. But in order to compare rates for different languages, having alphabets of different sizes, it is useful to normalize the expected coincidence rate by dividing it by the coincidence rate for a uniformly used alphabet of that same size. This is what the actual index of coincidence refers to. For English, this works out to about 1.73. 

<img src="https://github.com/KiraDiShira/Crypto/blob/master/KeyLengthDeterminationInPolyalphabeticCiphers/Images/kldipc9.png" />

Although not readily apparent, it is not too difficult to reason out that the expected coincidence rate will be greatest when the letters in each pair are drawn from the same alphabet. This is the critical observation that lets us find the key length. If we count the coincidences between the ciphertext and a copy of the ciphertext that has been shifted by k places, then when k is a multiple of the key length, each pair of letters are drawn from the same alphabet. And we expect to see a spike in the coincidence rate. Because of statistical variation, it will not be too surprising so see spikes at other shift amounts, but we would not expect to see these spikes at every multiple of that shift.
