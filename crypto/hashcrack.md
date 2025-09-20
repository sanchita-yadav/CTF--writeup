# Challenge Name: hashcrack

## Category
Crypto

## Description
In this challenge, we are provided with several hashed strings. The task is to identify the hash types and then crack them to reveal the original plaintext values.

## Approach / Steps Taken

1. **Identify the Hash Type**  
   The first step is to determine the type of each hash. This can be achieved using online tools such as [hashes.com](https://hashes.com/en/tools/hash_identifier).

   - For the given hash `482c811da5d5b4bc6d497ffa98491e38`, the tool identified it as an **MD5** hash.

2. **Crack the Hash**  
   Once the hash type is identified, the next step is to crack it. Online services like [decode.fr](https://www.decode.fr/) can be used to find the plaintext corresponding to the hash.

   - Inputting the MD5 hash `482c811da5d5b4bc6d497ffa98491e38` into decode.fr yields the plaintext: `password123`.

3. **Repeat for Other Hashes**  
   Similarly, the other hashes are processed:

   - `b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3`: Identified as **SHA-1**, cracked to `letmein`.
   - `qwerty098`: Identified as **SHA-256**, cracked to `qwerty098`.
