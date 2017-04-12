---
title:      "Neural Cryptography"
---
### Protocol to exchange key
[Github link](https://github.com/exced/neural-crypto)

Here is my [report](https://github.com/exced/neural-crypto/blob/master/neural-crypto.pdf) on this subject. It well summarizes the situation and the strengths of this algorithm.



Otherwise... Here is a quick description

I recently read a [Wikipedia page](https://en.wikipedia.org/wiki/Neural_cryptography) about neural cryptography so I
decided to implement my version.

The purpose is to build a protocol that is not based on any number theory.
> Algorithm that are not based on any of these number theory problems are being searched because of this property.

### How does it work ?

The scenario is : Alice want to secretly send messages to Bob. Eve is listening to the messages as Man-In-The-Middle.
First answer is probably to work with asymmetric keys such RSA.

But if we had a way to secretly send our key to Bob we could then do symmetric encryption.

Sending a secret key is quiet impossible but we can work together to build the same key (Alice and Bob).
This algorithm is based on synchronization of 2 neural nets.

Alice and Bob build try to build the same neural nets and then use the weight matrix as key.

![Tree Parity Machine](https://upload.wikimedia.org/wikipedia/commons/4/42/Tree_Parity_Machine.jpg)

### Security against quantum computers

Some folks probably think that quantum computers will break every cryptographic communication...
But the fact is that if we use optical fiber to communicate with another quantum computer we can actually know if
someone is listening as the bits would change ([see wikipedia Quantum_computing](https://en.wikipedia.org/wiki/Quantum_computing)) and so
use *one time pads* (Vernam cryptographic protocol).
It works well as quantum physics give us the properties of real randomness.

The only problem remains in the optical fiber. Because we need these communications everywhere.

There neural-cryptography algorithm might be good.



