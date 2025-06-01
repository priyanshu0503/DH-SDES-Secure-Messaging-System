# SecureChat-CSC487: Diffie-Hellman Key Exchange with SDES Encryption

## Overview

This project demonstrates a secure communication protocol between a client and a server using **Diffie-Hellman Key Exchange** for shared key generation and **Simplified DES (SDES)** for encryption and decryption. Built using **C and socket programming**, this system enables encrypted message transmission over a network.

Developed as part of **CSC 487 - Computer Security**, the system highlights fundamental principles of cryptography and secure network communication.

## Team Members

* Taitlyn Gowlovech
* Linnet Mathiu
* Priyanshu Mittal

Credits to Fourney's example on sockets in C for foundational networking structure.

---

## Features

* Secure key generation using Diffie-Hellman protocol.
* SDES encryption for character-based message security.
* Socket-based communication between client and server.
* Manual private key input for interactive demo.

---

## File Descriptions

| File                  | Description                                                                                                |
| --------------------- | ---------------------------------------------------------------------------------------------------------- |
| `client.c`            | Connects to server, receives DH parameters, computes shared key, encrypts message with SDES, and sends it. |
| `server.c`            | Listens for client, generates DH parameters, computes shared key, decrypts received message using SDES.    |
| `SDES.c`              | Contains SDES logic: key generation, permutation, encryption, decryption, S-box operations.                |
| `SDES.h`              | Header file for `SDES.c`. Contains function declarations and shared constants.                             |
| `mod_exp_algorithm.c` | Implements fast modular exponentiation for DH calculations.                                                |
| `mod_exp_algorithm.h` | Header for modular exponentiation functions.                                                               |
| `primes.txt`          | List of prime numbers and primitive roots used for generating DH parameters. Format: `prime generator`.    |

---

## Compilation & Execution

### 1. Compile the Server:

```bash
gcc -o SERVER_ server.c SDES.c mod_exp_algorithm.c
./SERVER_
```

### 2. Compile the Client:

```bash
gcc -o CLIENT_ client.c SDES.c mod_exp_algorithm.c
./CLIENT_
```

> Note: Ensure IP address in `client.c` matches the server's IP.

---

## Usage Notes

* Run the **server first**. It will wait for the client to connect.
* Client connects, performs key exchange, and sends an encrypted message.
* The server decrypts and displays the message.
* Communication is **one-way**: client to server.
* Port number (8439) must match on both client and server.
* All files must reside in the **same directory**.

---

## Suggestions for Improvement

* Add bidirectional messaging (server replies to client).
* Include command-line arguments for IP and port.
* Improve error handling for message format and buffer overflow.
* Option to auto-generate or securely generate private keys.

---

## Known Limitations

* Only supports one client connection at a time.
* Binary handling is basic and can break with malformed input.
* Manual private key entry slows automation or bulk testing.

---

## Contact

For any questions or improvements, feel free to reach out to the project members.

---

\* This project was submitted as coursework for CSC 487 at South Dakota State University, Fall 2024.
