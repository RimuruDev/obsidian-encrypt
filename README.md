
---

# Установка Meld Encrypt на macOS (Obsidian Desktop)
- Settings → Community plugins
- Включить Restricted mode и включить community plugins
- Browse → в поиске набрать Meld Encrypt
- Install → Enable 
- Obsidian Help
- Готово, изи катка :3

# Найденные баги
- Возможность потери данных из-за UX ошибки плагина на macOS
- Завел issue: https://github.com/meld-cp/obsidian-encrypt/issues/226

Продублирую issue для удобства себе:

 ## Title: 
 Cyrillic password can be set during encryption, but cannot be typed during decryption (keyboard layout forced to ABC)

 ## Desc:
 **Describe the bug**
Meld Encrypt allows setting an encryption password using Cyrillic characters (e.g., Russian keyboard layout) during the *encryption* dialog, but later the *decryption* password input appears to block non-English/Cyrillic typing and forces the "ABC" (English) input mode.  
As a result, the user can successfully encrypt a note with a Cyrillic password, but then cannot type the same password to decrypt it (unless they paste it from clipboard). This is a data-loss risk.

**To Reproduce**
Steps to reproduce the behavior:
1. Install and enable Meld Encrypt.
2. Encrypt any note (whole note encryption).
3. When the password prompt appears, switch the system keyboard layout to Russian/Cyrillic.
4. Type a Cyrillic password (e.g., "ТестируюПароль") and confirm encryption — it succeeds.
5. Now try to decrypt the same note.
6. In the decryption password prompt, switch keyboard layout to Russian/Cyrillic and try to type the same password.
7. Observe that Cyrillic input is blocked / input mode is forced to "ABC", making it impossible to enter the real password.

**Expected behavior**
The password input behavior should be consistent and safe:
- Either support Unicode/Cyrillic passwords in BOTH encryption and decryption dialogs, OR
- Prevent setting non-ASCII passwords during encryption and show a clear warning before confirming (e.g., "Only ASCII passwords are supported").

**Screenshots**
1) Encryption dialog: Cyrillic password can be entered and confirmed  

<img width="576" height="307" alt="Image" src="https://github.com/user-attachments/assets/3f85aff7-609b-4e67-8ea1-f62fb03bfecc" />

2) Another example of encryption dialog accepting Cyrillic  

<img width="606" height="341" alt="Image" src="https://github.com/user-attachments/assets/82ac879f-46fe-4572-b937-df28bf79d376" />

3) Decryption dialog: input is forced to "ABC" / Cyrillic typing is blocked

<img width="464" height="180" alt="Image" src="https://github.com/user-attachments/assets/91b6c4f2-39f5-47a8-a4e2-a247f9226bc3" />

**Desktop (please complete the following information):**
 - OS: macOS Tahoe 26.2
 - Obsidian Version: 1.10.6
 - Plugin Version: 2.4.5
 - Keyboard layouts tested: English (ABC) + Russian

**Smartphone (please complete the following information):**
 - N/A

---

# Информация о плагине:

# [Meld Encrypt](https://github.com/meld-cp/obsidian-encrypt) Plugin for Obsidian

**Create Encrypted Notes Within Your [Obsidian.md](https://obsidian.md/) Vault**

[Meld Encrypt](https://github.com/meld-cp/obsidian-encrypt) is a community plugin that lets you encrypt and decrypt your notes in [Obsidian](https://obsidian.md/). You can choose to encrypt an [entire note](https://meld-cp.github.io/obsidian-encrypt/whole-encrypted-notes.html) or just [selected text within a note](https://meld-cp.github.io/obsidian-encrypt/in-place-encryption.html).

Encrypted notes are never decrypted to disk giving you peace-of-mind that the decrypted contents haven't been sync'd or backed up to external systems.

---

> [!WARNING]
> ⚠️ Use at Your Own Risk ⚠️
> - Your passwords are never stored. If you forget your password, your notes cannot be decrypted..
> - The encryption methods used have not been independently audited. Unauthorized access may be possible if someone gains access to your files.
> - Bugs may be introduced at any time. You are solely responsible for maintaining backups of your notes.

---

## Ongoing Maintenance and Development

If you find this plugin useful please support the ongoing maintenance and development by:
* [Staring ⭐ this repo](https://github.com/meld-cp/obsidian-encrypt)
* [Buying me a coffee ☕](https://www.buymeacoffee.com/cleon)
* [Sponsoring ❤️ me](https://github.com/sponsors/meld-cp).

Thank you for your support 😊

<a href="https://www.buymeacoffee.com/cleon" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 50px !important;" ></a>


## Latest Changes

Information about the latest release can be found on the [release notes](https://meld-cp.github.io/obsidian-encrypt/release-notes.html) page.

Report any bugs or features requests [here](https://github.com/meld-cp/obsidian-encrypt/issues).


## Documentation

Documentation can be found [here](https://meld-cp.github.io/obsidian-encrypt/)


**Additional context**
This can easily cause lockout and potential data loss: users may encrypt notes with a password they later cannot type.
Workaround: copy/paste the password (if it was saved somewhere), but if the user did not store it, the note may become permanently inaccessible.
