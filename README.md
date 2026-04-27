# OBSIDYN Operational Sanctuary (v2.0.2)
**Absolute sovereignty over your digital footprint.**

<p align="center">
  <img src="ui/src/icon.png" alt="OBSIDYN Banner" width="250"/>
</p>

**OBSIDYN** is an advanced, self-contained desktop security environment engineered to protect highly sensitive data through extreme cryptographic isolation, biometric rhythm analysis, and steganographic obfuscation. 

Designed for operators who require plausible deniability and zero-trust data custody, OBSIDYN masks its existence, defends against unauthorized forensic analysis, and ensures that your critical intelligence remains exclusively under your control.

---

## 💻 System Requirements

- **Operating System**: Windows 10 / Windows 11 (64-bit required)
- **Processor**: Intel Core i5 / AMD Ryzen 5 or higher recommended
- **Memory (RAM)**: 8GB minimum (16GB recommended for heavy Vault I/O)
- **Storage**: Minimum 500MB for installation (additional space required for Vault storage)
- **Hardware**: Standard Keyboard (for Rhythm Lock), Web Camera (Required for Visual Recovery enrollment)

---

## 🚀 Installation Guide

OBSIDYN is deployed via a compiled standalone executable.

1. **Obtain the Installer**: Locate `obsidyn-production-v2.0.2.exe`.
2. **Execute Installation**: Run the executable as Administrator. 
3. **Stealth Footprint**: OBSIDYN is designed with stealth in mind. Depending on your installation parameters, the software may not appear in standard "Add/Remove Programs" lists or desktop shortcuts. Be sure to note the installation directory (typically `AppData/Local/Programs/obsidyn-see` or a custom directory).
4. **Initial Launch**: Navigate to the installation directory and launch the primary executable.

---

## 🛡️ Core Features & Usage Guide

### 1. Initialization & Rhythm Lock Enrollment
**What it does**: OBSIDYN does not just rely on what your password is, but *how* you type it. 
**How to use**:
- Upon first launch, you will be prompted to create a Master Key.
- You must type this password multiple times. The system is analyzing your keystroke dynamics (flight and dwell times) to create a unique behavioral biometric profile (Rhythm Lock).
- *Tip*: Type naturally. Do not artificially speed up or slow down. If an adversary steals your password, they cannot access the system unless they mimic your exact typing cadence.

### 2. Multi-Factor Authentication (PVS Carrier Image)
**What it does**: Allows you to bypass keystroke requirements using a steganographically verified image (Pixel Veil System).
**How to use**:
- **Setup**: Go to Settings -> Security. Enroll a "PVS-pass". The system will hide an encrypted text string inside an image of your choosing.
- **Usage**: When logging in, if MFA is enabled, you will be prompted to supply this Carrier Image. The engine will extract and verify the hidden hash before allowing entry.

### 3. Visual Recovery (Passwordless Override)
**What it does**: A fallback mechanism in case you forget your master key or fail the Rhythm Lock.
**How to use**:
- **Enrollment**: Go to Settings -> Identity. Select "Enroll Visual Recovery". Look into your webcam and perform a specific, memorable gesture. The system embeds these facial and gesture mappings locally.
- **Recovery**: If you fail your password attempts (default 3 times), the Visual Recovery module activates. Perform your registered gesture to regain access to your vault and rotate your master key.

### 4. The Encrypted Vault
**What it does**: AES-GCM 256-bit encryption for files and folders, physically hidden on the OS.
**How to use**:
- **Locking**: Drag and drop files/folders into the Vault UI, or use the "Lock File/Folder" buttons. The original plaintext files are securely shredded from your drive, and the encrypted `.obs` containers are marked as invisible OS-level system files.
- **Unlocking**: Select an item in your Vault list and click "Unlock". Choose a destination directory to restore the decrypted file.

### 5. Steganography Engine (Pixel Veil)
**What it does**: Hides secret files, documents, or texts directly inside the pixels (LSB) of standard, innocent-looking images. Provides ultimate plausible deniability.
**How to use**:
- **Hide Data**: Go to the Steganography tab. Select a target payload file, select a normal "Carrier Image" (e.g., a family photo), and optionally provide an encryption password. OBSIDYN will generate a new image that looks identical but contains your hidden payload.
- **Extract Data**: Select an image containing OBSIDYN data. Enter the password (if used), and the engine will decrypt and spit out your original file.
- **Sanitize Image**: (New in v2.0.2) Select an image to permanently strip and destroy any hidden LSB steganographic data without compromising the visual quality of the image.

### 6. Decoy Environments
**What it does**: Wastes an adversary's time. Generates highly realistic but completely fake files (logs, financial records, source code) to misdirect unauthorized investigations.
**How to use**:
- Go to Settings -> Decoy Operations.
- Select a profile (e.g., "Financial" or "Operations") and define a target directory.
- Click "Deploy Decoys". OBSIDYN will flood the directory with synthetic, believable noise.

### 7. Secure Shredding
**What it does**: Deleting a file normally leaves traces on the hard drive. Secure Shredding overwrites the physical disk sectors to ensure DoD-level (5220.22-M) data destruction.
**How to use**:
- You can manually shred files from the UI. Additionally, when locking items into the Vault, OBSIDYN automatically uses this protocol to destroy the original plaintext files, leaving zero forensic trace.

### 8. Operator Notes
**What it does**: A double-encrypted notepad built directly into the UI.
**How to use**:
- Go to the Identity/Notes tab. Accessing notes requires a secondary "Note Passcode", distinct from your Master Key. Even if your main session is left unlocked, adversaries cannot read your operational intelligence without this secondary key.

---

## 🔒 Security Posture & Architecture Overview

For advanced operators, OBSIDYN employs a Zero-Trust internal architecture:
- **No Plaintext Storage**: Your master key is never stored. It is hashed using strong KDFs (Key Derivation Functions). 
- **Ephemeral Keys**: Cryptographic keys exist only in active RAM. When you lock the system or close the UI, the session keys are instantly wiped. 
- **Isolated Modules**: The UI (Electron) has zero access to encryption keys or algorithms. It communicates strictly via structured IPC pipelines to a heavily isolated Python cryptography engine.
- **Offline By Design**: OBSIDYN does not "phone home." Your data, biometrics, and keys never leave your local hard drive.

*(For a comprehensive developer-level architectural breakdown, refer to the `/Memory` directory included in the source codebase).*

---

## ⚠️ Critical Warnings & Best Practices

1. **DO NOT LOSE YOUR MASTER KEY OR CARRIER IMAGE.** Because OBSIDYN relies on true zero-knowledge AES encryption, the developers **cannot** recover your data if you lose your keys and fail your Visual Recovery. 
2. **Back up your Carrier Image**: If using the PVS-pass system, ensure your Carrier Image is backed up securely (e.g., on an offline USB drive). If the file is altered by even a single pixel, the steganographic hash will change, and authentication will fail.
3. **Environment Stability**: Do not modify the `data/vaults` directory manually using Windows Explorer. Doing so may corrupt the AES-GCM nonces and result in permanent data loss.

---
*OBSIDYN v2.0.2 - Securing the Unseen.*
