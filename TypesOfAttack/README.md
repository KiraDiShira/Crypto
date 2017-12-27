- [Index](https://github.com/KiraDiShira/Crypto#crypto)   

# Types of attack

- [Attacks on encryption schemes](#attacks-on-encryption-schemes)   
- [Side-channel attacks](#side-channel-attacks)
- [Social engineering](#social-engineering)

## Attacks on encryption schemes

The objective of the following attacks is to systematically recover plaintext from ciphertext, or even more drastically, to deduce the decryption key

1. A **ciphertext-only attack** is one where the adversary (or cryptanalyst) tries to deduce the decryption key or plaintext by only observing ciphertext. Any encryption scheme vulnerable to this type of attack is considered to be completely insecure.

2. A **known-plaintext attack** is one where the adversary has a quantity of plaintext and corresponding ciphertext. This type of attack is typically only marginally more difficult to mount.

3. A **chosen-plaintext attack** is one where the adversary chooses plaintext and is then given corresponding ciphertext. Subsequently, the adversary uses any information deduced in order to recover plaintext corresponding to previously unseen ciphertext.

4. An **adaptive chosen-plaintext attack** is a chosen-plaintext attack wherein the choice of plaintext may depend on the ciphertext received from previous requests.

5. A **chosen-ciphertext attack** is one where the adversary selects the ciphertext and is then given the corresponding plaintext. One way to mount such an attack is for the adversary to gain access to the equipment used for decryption (but not the decryption key, which may be securely embedded in the equipment). The objective is then to be able, without access to such equipment, to deduce the plaintext from (different) ciphertext.

## Side-channel attacks

A **side-channel attack** is any attack based on information gained from the physical implementation of a cryptosystem, rather than brute force or theoretical weaknesses in the algorithms (compare cryptanalysis). For example, timing information, power consumption, electromagnetic leaks or even sound can provide an extra source of information, which can be exploited to break the system. Some side-channel attacks require technical knowledge of the internal operation of the system on which the cryptography is implemented, although others such as differential power analysis are effective as black-box attacks. Many powerful side-channel attacks are based on statistical methods pioneered by Paul Kocher.

## Social engineering

**Social engineering** refers to psychological manipulation of people into performing actions or divulging confidential information. 

For example, even in fairly small groups of users, at least a few people will use common passwords. Wireless networks are penetrated all the time because the person that set them up never changed the default password. Another example has an attacker calling an employee claiming to be from the IT Department and requesting the person's username and password so they can perform some critical piece of maintenance in order to permit all of the person's data from being permanently deleted. We all know that we should never just click a link in an email even if it appears to come from someone we know. Yet countless people do that every single day because the email appeared to be from someone they knew and therefore, trusted not to send them anything evil. Attackers can always count on enough people looking for something free to give them the in that they need. It might be an email informing them that they've just won an all-expense cruise. Just click here to claim your prize. 
