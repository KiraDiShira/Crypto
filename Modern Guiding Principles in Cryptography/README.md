- [Index](https://github.com/KiraDiShira/Crypto#crypto)   

# Modern Guiding Principles in Cryptography

- [Codes vs chiphers](#codes-vs-chiphers)   
- [Transposition vs substitution](#transposition-vs-substitution)
- [Monoalphabetic vs polyalphabetic](#monoalphabetic-vs-polyalphabetic)
- [Cryptanalysis](#cryptanalysis)

## Codes vs chiphers

Kerckhoffs' Principle states that a cryptosystem should remain secure, even if the adversary knows every detail of the system, except the key. This underscores the need to safeguard the security of the key, which opens its own Pandora's box of complications. Included in this is the *key distribution problem*, the resulting desirability of public key cryptosystems and the need and role for trusted third parties. One thing that is frequently overlooked, often with disastrous consequences, are how human factors impact the practical security of a cryptosystem.

*1883 – Auguste **Kerckhoffs’ design principles**
•  System should not have complex rules 

• Algorithms shouldn’t need to be secret 

• Security should rely on simple keys

One thing that Kerckhoffs didn't directly address, most likely because in his time cyphers were used on very small scales compared to what became commonplace in the 20th century with the advent of industrial scale cryptography, is know as the **key distribution problem**. This problem reflects the difficulty of generating sufficient key material, securely distributing it to the parties that need it, and being able to detect when and if there's been a compromise.
 
 Let's consider how the number of keys needed grows as the scope of a cryptosystem grows. If you have end users, then the greatest security is achieved if each pair of users has a unique key. A strong advantage of using such pairwise keys is that if a key is compromised, it only endangers the traffic between that pair of individuals,.although this could be parlayed into additional key breaches. Because the benefit to the enemy of compromising one key is minimal, the resources that they're likely to put into the effort is likewise probably going to be limited. But this only true if it is feasible to properly manage all of the keys.
 
With N participants each needing N- 1 keys to communicate with the other people, the total number of keys that you need is on the order of N squared. If you have a small team of operatives, say 10, then you only need about 50 keys, and this is not too unreasonable. But today we need to secure communication networks that have literally millions of users, some human and some not, such as communication relays and in-place sensor networks.
 
For the best security, you would want every pair of users to have their own key, but 1 million users would require 1 trillion keys. And then somehow you would need to distribute 1 million of these keys to each of 1 million users. This is completely unmanageable, and 1 million nodes is small compared to something the scope of the global information grid. An alternative is to have large groups of users share a common key, to reduce the total number of keys to a manageable level. The problem here is that the the larger the group, the more valuable a key compromise becomes to your adversary, and hence the greater the resources they may commit to the effort.
 
This is an addition to the fact that just having the key known to a larger group of people, increases the likelihood that someone is going to get careless and exposed the key.
 
Furthermore, it becomes increasing likely that any bridge that does happen, will not be detected by the other users, who will continue using the compromised key. About the only thing worse than your key becoming known to your enemy is for you not to know that it has.
 
No one has yet devised a truly practical and scalable solution to the key distribution problem. But in the mid 1970s, a revolutionary alternative was developed. The basic idea stems from asking whether it was possible to use secrets that didn't have to be shared. Something that had previously not even been considered, since its absurdity would have seemed obvious. It was taken as a given that secret communications relied on shared secrets, now known as symmetric keys. But let's rephrase the question slightly as two separate questions. First, is it possible to use two different but related keys, such that two people can communicate securely as long as each one has one of the keys? This is what is known as asymmetric cryptography. Second, if this is possible, we then ask, is it possible to make one of the keys public knowledge without compromising the other key? If this has a solution, then Alice can generate both keys, keep one all to herself and publish the other for Bob to look up, as can even Mallory and everyone else. As the saying goes, if you want to keep something a secret, never tell anyone. If two people know a secret, then it's no longer a secret. This is known as public key cryptography, and it's become perhaps the most single critical component in today's vibrant online economy.

On one level this would seem to trivially solve the key distribution problem. Alice can publish her public key in as many ways that she wants, and Bob only needs to be able to find one of them. But there's a really big catch, how does Bob know that the key he finds is really Alice's public key? Perhaps Mallory made up a pair of keys and published one of those in Alice's name. Bob has to be able to trust that the key he looks up really is the one published by Alice.
Whether we are talking about symmetric or asymmetric cryptography, nearly any practical cryptosystem that operates on any meaningful scale currently uses some form of trusted third party. The role of the trusted third party, usually named Trent in our cast of characters, varies depending on the system.


