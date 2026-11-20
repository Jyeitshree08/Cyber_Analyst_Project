# Browser-Based Encryption

A standalone, client-side **self-decrypting HTML application** that protects sensitive webpage content with a password—requiring **zero backend servers, databases, or external libraries**. 

Built using the browser's native **Web Crypto API**, this project derives a 256-bit cryptographic key via **PBKDF2** and locks content locally using **AES-256-GCM** authenticated encryption.

---

## Features

* **100% Client-Side & Zero-Knowledge:** All encryption, key stretching, and decryption run locally in browser memory. Passwords and unencrypted text never leave your device.
* **AES-256-GCM Authenticated Encryption:** Scrambles the hidden webpage into unreadable Base64 ciphertext and appends a 16-byte authentication tag to detect tampering.
* **PBKDF2 Key Stretching:** Uses `600,000` iterations of SHA-256 with a random 16-byte salt to protect against brute-force attacks.
* **Real-Time Password Strength Meter:** Scores passwords dynamically across five security criteria (length, mixed case, numbers, and symbols) from *Very Weak* to *Strong*.
* **Show / Hide Password Toggles:** Prevents typing mistakes when setting or entering passwords.
* **Full-Page Decryption:** Dynamically replaces the lock screen with a brand-new styled webpage (`backg.jpg`) upon successful password verification.

---

## How It Works

1. **Stage 1 — Password Setup:** Enter a password and monitor its strength on the live color-coded progress bar.
2. **Stage 2 — Encryption & Locking:** Clicking **Lock & Encrypt Page** generates a random 16-byte Salt and 12-byte IV, derives an AES-256 key, encrypts the hidden webpage, and displays a Base64 ciphertext preview.
3. **Stage 3 — Authenticated Unlock:** Entering the matching password verifies the GCM security tag, decrypts the content, and opens the full protected webpage.

---

## Project Structure

```text
browser-based-encryption/
├── browser_encryption.html     # Complete self-contained UI, encryption, and decryption logic
├── backg.jpg      # Background wallpaper displayed on the unlocked webpage
└── README.md      # Project documentation
```

---

## How to Run Locally

1. Download or clone this repository:
   ```bash
   git clone https://github.com/Jyeitshree08/browser-based-encryption.git
   ```
2. Ensure `index.html` and `backg.jpg` are in the **same folder**.
3. Double-click `browser_encryption.html` to open it directly in any modern web browser (Chrome, Edge, Firefox, or Safari).

---

## Technologies Used

* **HTML5 & CSS3** — Responsive card layout and custom full-screen unlocked view
* **JavaScript (ES6+)** — Async binary buffer handling (`Uint8Array`) and dynamic DOM replacement
* **Web Crypto API (`window.crypto.subtle`)** — `PBKDF2`, `AES-GCM`, and `crypto.getRandomValues()`

---

## Author

* Jyeitshree — BCA First-Year Individual Project
# Cyber_Analyst_Project
