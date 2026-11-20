# Password Cracking & Hash Recovery Lab (John the Ripper & Johnny)

![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity%20%26%20Ethical%20Hacking-blue)
![Tools](https://img.shields.io/badge/Tools-John%20the%20Ripper%20%7C%20Johnny%20%7C%20Kali%20Linux-green)
![Status](https://img.shields.io/badge/Lab%20Status-Completed-brightgreen)

## ⚠️ Ethical & Liability Disclaimer
**For Educational and Authorized Testing Purposes Only.**

The techniques, tools, and walkthroughs documented in this repository are strictly intended for educational learning, defensive security auditing, and authorized penetration testing within isolated lab environments[span_0](start_span)[span_0](end_span). 

* **No Unauthorized Access:** Attempting to crack passwords, extract hashes, or bypass security controls on systems, files, or networks without explicit, written authorization from the owner is illegal and unethical.
* **Limitation of Liability:** The author of this repository assumes **no responsibility or liability** for any misuse, damage, data loss, or legal consequences resulting from the application of the information provided herein. Users are solely responsible for complying with all applicable local, national, and international laws.

---

## 📌 Project Overview
This repository documents hands-on cybersecurity lab modules focused on cryptographic hashing, hash extraction, and dictionary-based password recovery[span_1](start_span)[span_1](end_span)[span_2](start_span)[span_2](end_span). Across this project, I successfully processed **multiple password-protected PDF targets (`My Locked PDF1.pdf` and variants)**, extracted their structural hashes, and successfully recovered the plain-text passwords to capture all target flags[span_3](start_span)[span_3](end_span)[span_4](start_span)[span_4](end_span).

1. **Module 1: Password Cracking with JTR & Johnny GUI** — Extracting hashes from an encrypted PDF and recovering credentials using John the Ripper and its graphical interface (Johnny) on Kali Linux and Windows[span_5](start_span)[span_5](end_span)[span_6](start_span)[span_6](end_span).
2. **Module 2: Browser-Based Hashing & Dictionary Attacks** — Performing local hash extraction and dictionary attack simulations using Networkwalks web utilities[span_7](start_span)[span_7](end_span)[span_8](start_span)[span_8](end_span).

---

## 🛠️ Environment & Tools Used
* **Operating Systems:** Kali Linux (VirtualBox Guest) & Windows Host[span_9](start_span)[span_9](end_span)[span_10](start_span)[span_10](end_span)
* **Password Auditing Tools:** John the Ripper (`1.9.0-jumbo-1`), Johnny GUI (`v2.2`)[span_11](start_span)[span_11](end_span)[span_12](start_span)[span_12](end_span)
* **Web Utilities:** OnlineHashCrack PDF Extractor, Networkwalks Hash Calculator & Password Cracker[span_13](start_span)[span_13](end_span)[span_14](start_span)[span_14](end_span)
* **Target Artifacts:** Multiple password-protected PDF CTF challenges (`My Locked PDF1.pdf` series)[span_15](start_span)[span_15](end_span)[span_16](start_span)[span_16](end_span)

---

## 📋 Step-by-Step Execution Guide

### Module 1: Command-Line & GUI Password Cracking (JTR & Johnny)
1. **Tool Setup:** Verified pre-installed JTR binaries (`/usr/sbin/john`) within Kali Linux and installed Johnny GUI via `sudo apt install johnny`[span_17](start_span)[span_17](end_span)[span_18](start_span)[span_18](end_span)[span_19](start_span)[span_19](end_span). Configured Johnny to automatically detect the JTR Jumbo binary under **Settings**[span_20](start_span)[span_20](end_span).
2. **Hash Acquisition (`pdf2john`):** Uploaded the encrypted PDF files to extract structural encryption metadata hashes in the standard `$pdf$` format[span_21](start_span)[span_21](end_span)[span_22](start_span)[span_22](end_span)[span_23](start_span)[span_23](end_span). Copied the full hash strings (ensuring no extraneous wrapper characters like `b'` were included)[span_24](start_span)[span_24](end_span).
3. **Execution:** Created clean reference text files (`hash1.txt`) containing the extracted hashes[span_25](start_span)[span_25](end_span)[span_26](start_span)[span_26](end_span). Loaded them into Johnny via **Open password file (PASSWD format)** and initialized a dictionary-based attack by clicking **Start new attack**[span_27](start_span)[span_27](end_span)[span_28](start_span)[span_28](end_span).
4. **Result:** Successfully recovered the plain-text passwords (e.g., `password1`) across all target files[span_29](start_span)[span_29](end_span), unlocking the secure documents to capture the flags[span_30](start_span)[span_30](end_span)[span_31](start_span)[span_31](end_span).

### Module 2: Browser-Based Hashing & Dictionary Attacks
1. **Hash Calculation:** Opened the Networkwalks Hash Calculator utility in a browser, switched to the **PDF** tab, and uploaded the target encrypted PDF[span_32](start_span)[span_32](end_span)[span_33](start_span)[span_33](end_span). The tool parsed the file locally to generate a compatible `$pdf$` hash[span_34](start_span)[span_34](end_span).
2. **Dictionary Attack Simulation:** Passed the extracted hashes into the Networkwalks Password Cracker tool against a built-in wordlist of 100 common passwords to simulate rapid brute-forcing.
3. **Validation:** Matched the hashes against target dictionary words and successfully unlocked the secure documents to verify end-to-end security auditing workflows.

---

## 🖼️ Lab Execution Highlights

### 1. Johnny GUI & JTR Engine Configuration
Verifying that Johnny automatically detects the pre-installed `/usr/sbin/john` binary inside Kali Linux[span_35](start_span)[span_35](end_span)[span_36](start_span)[span_36](end_span):
![Johnny Settings](images/01-johnny-settings.png)

### 2. Successful Password Recovery
Running a dictionary attack against the extracted `$pdf$` hash to recover the plain-text password[span_37](start_span)[span_37](end_span)[span_38](start_span)[span_38](end_span):
![Johnny Cracked Password](images/03-johnny-cracked.png)

### 3. Flag Capture Verification
Unlocking the protected document using the recovered credential to complete the challenge[span_39](start_span)[span_39](end_span)[span_40](start_span)[span_40](end_span):
![Captured Flag](images/04-flag-captured.png)

---

## 🔑 Key Security Takeaways
* **Hashing vs. Encryption:** Encryption is a reversible two-way process requiring a decryption key, whereas hashing is a one-way mathematical function that produces a fixed-length message digest for credential verification[span_41](start_span)[span_41](end_span).
* **Vulnerability of Weak Passwords:** Simple dictionary words can be cracked in seconds once an attacker obtains the underlying hash[span_42](start_span)[span_42](end_span).
* **Defense-in-Depth:** Organizations should enforce long, high-entropy passphrases, modern slow-hashing algorithms (e.g., Argon2id, bcrypt), and Multi-Factor Authentication (MFA).

---
*Projects completed as part of practical Cybersecurity & Ethical Hacking training modules[span_43](start_span)[span_43](end_span)[span_44](start_span)[span_44](end_span).*
