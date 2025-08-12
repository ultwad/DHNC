# DHNC
Dynamic Homophonic Noise Cipher (DHNC)
## Overview
DHNC is a custom encryption algorithm that uses a dynamic set of secret special tokens, cycling terminators, and random noise injection to encrypt plaintext messages. The design enhances security through obfuscation and homophonic substitution, while keeping the key exchange secure using public key cryptography.

## Features
- Randomly generated secret special tokens per session
- Fixed, publicly known cycling terminators marking letter boundaries
- Noise tokens to confuse attackers and resist frequency analysis
- Secure key exchange of special tokens using public key cryptography
- Simple single-letter token encryption for natural ciphertext appearance

## How it works
1. The sender and receiver agree on a fixed sequence of terminator tokens.
2. The sender randomly partitions the alphabet into special tokens and noise tokens.
3. The special tokens are encrypted using the receiver’s public key and sent securely.
4. The sender encrypts the plaintext by:
   - Sending a number of special tokens equal to the letter's alphabetical position.
   - Following them with the current terminator token.
   - Sprinkling noise tokens randomly.
5. The receiver decrypts the special token set using their private key, then:
   - Counts special tokens until each terminator.
   - Converts counts back to plaintext letters.

## Getting Started

### Prerequisites
  - Python 3.x
  - (Optional) Cryptography libraries for public key encryption (e.g., `cryptography` or `PyCryptodome`)

### Installation
- Clone the repository:
```bash
  git clone https://github.com/ultwad/DHNC.git
  cd DHNC
