# EnvVault

EnvVault is a lightweight, client-side web application that allows you to securely encrypt your `.env` files using a password, and share the encrypted result with others.

All encryption and decryption are performed locally in your browser. No data is ever transmitted to any server.

## How it works

1. **Encrypt (Sender)**
   - Paste your `.env` content into the text area, or upload the file directly.
   - Set a strong password (minimum 8 characters).
   - Click "Encrypt".
   - The encrypted output (payload) is displayed. You can:
     - Copy it to your clipboard.
     - Download it as a `.vault` file.

2. **Decrypt (Receiver)**
   - Paste the received payload text, or upload the `.vault` file.
   - Enter the same password.
   - Click "Decrypt".
   - The original `.env` content is shown, ready to copy or download.

## Security

- Encryption uses the Web Crypto API with AES-256-GCM and PBKDF2 key derivation (150,000 iterations).
- The password never leaves your device.
- The encrypted payload is safe to store or share publicly; only the password holder can decrypt it.

> [!IMPORTANT]
> Your password is the only protection. Use a strong, unique password with at least 12 characters, including uppercase, lowercase, numbers, and symbols. Never share your password over the same channel as the encrypted file (e.g., do not send both in the same email or chat message). If your password is weak or reused, the encryption will not protect you.

## Usage scenarios

- Share environment variables with team members without exposing them in plain text.
- Store encrypted backups of your `.env` files in version control.
- Transfer sensitive configuration securely via any communication channel (email, chat, etc.) – the encrypted payload and password are sent separately.

## Technical details

- Single HTML file – no build tools or dependencies.
- Works offline (PWA-ready) with a service worker.
- No external storage or database; everything is ephemeral and stored only in your browser's memory.

## Deployment

You can host this application on any static hosting service (GitHub Pages, Netlify, Vercel, etc.). Simply upload the `index.html` file.

To run it locally, open the file in a modern browser, or use a local server for full offline and camera support (though camera is not required).

## License

This project is open source and available under the MIT License. Feel free to use, modify, and distribute it as you wish.

## Contributing

Contributions are welcome. Please open an issue or submit a pull request on the repository.

## Acknowledgements

Built with vanilla JavaScript and the Web Crypto API.

---

For more information, visit the project repository.