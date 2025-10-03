# Cryptography & Cryptanalysis 🔐

**Cryptography** focuses on techniques for encrypting and decrypting information, while **Cryptanalysis** studies methods for breaking or bypassing those protections.

---

## Importance & Applications 🌍
- **Communication Security:** Ensures confidentiality and integrity of internet communications.  
- **Data Storage Security:** Encrypts sensitive stored data.  
- **Authentication:** Digital signatures and certificates verify identities.  
- **Financial Transactions:** Secures online banking and e-commerce.  
- **Government & Military:** Protects classified and sensitive information.

---

## Core Difference — Cryptography vs Cryptanalysis 🔁
- **Cryptography:** The builder — designs algorithms and systems to secure data (the lock).  
- **Cryptanalysis:** The breaker — analyzes and tries to find weaknesses or keys to unlock the system.

---

## Kerckhoffs’ Principle 🔑
Security should rely on the secrecy of the **key**, not the secrecy of the algorithm. Assume attackers know the algorithm.

---

## Symmetric vs Asymmetric Encryption ⚖️

### Symmetric (Fast)
- Uses a **single shared key** for encryption and decryption.  
- Very fast — ideal for encrypting large amounts of data.  
- Main challenge: secure key distribution.

**Example:** AES — the current standard for symmetric encryption.

### Asymmetric (Public-Key) (Slow but Functional)
- Uses a **pair of keys**: public (encrypt) and private (decrypt).  
- Slower, but solves key distribution and supports digital signatures (authentication).

**Common usage:** Use asymmetric encryption to securely exchange a symmetric session key, then use symmetric encryption for bulk data.

**RSA vs ECC**
- **RSA:** Older, widely used, requires larger keys.  
- **ECC:** Newer, provides similar security with shorter keys — useful for constrained devices.

---

## Common Attacks ⚠️
- **Brute Force:** Trying all possible keys — infeasible if keys are long enough.  
- **Side-Channel Attacks:** Exploit implementation leaks (timing, power, electromagnetic) rather than the algorithm itself.

---

## Modes of Operation (Symmetric) 🔄
- **ECB:** Not recommended — leaks patterns (encrypts blocks independently).  
- **CBC, CTR, GCM, etc.:** Provide randomness, integrity, or parallelism — prefer these over ECB.

---

## Practical Notes
- Symmetric encryption = speed; asymmetric = key exchange & identity.  
- Protect private keys at all costs — they are the root of trust for signatures.  
- PKI (Public Key Infrastructure) and CAs (Certificate Authorities) bind public keys to identities.

---

## Hash Functions — Digital Fingerprints 🛡️
- **What:** Hash produces a fixed-size digest (fingerprint) for arbitrary input.  
- **One-way:** You cannot derive the original input from the hash.  
- **Avalanche effect:** Small change in input produces a completely different hash.  
- **Common standards:** SHA-2 family (e.g., SHA-256) — recommended.  
- **Avoid:** MD5 and SHA-1 (vulnerable to collisions).

### Uses of Hashes
- Password storage (with salts and proper key derivation).  
- Data integrity checks (compare file hashes).  
- Part of digital signature processes (sign the hash, not the full data).

---

## Typical Real-World Pattern 🔁
1. Use **asymmetric crypto** to authenticate and exchange a symmetric session key.  
2. Use **symmetric crypto** (AES, etc.) for fast bulk encryption.  
3. Use **hashes** for integrity checks and part of signatures.

---

## Suggested Topics to Add Later ✅
- Example: key exchange (Diffie–Hellman) and TLS handshake overview.  
- Short demo: AES encryption and comparing CBC vs CTR.  
- Short demo: RSA signing and verification.  
- Common cryptographic libraries and safe usage (e.g., libsodium, OpenSSL best practices).

