# Glossary

## Public-Private Key Pair
* In asymmetric encryption, a private key and a public key are generated at the same time as a pair and are mathematically linked. 
* The pulic key is derived from the private key using a one-way function. 
* It's easy to compute the public key from the private key, but difficult to derive the private key from the public key. 
### Private Key
* Kept confidential by its owner
* Used for ***signing*** a ***digital signature***
* Used for ***decrypting*** data encryped using its corresponding public key

### Public Key 
* Made publicly available
* Used for ***verifying*** a ***digital signature*** signed using its corresponding private key
* Used for ***encrypting*** data that can only be decrypted by the corresponding private key.

## Digital Certificate
* Serves to verify the ownership of a public key. 
* Issued by a trusted third party known as a Certificate Authority (CA)
* Contains the ***public key***, info about the identiy of the ***key holder***, and ***digital signature*** of the ***CA***.

## Digital Signature
* A math scheme used to demonstrate the authenticity of a digital message or document
* Created by using the sender's private key to encrypt a hash of the message 
* The recipient can use the sender's public key to decrypt the hash. 
* If the decrypted hash matches a new hash computed from the received message, it verifies that the message has not been altered (***integrity***) and that it was sent by the owner of the private key (***authenticity***). 
* Normally, a digital signature is a package containing the following items: 
    * **The Encrypted Hash**: This is the core "signature value" created by using the signer's private key.
    * **Algorithm Identifiers**: Metadata that specifies the exact hashing and encryption algorithms used.
    * **The Signer's Certificate**: the signer's public certificate, which ocntains their public key. This is needed to decrypt the hash. 
    * **The Certificate Chain** (optional): Often, the certificates of the intermediate Certificate Authorities (CAs) are also included. This helps the verifier easily trace the signer's certificate back to a trusted root authority.  

## Public-Private Key Encryption Use Cases
Public-private key encryption can be used in two ways (shown below). Note that the first use case is using the public key to encrypt and private to decrypt and the second use case is doing it the other way around (using the private key to encrypt and public key to decrypt). 
### For Confidentiality (Keeping Data Secret)
* If Alice wants to send Bob a message and only wants Bob to read it, not anyone else, Alice can encrypt the message using Bob's public key. 
* Suppose Cindy also has Bob's public key. However, Alice's encrypted message can only be decrypted using Bob's private key. 
* Public-private key encryption is a one way street. 

### For Authentication 
* Suppose Alice wants to send a legal contract to Bob. Upon receiving the contract, Bob needs to verify two things:
1) ***Authenticity***: The contract really came from Alice.
2) ***Integrity***: The contract wasn't altered in any way after Alice sent it.
* To convince Bob of the above, Alice will:
1) Use a hashing algorithm to generate a ***fixed-size hash*** of the original contract (= the ***fingerprint*** of the message) 
2) Use her private key to encrypt the hash. This is the ***digital signature*** of Alice. 
3) Send both the digital signature and the original contract to Bob
* Upon receiving the stuff sent by Alice, Bob will: 
1) Descrypt Alice's digital signature using Alice's public key. The result is the original hash Alice created. 
2) Take the plain-text message and runs it through the same hashing algorithm that Alice used. This generates a new hash. 
3) If this new hash is the same as the original hash Alice created, the message hasn't been altered. 