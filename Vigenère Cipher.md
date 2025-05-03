### **Vigenère Cipher**

The **Vigenère Cipher** is a type of **polyalphabetic cipher**, which means it uses more than one shift to encrypt a message, making it more secure than simple ciphers like the Caesar cipher.

### **How It Works**:

1. **Key**: You choose a word or phrase (called the "key"). This key is used to determine how each letter in your message will be shifted. If the key is shorter than your message, you repeat the key to match the length of the message.

2. **Alphabet Table**: The Vigenère Cipher uses a table where each row shifts the alphabet by one position. This is known as the **Vigenère Square**.

### **Steps for Encryption**:

Let’s use an example to make this easier:

#### **Example**:

**Plaintext**: "HELLO"

**Key**: "KEY"

##### **Step 1: Repeat the Key**

* The key "KEY" is repeated to match the length of the message "HELLO":

  * **Key**: "KEYKE"

##### **Step 2: Use the Vigenère Square**

The Vigenère Square shows how the alphabet shifts for each letter. Here's a small part of it:

| Letter    | A  | B | C  | D  | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z |
| --------- | -- | - | -- | -- | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - |
| **Key**   | K  | E | Y  | K  | E |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |
| **Shift** | 10 | 4 | 24 | 10 | 4 |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |

##### **Step 3: Encrypt the Message**

To encrypt, for each letter in the plaintext:

1. Find the corresponding letter from the key.
2. Use the Vigenère Square to shift the plaintext letter according to the key letter.

| **Plaintext**  | **H** | **E** | **L** | **L** | **O** |
| -------------- | ----- | ----- | ----- | ----- | ----- |
| **Key**        | **K** | **E** | **Y** | **K** | **E** |
| **Shift**      | 10    | 4     | 24    | 10    | 4     |
| **Ciphertext** | **R** | **I** | **J** | **V** | **S** |

* **H** is shifted by **K** (10 positions) → **R**
* **E** is shifted by **E** (4 positions) → **I**
* **L** is shifted by **Y** (24 positions) → **J**
* **L** is shifted by **K** (10 positions) → **V**
* **O** is shifted by **E** (4 positions) → **S**

So, the **Ciphertext** is: **"RIJVS"**.

---

### **Decryption Process**:

To decrypt, you just reverse the encryption process:

1. Use the same key.
2. For each letter in the ciphertext, subtract the shift value based on the key.

| **Ciphertext** | **R** | **I** | **J** | **V** | **S** |
| -------------- | ----- | ----- | ----- | ----- | ----- |
| **Key**        | **K** | **E** | **Y** | **K** | **E** |
| **Shift**      | 10    | 4     | 24    | 10    | 4     |
| **Plaintext**  | **H** | **E** | **L** | **L** | **O** |

* **R** is shifted back by **K** (10 positions) → **H**
* **I** is shifted back by **E** (4 positions) → **E**
* **J** is shifted back by **Y** (24 positions) → **L**
* **V** is shifted back by **K** (10 positions) → **L**
* **S** is shifted back by **E** (4 positions) → **O**

So, the **Decrypted Plaintext** is: **"HELLO"**.

---

### **Conclusion**:

The Vigenère Cipher is stronger than simpler ciphers because it uses different shifts for each letter, depending on the key. This makes it harder for someone to break the code by just looking at the frequency of letters, as is possible with simpler ciphers.
