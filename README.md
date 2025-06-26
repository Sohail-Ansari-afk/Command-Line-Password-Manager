# 🔐 Command-Line Password Manager (Python)

A secure and simple **command-line password manager** built using Python and `cryptography`. It lets you save, encrypt, and retrieve passwords securely — all via your terminal! 💻🔏

---

## 🔒 Features

- 🧠 Master password protection
- 🔐 AES-based password encryption using `Fernet` and `PBKDF2`
- 💾 Stores credentials in a local `vault.json`
- 🧊 Salted key derivation for enhanced security
- 🧑‍💻 CLI interface — no GUI clutter

---

## 🛠️ Requirements

- Python 3.x
- Install required package:

```bash
pip install cryptography
````

---

## 🚀 How to Use

1. 📥 Save the script as:

   ```bash
   Command-Line Password Manager.py
   ```

2. 🏃 Run the script:

```bash
python "Command-Line Password Manager.py"
```

3. 🔑 When prompted, enter your **master password** (first time generates a new salt).

4. Select from the menu:

```
--- Menu ---
1. Add new password
2. View saved passwords
3. Exit
```

---

## 🗄️ How Passwords Are Stored

Passwords are stored in `vault.json` in encrypted form, like:

```json
{
  "salt": "c2FsdC1ieXRlcy1lbmNvZGVk",
  "passwords": {
    "example.com": {
      "username": "myusername",
      "password": "gAAAAABj..."
    }
  }
}
```

---

## 📦 Example Flow

* Enter master password
* Choose **"1"** to add a new password
* Enter website, username, and password
* Choose **"2"** to view saved credentials

✔️ The script decrypts and shows the username and password

---

## 🔐 Security Details

* Uses `PBKDF2HMAC` (390,000 iterations) with SHA-256 to derive key from master password 🔑
* Random salt is generated and stored (encoded in base64)
* Uses `Fernet` for symmetric AES encryption of passwords
* Password input hidden using `getpass`

---

## ⚠️ Important Notes

* This is a **local-only** password manager (no sync or online backup)
* Protect your `vault.json` file — do not upload it or share it
* Master password must be remembered — there’s no recovery built-in
* Encryption key is never stored — it's derived from the master password and salt at runtime

---

## 🧑‍💻 Author

Crafted with ❤️ for privacy-conscious CLI users and coders.

---

Start managing your passwords like a pro! 🔐💪🧠

