Session 6: Cryptography.
Lesson 3: Hashing Basics.

- What is hashing
Hashing takes input of any size and turns it into a fixed-size hash value. The important part is that the output is always the same size, no matter how big the input is. In the room, this is introduced with the idea of checking whether two large files are identical by comparing their hash values. If the hashes match, the files are almost certainly the same.

1. Why hashes matter
I learned that hashing is useful when you need to compare data without looking at the full content. It is used in password verification and file integrity checking, so it has two main jobs in this room, checking identity and checking if something was changed.
Task: What is the SHA256 hash of the passport.jpg file in ~/Hashing-Basics/Task-2?
Command: sha256sum ~/Hashing-Basics/Task-2/passport.jpg

2. Hash functions and collisions
A hash function takes an input and returns a fixed-length result. The room also introduces collisions, which happen when two different inputs produce the same hash value. That is one of the main limits of hashing, and it is why good hash functions are designed to make collisions very hard to find.
Task: What is the 20th password in rockyou.txt?
Command: head -n 20 /usr/share/wordlists/rockyou.txt | tail -n 1

3. Hashing in authentication
The room covers how hashing fits into login systems. Instead of storing plain text passwords, systems store hash values and compare the user’s login attempt against the stored value. That means the real password is not kept directly, which gives better protection if the database is exposed.

4. Recognising stored hashes
I learned that stored hash values can often be identified by their format and length. This matters because different hash types use different structures, and recognizing them helps you know what kind of hash you are working with before trying to analyse or crack it.

5. Cracking hash values
The room also teaches the idea of cracking hashes. That means testing guesses against the hash until one matches. This shows why weak passwords and weak hash choices are dangerous, because if the hash is easy to attack, the original password can be recovered.
Task: Use hashcat to crack the hash, $2a$06$7yoU3Ng8dHTXphAg913cyO6Bjs3K5lBnwq5FJyA6d01pMSrddr1ZG, saved in ~/Hashing-Basics/Task-6/hash1.tx
Command: hashcat -m 3200 -a 0 ~/Hashing-Basics/Task-6/hash1.txt /usr/share/wordlists/rockyou.txt
Task: Use hashcat to crack the SHA2-256 hash, 9eb7ee7f551d2f0ac684981bd1f1e2fa4a37590199636753efe614d4db30e8e1, saved in saved in ~/Hashing-Basics/Task-6/hash2.txt.
Command: hashcat -m 1400 -a 0 ~/Hashing-Basics/Task-6/hash2.txt /usr/share/wordlists/rockyou.txt
Task:Use hashcat to crack the hash, $6$GQXVvW4EuM$ehD6jWiMsfNorxy5SINsgdlxmAEl3.yif0/c3NqzGLa0P.S7KRDYjycw5bnYkF5ZtB8wQy8KnskuWQS3Yr1wQ0, saved in ~/Hashing-Basics/Task-6/hash3.txt.
Command: hashcat -m 1800 -a 0 hash3.txt /usr/share/wordlists/rockyou.txt --status --status-timer=10. To get a plaintext: hashcat --show -m 1800 hash3.txt
Task: Crack the hash, b6b0d451bbf6fed658659a9e7e5598fe, saved in ~/Hashing-Basics/Task-6/hash4.txt.
Command: hashcat -m 0 -a 0 ~/Hashing-Basics/Task-6/hash4.txt /usr/share/wordlists/rockyou.txt

6. Integrity checking
Hashing is also used to check if a file was changed. The room uses the example of comparing a downloaded file to the original version. If both hashes are equal, you can be very confident the file was not modified. That makes hashing useful for safe downloads and file verification.
Task: What is SHA256 hash of libgcrypt-1.11.0.tar.bz2 found in ~/Hashing-Basics/Task-7
Command: sha256sum ~/Hashing-Basics/Task-7/libgcrypt-1.11.0.tar.bz2

- Summary
This room gave me a clear overview of how hashing works and why it matters. I learned how hash values are formed, why collisions matter, how hashing is used in password storage, how to recognise and crack hashes, and how hashes help with file integrity checking.
