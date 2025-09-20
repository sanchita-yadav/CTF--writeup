# Challenge Name: EVEN RSA CAN BE BROKEN???

## Category
Crypto

## Description
In this challenge, we are provided with an encrypted flag using RSA encryption. The task is to decrypt it using the given modulus `N` and exponent `e`. The catch? The modulus `N` is even, which introduces a vulnerability in the RSA encryption.

## Approach / Steps Taken

1. **Understanding RSA Encryption**  
   RSA encryption relies on the difficulty of factoring large numbers. The public key consists of:
   - `N = p * q` (product of two primes)
   - `e` (public exponent)

   The private key `d` is computed as the modular inverse of `e` modulo `φ(N)`, where `φ(N) = (p-1) * (q-1)`.

2. **Identifying the Weakness**  
   In this challenge, `N` is even. This is a significant clue because:
   - If `N` is even, one of the prime factors must be 2.
   - Therefore, `p = 2` and `q = N / 2`.

3. **Calculating φ(N)**  
   Given that `p = 2` and `q = N / 2`, we can compute:
   - `φ(N) = (p-1) * (q-1) = 1 * (q-1) = q-1`.

4. **Computing the Private Key `d`**  
   Using the formula `d = e⁻¹ mod φ(N)`, we can compute the private key `d`.

5. **Decrypting the Ciphertext**  
   With `d` and `N`, we can decrypt the ciphertext `c` using:
   - `m = c^d mod N`

   The result `m` is the plaintext message, which is the flag.

```python
from Crypto.Util.number import inverse, long_to_bytes

# Given values
N = <provided_N>
e = 65537
c = <provided_ciphertext>

# Step 1: Calculate q
q = N // 2

# Step 2: Calculate φ(N)
phi_N = q - 1

# Step 3: Compute the private key d
d = inverse(e, phi_N)

# Step 4: Decrypt the ciphertext
m = pow(c, d, N)

# Step 5: Convert the decrypted message to bytes
flag = long_to_bytes(m)
print(flag)
