# 🔒 Cryptic Shadows CTF Challenge

A multi-layered cryptography challenge designed for intermediate CTF participants. Follow the trail of encrypted messages left by the rogue agent "Specter" to recover the Obsidian Key.

## 📋 Challenge Description

**Category:** Cryptography  
**Difficulty:** Intermediate  
**Estimated Time:** 30-60 minutes  
**Required Skills:** Basic cryptographic knowledge, logical thinking, pattern recognition

## 🎯 Challenge Overview

You are an agent of the secretive organization "Shadow Cipher," tasked with recovering a lost artifact known as the "Obsidian Key." The key is locked in a digital vault protected by a series of cryptographic puzzles. A rogue agent, codenamed "Specter," has left behind encrypted messages to taunt you.

Your mission is to:
1. Decrypt the initial message to find the hidden file
2. Decode the binary data to uncover the next clue
3. Solve the final vault puzzle to retrieve the flag

## 🧩 Challenge Structure

### Layer 1: The Ciphered Note
- **Ciphertext:** `LOENSUAZIQHDWMIOS`
- **Hint:** "The key lies in the shadows of the first word, repeated like an echo."
- **Solution:** Vigenère cipher with key "SHADOW" derived from challenge name

### Layer 2: The Hidden File
- **Data:** Binary string encoding "V"
- **Hint:** "Look beyond the greeting; the shadow hides in the base."
- **Solution:** Binary to ASCII conversion

### Layer 3: The Final Vault
- **Ciphertext:** `VAOZMNCVYJRN`
- **Hint:** "Use the key from the previous layer to unlock this cipher."
- **Solution:** Vigenère cipher with key "V" from Layer 2

## 🏆 Flag Format

The final flag follows standard CTF format: `flag{AFTERSHADOWS}`

---

*Good luck, agent. The shadows are watching... - Specter* 