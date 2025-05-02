## 🔐 a) **Encryption**

> **Definition**: Encryption is the process of converting **plaintext** (original message) into **ciphertext** (unreadable message) using a **key** and a mathematical algorithm.

### Example (Caesar Cipher):

Let’s say we use Caesar Cipher with a key $k = 3$.

* **Plaintext (P)**: `HELLO`

* Convert to numeric:
  H=7, E=4, L=11, L=11, O=14 (assuming A=0, B=1, ..., Z=25)

* **Encryption formula**:

  $$
  C_i = (P_i + k) \mod 26
  $$

* **Ciphertext (C)**:

  $$
  \begin{align*}
  C_1 &= (7 + 3) \mod 26 = 10 \rightarrow K \\
  C_2 &= (4 + 3) \mod 26 = 7 \rightarrow H \\
  C_3 &= (11 + 3) \mod 26 = 14 \rightarrow O \\
  C_4 &= (11 + 3) \mod 26 = 14 \rightarrow O \\
  C_5 &= (14 + 3) \mod 26 = 17 \rightarrow R \\
  \end{align*}
  $$

✅ **Result**: Ciphertext = **KHOOR**

---

## 🔓 b) **Decryption**

> **Definition**: Decryption is the reverse process of encryption, converting **ciphertext** back into **plaintext** using the key.

### Continuing the Caesar Cipher Example:

* **Ciphertext (C)**: `KHOOR`

* Numeric: K=10, H=7, O=14, O=14, R=17

* **Decryption formula**:

  $$
  P_i = (C_i - k) \mod 26
  $$

* **Plaintext (P)**:

  $$
  \begin{align*}
  P_1 &= (10 - 3) \mod 26 = 7 \rightarrow H \\
  P_2 &= (7 - 3) \mod 26 = 4 \rightarrow E \\
  P_3 &= (14 - 3) \mod 26 = 11 \rightarrow L \\
  P_4 &= (14 - 3) \mod 26 = 11 \rightarrow L \\
  P_5 &= (17 - 3) \mod 26 = 14 \rightarrow O \\
  \end{align*}
  $$

✅ **Result**: Plaintext = **HELLO**

---

## 🕵️ c) **Cryptanalysis**

> **Definition**: Cryptanalysis is the science of breaking cryptographic systems without knowing the key — i.e., **"breaking the code"**.

### Example (Caesar Cipher attack without key):

Suppose you intercept `KHOOR` and don’t know the key.

You try **all 26 possible shifts (brute force)**:

* Key = 3 gives: `HELLO`
* Other keys produce garbage like `JGNNQ`, `IFMMP`, etc.

In **more advanced cryptosystems**, cryptanalysis involves:

* Frequency analysis
* Known-plaintext attack
* Chosen-plaintext/ciphertext attacks
* Linear or differential cryptanalysis

🧠 **Goal**: Find the key or original message **without access to the key**.

---

## 🔑 d) **Key**

> **Definition**: A **key** is a piece of information that determines the output of the cryptographic algorithm.

### Example:

In Caesar Cipher:

* Key $k = 3$: shift each letter by 3.

In **AES** (Advanced Encryption Standard):

* The key might be 128, 192, or 256 bits long, e.g.,

  ```
  2b7e151628aed2a6abf7158809cf4f3c
  ```

🔐 **Keys determine security**. The larger and more complex the key, the harder it is to break.

---

## 📄 e) **Plaintext**

> **Definition**: Plaintext is the **original, readable message or data** before encryption.

### Example:

* **Plaintext**: `HELLO`
* In binary: `01001000 01000101 01001100 01001100 01001111` (ASCII)

Plaintext is what you want to protect using encryption.

---

## 🧾 f) **Ciphertext**

> **Definition**: Ciphertext is the **scrambled, unreadable version** of the plaintext after encryption.

### Example:

From above,

* **Plaintext**: `HELLO`
* **Ciphertext** (Caesar Cipher with key = 3): `KHOOR`

Without the key, this looks like gibberish to an attacker.

---

### 📌 Summary Table

| Term          | Meaning                               | Example                     |
| ------------- | ------------------------------------- | --------------------------- |
| Encryption    | Plaintext → Ciphertext                | HELLO → KHOOR               |
| Decryption    | Ciphertext → Plaintext                | KHOOR → HELLO               |
| Cryptanalysis | Breaking encryption without key       | Trying all Caesar shifts    |
| Key           | Secret used for encryption/decryption | Caesar: 3, AES: 256-bit key |
| Plaintext     | Original message                      | "HELLO"                     |
| Ciphertext    | Encrypted message                     | "KHOOR"                     |

Would you like an RSA example as well (modular arithmetic with public/private keys)?
