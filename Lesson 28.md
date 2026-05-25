Section 6: Cryptography.
Lesson 4: John the Ripper Basics.

1. Introduction to John the Ripper
In this room, I learned how to use John the Ripper, one of the most popular password cracking tools used in cybersecurity. John takes password hashes or password-protected files and tries to recover the original password.
The room focused on the Jumbo version of John, which supports many more hash formats and includes helper tools such as:
- zip2john
- rar2john
- ssh2john
These tools extract hashes from protected files so that John can crack them.

2. Basic Terminology
Before using John, I learned several important terms.
- Hash
A fixed-length representation of data. Passwords are often stored as hashes instead of plain text.
- Wordlist
A file containing possible passwords that John will test.
- Cracking
The process of trying different password guesses until one matches the target hash.
- Format
The hash type being used, such as MD5, SHA256, or NTLM.

3. Installing and Verifying John
I learned how to verify that John is installed and working correctly.

4. Using Wordlists
John is most commonly used with a wordlist. The most popular wordlist is rockyou.txt, which contains millions of leaked real-world passwords.
Location in Kali Linux:
/usr/share/wordlists/rockyou.txt
If the file is compressed:
gunzip /usr/share/wordlists/rockyou.txt.gz

5. Cracking a Basic Hash
The standard workflow is:
- Save the hash into a file.
- Run John with a wordlist.
- Display the cracked password.
Example:
- echo "5f4dcc3b5aa765d61d8327deb882cf99" > hash.txt
- john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
- john --show hash.txt
In this example, John cracks the MD5 hash and reveals the password.

Task: What type of hash is hash1.txt?
Command: python3 hash-id.py < hash1.txt
Task: What is the cracked value of hash1.txt?
Command: john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt

- I have also found the type of hash and a cracked value for hash2.txt, hash3.txt, hash4.txt.

6. Specifying the Hash Format
Sometimes John cannot detect the hash type automatically.
In that case, I need to specify the format manually.
- john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
Examples of common formats:
- raw-md5
- raw-sha1
- raw-sha256
- nt 

7. Cracking Windows Password Hashes
Windows stores passwords as NTLM hashes.
To crack them:
- john --format=nt --wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt
This showed me how attackers can recover Windows passwords if they gain access to NTLM hashes.

Task: What is the cracked value of this password?
Command: john --wordlist=/usr/share/wordlists/rockyou.txt --format=nt ntlm.txt

8. Cracking Linux Password Hashes
Linux stores password hashes in /etc/shadow.
John uses the unshadow tool to combine /etc/passwd and /etc/shadow.
- unshadow passwd.txt shadow.txt > hashes.txt
- john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

Task: What is the root password?
Command: unshadow /path/to/passwd /path/to/shadow > unshadowed.txt then john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt unshadowed.txt

9. Single Crack Mode
Single Crack Mode uses information such as usernames and real names to generate targeted password guesses.
- john --single hashes.txt
This is useful because many users create passwords based on personal information.

Task: What is Joker’s password?
Command: john --single --format=raw-md5 hash07.txt

10. Custom Rules
Rules transform existing words into more realistic password guesses.
Examples:
- password → Password
- password → password123
- password → p@ssword
Command:
- john --rules --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
This significantly increases the number of guesses without needing a larger wordlist.

Task: What flag would we use to call a custom rule called THMRules?
Command: john --wordlist=/usr/share/wordlists/rockyou.txt --rule=THMRules hashfile.txt. to display cracked results: john --show hashfile.txt
11. Cracking ZIP Archives
First, extract the hash:
- zip2john secure.zip > zip.hash
Then crack it:
- john --wordlist=/usr/share/wordlists/rockyou.txt zip.hash

Task: What is the password for the secure.zip file?
Command: zip2john secure.zip > zip_hash.txt. After that, run john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt to crack the password.
Task: What is the contents of the flag inside the zip file?
Command: unzip secure.zip. Then cat flag.txt

12. Cracking RAR Archives
- rar2john secure.rar > rar.hash
- john --wordlist=/usr/share/wordlists/rockyou.txt rar.hash

Task: What is the password for the secure.rar file?
Command: rar2john secure.rar > rar_hash.txt. After that, run john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt

13. Cracking SSH Private Keys
- ssh2john id_rsa > ssh.hash
- john --wordlist=/usr/share/wordlists/rockyou.txt ssh.hash

Task: What is the SSH private key password?
Command: ssh2john id_rsa > id_rsa_hash.txt. Then john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt

This section showed me that even encrypted SSH keys can be attacked if the passphrase is weak.

- Summary
In this room, I learned how to use John the Ripper to crack password hashes and password-protected files.
I learned:
- How to use rockyou.txt
- How to specify hash formats
- How to crack NTLM and Linux hashes
- How Single Crack Mode works
- How rules generate password variations
- How to crack ZIP, RAR, and SSH files
