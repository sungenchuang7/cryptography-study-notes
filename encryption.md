# Encryption

## What Is Encryption? 
* Process by which plain text data becomes hidden 
* Ciphered data becomes difficult, hopefully impossible, to read without the ***key*** that was used to generate the ciphered text. 
* Therefore, only authorized parties can decrypt 

## Goals of Encryption
* **Confidentiality** (= privacy):
> The message I send you is only readable by you, assuming that two of us share an algo and some sort of key parlance between us. 
* **Integrity**: 
> What you send me has not been modified by a bad actor. 
* **Authentication**:
> You are who you say you are .
* **Nonrepudiation**:
> Prove a message came from who you believe sent it &rarr; the goal of ***digital signatures***

## Types of Encryption
### Symmetric Encryption (Shared Key Encryption)
> Both parties involved ***share a common key***. The shared key must be ***kept secret*** by ***both parties***. 
* Example: Alice encrypts a message using a shared key with Bob and sends the encrypted message to Bob. Bob can then decrypt the message using the same key. 
* Cons: Both parties need to keep the shared key secure. 

### Asymmetric Encrpytion (Public/Private Key Encryption)
> Uses public/private key pair. Public and private keys are ***mathematically related***. 
* Example: Alice creates a public key and a private key. She shares her ***public key*** to ***everyone***. She ***encrypts*** her message with the ***private key*** and sends it to Bob. Bob descrypts the message using Alice's ***public key*** to get plain text. If Bob wants to send a private message to Alice, Bob can use Alice's ***public key*** to encrypt the message and Alice can decrypt it using her own ***private key***. 
* Asymmetric encryption works ***both ways***. 
* Use cases: 
    * TLS
    * Digital signatures
    * Certificate trusts

### Performance Considerations 
* Shared key is faster than PKI (asymmetric). 
* Usually PKI is used solely to transfer a shared key: ***TLS*** 