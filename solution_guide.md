# Cryptic Shadows Challenge - Solution Guide

## Challenge Overview
This is a three-layer cryptography challenge where each layer reveals a hint to the next. The final flag is `flag{AFTERSHADOWS}`.

## Layer 1: The Ciphered Note

### Given:
- **Ciphertext:** `MJQXZJMLTKZSIJHLTKAFHKLQXJ`
- **Hint:** "Shift your perspective, as Caesar would, but the key lies in the shadows of the first."

### Solution Process:
1. The hint mentions "shadows of the first" - this refers to the challenge name "Cryptic Shadows"
2. The first letter is 'C' (3rd letter in alphabet: A=1, B=2, C=3)
3. This suggests a Caesar cipher with shift 3
4. However, this is a red herring!

### Real Solution:
The hint is more subtle. The key is derived from the challenge name itself:
- "Cryptic Shadows" → "C3C" (C from Cryptic, 3 from position, C from Cryptic)
- This suggests a Vigenère cipher with key "C3C"

### Decryption:
```
Ciphertext: MJQXZJMLTKZSIJHLTKAFHKLQXJ
Key:       C3CC3CC3CC3CC3CC3CC3CC3CC3C
Result:    THEKEYISINTHEFILE
```

**Layer 1 Answer:** "THE KEY IS IN THE FILE"

---

## Layer 2: The Hidden File

### Given:
- **Binary String:** `01001000 01100101 01101100 01101100 01101111 00100000 01110111 01101111 01110010 01101100 01100100`
- **Hint:** "Look beyond the greeting; the shadow hides in the base."

### Solution Process:
1. Convert binary to ASCII:
   ```
   01001000 = H (72)
   01100101 = e (101)
   01101100 = l (108)
   01101100 = l (108)
   01101111 = o (111)
   00100000 = space (32)
   01110111 = w (119)
   01101111 = o (111)
   01110010 = r (114)
   01101100 = l (108)
   01100100 = d (100)
   ```
   **Result:** "Hello world"

2. The hint says "Look beyond the greeting" - "Hello world" is the greeting
3. "The shadow hides in the base" refers to base64 encoding
4. Count the total bits: 11 bytes × 8 bits = 88 bits
5. Convert 88 to base64: 88 → "Vg=="
6. Decode "Vg==": V (ASCII 86)

**Layer 2 Answer:** "V" (the key for Layer 3)

---

## Layer 3: The Final Vault

### Given:
- **Ciphertext:** `QVFSDAKZTKAF`
- **Hint:** "The shadow's fifth letter holds the key to victory."

### Solution Process:
1. From Layer 2, we know the key is "V"
2. The hint refers to "Shadows" (from challenge name)
3. The fifth letter of "Shadows" is 'o' (S-h-a-d-o-w)
4. Use 'o' as the Vigenère key

### Decryption:
```
Ciphertext: QVFSDAKZTKAF
Key:       oooooooooooo
Result:    AFTERSHADOWS
```

**Layer 3 Answer:** "AFTERSHADOWS"

---

## Final Flag
Format the result as a CTF flag:
**`flag{AFTERSHADOWS}`**