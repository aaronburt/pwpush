# PW Push 🔐

**Client-side secure message sharing (AES-GCM)**

A small static web page that lets users encrypt short secrets in the browser and share them as a URL fragment (hash). All encryption and decryption happen locally using the Web Crypto API — no payloads or private data are sent to any server.

---

## Features ✅

- AES-GCM encryption with a key derived from a passphrase (PBKDF2 + SHA-256)
- Copyable secure links containing the encrypted payload in the URL fragment
- Simple UX for generating and unlocking messages

---

## Security & Privacy ⚠️

- The link contains the encrypted payload in the hash; the passphrase is not included — keep it secret and share it out-of-band.
- Use a strong, long passphrase instead of a short PIN when possible.
- Decryption failures are indistinguishable from wrong passphrases or tampered payloads.
- The app relies on the browser's Web Crypto API; older browsers without `crypto.subtle` will not work.
