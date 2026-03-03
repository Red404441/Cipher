#Cipher
Encrypted messaging with a shared key

What is Cipher?
Cipher is a simple, browser-based tool that lets two people exchange encrypted messages using a shared secret key. No accounts, no servers, no data sent anywhere — everything runs entirely in your browser.

How to Use
Step 1 — Share a key with your friend
One person clicks "Generate" to create a random secret key, then shares it with the other person through any channel (text, email, in person). This only needs to happen once.
Step 2 — Encrypt a message
Type your message, make sure the secret key is entered, and hit "Encrypt". Copy the scrambled output and send it to your friend however you like.
Step 3 — Decrypt a message
Paste the encrypted message you received, enter the same shared key, and hit "Decrypt". Your original message will appear.
That's it. The key is what makes decryption possible — anyone without it cannot read the message.

How the Encryption Works
Cipher uses AES-256-GCM, one of the strongest and most widely trusted encryption standards in the world. It is the same algorithm used by governments, banks, and secure messaging apps.
Before encrypting, your secret key is run through PBKDF2 — a key-stretching algorithm that turns even a short password into a hardened 256-bit cryptographic key. This makes brute-force attacks significantly harder.
Each message is encrypted with a randomly generated IV (initialisation vector), meaning the same message encrypted twice will produce different output every time — making pattern analysis impossible.
The GCM part of AES-256-GCM also verifies that the message hasn't been altered in transit. If anyone tampers with the encrypted text, decryption will fail.
All cryptography is handled by the browser's built-in Web Crypto API — no third-party libraries involved.

Security Note
The strength of Cipher depends entirely on how securely you share the key. If someone intercepts your key, they can decrypt your messages. Share it in person or through a separate trusted channel.
