Section 6: Cryptography.
Lesson 2: Public key cryptography basics.

- Public and private keys
This room goes deeper into asymmetric encryption. It showed how one public key can be shared with everyone, while the private key stays protected. The public key is used to encrypt or verify, and the private key is used to decrypt or sign.

- Why it matters
Public key cryptography solves the problem of securely sharing secrets over an unsafe network. It is the base for secure communication, trusted connections, and identity verification.

- RSA
RSA is one of the main public key algorithms. It relies on large prime numbers and the difficulty of factoring them. It can be used for encryption and digital signatures.

- Diffie-Hellman
Diffie-Hellman lets two people create the same shared secret without sending the secret directly. That shared secret can then be used for symmetric encryption.

- SSH and certificates
SSH uses key pairs for secure login. Certificates are used in TLS to prove identity and help browsers trust a site.
Task: Check the SSH Private Key in ~/Public-Crypto-Basics/Task-5. What algorithm does the key use?
Command: ssh-keygen -lf ~/Public-Crypto-Basics/Task-5/id_rsa

- PGP and GPG
I also learned about PGP and GPG for secure file and message protection. They use public and private keys to encrypt data and verify who sent it.
Task: Use GPG to decrypt the message in ~/Public-Crypto-Basics/Task-7. What secret word does the message hold?
Commands: gpg --import tryhackme.key to import the GPG key. gpg --decrypt message.gpg to decrypt the message and reveal the secret word.

- Summary
This room explained how public key cryptography works in practice. I learned RSA, Diffie-Hellman, SSH, certificates, and PGP/GPG, and how they are used to build trust and secure communication.
