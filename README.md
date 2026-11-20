# Password Cracking & Hash Recovery Lab (John the Ripper & Johnny)

![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity%20%26%20Ethical%20Hacking-blue)
![Tools](https://img.shields.io/badge/Tools-John%20the%20Ripper%20%7C%20Johnny%20%7C%20Kali%20Linux-green)
![Status](https://img.shields.io/badge/Lab%20Status-Completed-brightgreen)

## ⚠️ Ethical & Liability Disclaimer
**For Educational and Authorized Testing Purposes Only.**

The techniques, tools, and walkthroughs documented in this repository are strictly intended for educational learning, defensive security auditing, and authorized penetration testing within isolated lab environments. 

* **No Unauthorized Access:** Attempting to crack passwords, extract hashes, or bypass security controls on systems, files, or networks without explicit, written authorization from the owner is illegal and unethical.
* **Limitation of Liability:** The author of this repository assumes **no responsibility or liability** for any misuse, damage, data loss, or legal consequences resulting from the application of the information provided herein. Users are solely responsible for complying with all applicable local, national, and international laws.

---

## 📌 Project Overview
This repository documents hands-on cybersecurity lab modules focused on cryptographic hashing, hash extraction, and dictionary-based password recovery. Across this project, I successfully processed **multiple password-protected PDF targets (`My Locked PDF1.pdf` and variants)**, extracted their structural hashes, and successfully recovered the plain-text passwords to capture all target flags.

1. **Module 1: Password Cracking with JTR & Johnny GUI**
Extracting hashes from an encrypted PDF and recovering credentials using John the Ripper and its graphical interface (Johnny) on Kali Linux and Windows.

2. **Module 2: Browser-Based Hashing & Dictionary Attacks**
 Performing local hash extraction and dictionary attack simulations using Networkwalks web utilities.
---

## 🛠️ Environment & Tools Used
* **Operating Systems: ** Kali Linux (VirtualBox) & Windows.
* **Password Auditing Tools:** John the Ripper (`1.9.0-jumbo-1`), Johnny GUI (`v2.2`)
* **Web Utilities:** OnlineHashCrack PDF Extractor, Networkwalks Hash Calculator & Password Cracker
* **Target Artifacts: ** Multiple password-protected PDF CTF challenges ('My Locked PDF1.pdf' 'My Locked PDF 2.pdf' 'My Locked PDF 3.pdf')

---

## 📋 Step-by-Step Execution Guide

### Module 1: Command-Line & GUI Password Cracking (JTR & Johnny)
1. **Tool Setup:** Verified pre-installed JTR binaries (`/usr/sbin/john`) within Kali Linux and installed Johnny GUI via `sudo apt install johnny`. Configured Johnny to automatically detect the JTR Jumbo binary under **Settings**[span_20](start_span)[span_20](end_span).

2. **Hash Acquisition (`pdf2john`):** Uploaded the encrypted PDF files to extract structural encryption metadata hashes in the standard `$pdf$` format). Copied the full hash strings (ensuring no extraneous wrapper characters like `b'` were included).

3. **Execution:** Created clean reference text files (`hash1.txt`) containing the extracted hashes.

4. Loaded them into Johnny via **Open password file (PASSWD format)** and initialized a dictionary-based attack by clicking **Start new attack**

5. **Result:** Successfully recovered the plain-text passwords (e.g., `password1`) across all target files, unlocking the secure documents to capture the flags.



### Module 2: Browser-Based Hashing & Dictionary Attacks
1. **Hash Calculation:** Opened the Networkwalks Hash Calculator utility in a browser, switched to the **PDF** tab, and uploaded the target encrypted PDF. The tool parsed the file locally to generate a compatible `$pdf$` hash.

2. **Dictionary Attack Simulation:** Passed the extracted hashes into the Networkwalks Password Cracker tool against a built-in wordlist of 100 common passwords to simulate rapid brute-forcing.

3. **Validation:** Matched the hashes against target dictionary words and successfully unlocked the secure documents to verify end-to-end security auditing workflows.

---


## 🖼️ Lab Execution Highlights

### 1. Johnny GUI & JTR Engine Configuration
Verifying that Johnny automatically detects the pre-installed `/usr/sbin/john` binary inside Kali Linux
![Johnny Settings](images/01-johnny-settings.png)

### 2. Successful Password Recovery
Running a dictionary attack against the extracted `$pdf$` hash to recover the plain-text password
![Johnny Cracked Password](images/03-johnny-cracked.png)

### 3. Flag Capture Verification
Unlocking the protected document using the recovered credential to complete the challenge
![Captured Flag](images/04-flag-captured.png)

---


## 🔑 Key Security Takeaways
* **Hashing vs. Encryption:** Encryption is a reversible two-way process requiring a decryption key, whereas hashing is a one-way mathematical function that produces a fixed-length message digest for credential verification.

* **Vulnerability of Weak Passwords:** Simple dictionary words can be cracked in seconds once an attacker obtains the underlying hash.

* **Defense-in-Depth:** Organizations should enforce long, high-entropy passphrases, modern slow-hashing algorithms (e.g., Argon2id, bcrypt), and Multi-Factor Authentication (MFA).

---
*Projects completed as part of practical Cybersecurity & Ethical Hacking training modules
