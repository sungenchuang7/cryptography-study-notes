# Cryptography
> The study of "secrets" 

# Goal
> To hide plain text 

Flow: 
```
plain text --- (publicly available encryption algo + privately secured key (+ salt)) ---> cipher text
``` 

* salt: value to enhance the randomness of a one-way function

## Three Classes of Mathematical Algorithms 
### Digital Signature: 
> An asymmetric key function that verifies the authenticity of a message coming from a remote party. 

By signing the message with a private key, using the public key to decrpyt the message confirms that the sender is who they say they are.

### Encryption
> Encryption in any form is a way of taking plain text and converting it to a cipher text, which with the correct pieces of data, can be converted back into plain text at later point. Basically,  using a ***two-way math function to mask data***.

Encrpytion can be accomplished using a ***single shared key***, or an ***asymmetric key pair***. 

### Hashing (Cryptogrpahic Hashing)
> One-way mathematical function to map data

Hashing allows you to map an arbitrary-sized set of bytes into a finite-size of relatively unique set of bytes. 



