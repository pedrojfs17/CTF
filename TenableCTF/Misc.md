# Tenable CTF

## Misc

### **Esoteric**
After some tries to find out which type of encryption this had, we found that it was `Brainfuck` encryption. Decoding to plain text we get the flag.

> flag{wtf_is_brainfuck}

---

### **Find the encoding**
With the input in `CyberChef`, we tested some different encodings and found out that this was `base58`.

> flag{not_base64}

---