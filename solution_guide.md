# Cryptic Shadows Challenge - Solution Guide

## Challenge Overview
This is a three-layer cryptography challenge where each layer reveals a hint to the next. The final flag is `flag{AFTERSHADOWS}`.

## Layer 1: The Ciphered Note

### Given:
- **Ciphertext:** `LOENSUAZIQHDWMIOS`
- **Hint:** "The key lies in the shadows of the first word, repeated like an echo."

### Solution Process:
1. The hint mentions "shadows of the first word" - this refers to the challenge name "Cryptic Shadows"
2. The first word is "Cryptic"
3. "Shadows" suggests taking letters from "Shadows" 
4. "Repeated like an echo" suggests repeating the key
5. Key derivation: Take the word "Shadows" → "SHADOW" (removing the 'S' at the end)
6. Use "SHADOW" as the Vigenère key

### Decryption:
```
Ciphertext: LOENSUAZIQHDWMIOS
Key:       SHADOWSHADOWSHADO
Result:    THEKEYISINTHEFILE
```

**Layer 1 Answer:** "THE KEY IS IN THE FILE"

---

## Layer 2: The Hidden File

### Given:
- **Binary String:** `01010110`
- **Hint:** "Look beyond the greeting; the shadow hides in the base."

### Solution Process:
1. Convert binary to ASCII:
   ```
   01010110 = V (86)
   ```
   **Result:** "V"

2. The hint says "Look beyond the greeting" - this is a red herring, the greeting is not "Hello world"
3. "The shadow hides in the base" refers to the binary encoding
4. The binary string directly represents the letter "V" in ASCII

**Layer 2 Answer:** "V" (the key for Layer 3)

---

## Layer 3: The Final Vault

### Given:
- **Ciphertext:** `OTHSFGVORCKG`
- **Hint:** "The shadow's fifth letter holds the key to victory."

### Solution Process:
1. From Layer 2, we know the key is "V"
2. The hint refers to "Shadows" (from challenge name)
3. The fifth letter of "Shadows" is 'o' (S-h-a-d-o-w)
4. Use 'O' as the Vigenère key

### Decryption:
```
Ciphertext: OTHSFGVORCKG
Key:       OOOOOOOOOOOO
Result:    AFTERSHADOWS
```

**Layer 3 Answer:** "AFTERSHADOWS"

---

## Final Flag
Format the result as a CTF flag:
**`flag{AFTERSHADOWS}`**