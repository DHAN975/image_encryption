# image_encryption
🔐 Image Encryption with AES 
🧠 Overview
This project demonstrates how to securely encrypt and decrypt image files using the Advanced Encryption Standard (AES) algorithm in Cipher Block Chaining (CBC) mode. AES is a symmetric encryption algorithm widely used for data security. CBC mode enhances security by ensuring that identical plaintext blocks produce different ciphertexts.


🔐 Why AES in CBC Mode?
Security: CBC mode uses a unique Initialization Vector (IV) for each encryption, ensuring that identical plaintexts yield different ciphertexts, thereby enhancing security.

Padding: AES requires input data to be a multiple of its block size (16 bytes). CBC mode requires padding the plaintext to meet this block size requirement. 
onboardbase.com

IV Handling: A random IV is generated for each encryption operation and is typically stored alongside the ciphertext to ensure proper decryption. 

⚙️ How It Works
Key Generation: A 128-bit AES key is randomly generated using os.urandom(16).


IV Generation: A random 16-byte IV is generated to ensure unique encryption for each file.

Padding: The plaintext image data is padded to make its length a multiple of 16 bytes using Crypto.Util.Padding.pad.

Encryption: The padded data is encrypted using AES in CBC mode with the generated key and IV.

Storage: The IV is prepended to the ciphertext and saved to a file, ensuring it can be used for decryption.

Decryption: To decrypt, the IV is extracted from the encrypted file, and the ciphertext is decrypted using the same key and IV, followed by unpadding to retrieve the original image data.

📌 Security Considerations
Key Management: The security of AES encryption relies on the secrecy of the key. It's crucial to store and manage the key securely.

IV Uniqueness: Reusing an IV with the same key can compromise security. Always generate a new IV for each encryption.

Padding: Ensure proper padding and unpadding to maintain data integrity.
