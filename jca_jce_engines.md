# Java Cryptography Architecture (JCA) 
* Provides a standard API
* Designed to allow JRE providers to create their own implementation
* Provides standard engine API definitions for supported operations

Devs use JCA functions to write code. Only during runtime, the actual implementation of those JCA functions are supplemented. Devs JRE can have more than 1 provider providing the implementations of those functions. 

# Java Cryptography Extension (JCE)
> The JCE is the most common provider 

* JCE is the default provider for Oracle Java. 
* Out of the box with JDK. 
* Provides implementation for every engine. 

However, JCE does ***not*** support ***every*** algorithm and variation. Developers might need to use third-party providers for implementation of certain functions. 

# Overview of Key JCA Engine Classes
The following engines are important Java classes.
## Secure Random 
* An engine to create cryptographically strong random numbers
* Different than `java.lang.Random`, which is usually not secure enough for cryptographic functions. 
* Requirement for good crypto operations. 

## Message Digest
* An engine to produce cryptographically secure hashes
* A hash == a digest == one-way operation that takes a variable sized input and outputs a fix-sized output. 

A good hash function will have very few collisions over a very large input set. 

## Signature
* An engine to create and validate digital signatures. 
* Combination of ***hash*** and ***PKI asymmetric encryption***. 
* Very useful in identity cases 

Signature engine takes ***both*** a hash and a public key encryption asymmetric operation to create a unique value or a signature. The signature can be verified to produce a hash that is equal to the original based on a decryption operation. 

## Cipher
* Engine to provide encryption
* Asymmetric and symmetric encryption support
* Supports both stream and block ciphers

Block ciphers require standard-sized input so padding can be required. 

## Stores
* KeyStore: stores ***keys***
* TrustStore: stores ***certificates***
* keytool: most often used for working with the above


