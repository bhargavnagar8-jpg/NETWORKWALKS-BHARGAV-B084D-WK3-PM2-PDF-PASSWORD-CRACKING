# 🔐 NETWORKWALKS-BHARGAV-B084D-WK3-PM2-PDF-PASSWORD-CRACKING

![Status](https://img.shields.io/badge/Status-Completed-brightgreen) ![Week](https://img.shields.io/badge/Week-3-blue) ![Task](https://img.shields.io/badge/Task-PM2-orange) ![Batch](https://img.shields.io/badge/Batch-B084D-lightgrey)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/bhargav-nagar-892a54447/) [![GitHub](https://img.shields.io/badge/GitHub-Profile-black?logo=github)](https://github.com/bhargavnagar8-jpg)

Week 3 submission for the **Networkwalks Cybersecurity Internship** (`#Waqaskarim`) — cracking password‑protected PDF files with **John the Ripper (Johnny GUI)** and the Networkwalks **NW Tools Lab (WK3‑PM2)**.

> 📌 Cracked password-protected PDFs using John the Ripper (Johnny GUI) and Networkwalks' Hash Calculator + Dictionary Attack Lab — Week 3 cybersecurity internship task (WK3-PM2).

## 👤 Author
| | |
|---|---|
| **Name** | BHARGAV NAGAR |
| **Batch** | B084D |
| **Week** | Week 3 Pdf Password Cracking |
| **Program** | Networkwalks Cybersecurity Internship (#Waqaskarim) |
| **LinkedIn** | (https://www.linkedin.com/in/bhargav-nagar-892a54447/) |
| **GitHub** | (https://github.com/bhargavnagar8-jpg) |

---

## 📖 Table of Contents
- [Author](#-author)
- [Objective](#-objective)
- [Working Environment](#-working-environment)
- [Tools Used](#️-tools-used)
- [Repository Structure](#-repository-structure)
- [Steps Performed](#-steps-performed)
- [Results](#-results)
- [What I Learned](#-what-i-learned)
- [Screenshots](#-screenshots)
- [Ethical Considerations](#-Ethical-Considerations)
- [Disclaimer](#-Disclaimer)

---

## 🎯 Objective
- Extract a crackable hash from a password‑protected PDF.
- Run a dictionary/wordlist attack to recover the original password.
- Use the recovered password to unlock the PDF and capture the flag.
- Compare doing this with the **real John the Ripper tool** against the **Networkwalks web‑based simulator** that mimics the same logic.

## 💻 Working Environment

| Component | Details |
|---|---|
| Host OS | Windows 10/11 |
| Cracking tool | John the Ripper **1.9.0‑jumbo‑1** (Cygwin 64‑bit, x86_64, OMP + AVX2‑AC build) |
| GUI front‑end | Johnny (bundled with the JtR Jumbo Windows build) |
| Hash extraction | [Online Hash Crack – PDF Hash Extractor](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php) *(pdf2john‑compatible output)* |
| Simulation tools | Networkwalks **Hash Calculator** + **Dictionary Attack Lab** (web‑based) |
| Browser | Microsoft Edge |
| PDF viewer | Microsoft Edge PDF viewer / Adobe Acrobat |
| Text editor | Notepad‑style editor for saving `.txt` hash files |

## 🛠️ Tools Used
- **John the Ripper (Jumbo build)** + **Johnny** — the actual offline password‑cracking engine and its GUI.
- **pdf2john**‑style hash extraction — converts an encrypted PDF into a crackable `$pdf$...` hash.
- **Networkwalks Hash Calculator** — a browser‑based equivalent of `pdf2john`, used for the official WK3‑PM2 lab file.
- **Networkwalks Dictionary Attack Lab** — a visual simulator that walks through a wordlist exactly like John the Ripper does, word‑by‑word.

## 📁 Repository Structure
```
NETWORKWALKS-<YOUR-NAME>-B084D-WK3-PM2-PDF-PASSWORD-CRACKING/
├── README.md
└── screenshots/
    ├── 01-johnny-settings-setup.png
    ├── 02-hash-extraction-pdf1-onlinehashcrack.png
    ├── 03-hash1-saved-as-txt.png
    ├── 04-johnny-cracked-password-good-luck.png
    ├── 05-flag1-captured-pdf1.png
    ├── 06-hash2-saved-as-txt.png
    ├── 07-johnny-cracked-password-password1.png
    ├── 08-flag2-captured-pdf2.png
    ├── 09-hash3-saved-as-txt.png
    ├── 10-johnny-cracked-password-1qaz2wsx.png
    ├── 11-flag3-captured-pdf3.png
    ├── 12-nw-hash-calculator-wk3-pm2.png
    ├── 13-nw-dictionary-attack-lab-cracked.png
    ├── 14-pdf-password-entry-wk3-pm2.png
    └── 15-flag4-wk3-pm2-captured.png
```

## 🧩 Steps Performed

### Part 1 — Cracking locked PDFs with John the Ripper (Johnny GUI)
1. **Set up Johnny** by pointing it to the John the Ripper Jumbo executable (`john.exe`) — Johnny auto‑detected *John the Ripper 1.9.0‑jumbo‑1 OMP [Cygwin 64‑bit x86_64 AVX2 AC]*.
2. **Extracted the hash** of each locked PDF (`$pdf$...` format) using the Online Hash Crack PDF Hash Extractor — this produces the same output `pdf2john` would.
3. **Saved each hash** to its own text file (`hash1.txt`, `hash2.txt`, `hash3.txt`).
4. **Loaded each hash file** into Johnny via *Open password file*.
5. **Ran a dictionary attack** (*Start new attack*) until Johnny reported a match.
6. **Opened the PDF** with the cracked password and captured the flag shown on the confirmation page.

### Part 2 — NW Tools Lab (WK3‑PM2)
1. Uploaded the official lab file `My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` to the Networkwalks **Hash Calculator** and extracted its `$pdf$...` hash (Revision R4, Version V4, 128‑bit key).
2. Pasted that hash into the Networkwalks **Dictionary Attack Lab**, which works through a wordlist the same way John the Ripper does internally.
3. The simulator matched the password **`password1`** after trying 91 of 100 candidate words.
4. Opened the PDF with the recovered password and captured the final flag.

## 📊 Results

| # | Source | Hash file | Cracked password | Flag captured |
|---|---|---|---|---|
| 1 | Locked PDF 1 (Johnny/JtR) | `hash1.txt` | `good-luck` | `nw{cybersecurity_flag_captured_2608}` |
| 2 | Locked PDF 2 (Johnny/JtR) | `hash2.txt` | `password1` | `nw{networkwalks_persistence_jtr_270521}` |
| 3 | Locked PDF 3 (Johnny/JtR) | `hash3.txt` | `1qaz2wsx` | `nw{networkwalks_flag_260821_1}` |
| 4 | WK3‑PM2 Lab PDF (NW Tools Lab) | *(web tool)* | `password1` | `nw{networkwalks_flag1_jtr_270521_1}` |

**4/4 PDFs successfully cracked — 4/4 flags captured. ✅**

## 📚 What I Learned
- **How a PDF password actually gets attacked** — the password itself is never "stored" in the PDF; instead a hash derived from it is extracted (`pdf2john`/Hash Calculator) and attacked offline, which is why the original file is never modified during the attempt.
- **Dictionary attacks succeed because people reuse weak passwords** — every password cracked this week (`good-luck`, `password1`, `1qaz2wsx`) is a well‑known top‑100 password; none required brute force.
- **Speed vs. wordlist quality matters more than raw power** — the simulator cracked the WK3‑PM2 password in 91/100 tries at just 9 passwords/sec, reinforcing that a *good* wordlist beats a *fast* but blind brute‑force attempt.
- **Johnny is just a GUI wrapper** — all the real work happens in `john.exe`; the GUI simply manages the password file, attack mode, and progress/output for you.
- **Real tool vs. simulator, same underlying logic** — repeating the exercise once with the actual John the Ripper binary and once with Networkwalks' browser simulator made it clear both follow the identical hash‑then‑match workflow.
- **Why this matters defensively** — as a future security analyst, this is the exact technique I'd use (with authorization) to audit whether an organization's documents are protected with strong, non‑dictionary passwords.

## 📸 Screenshots

### Part 1 — John the Ripper (Johnny GUI)

**1. Johnny pointed to the John the Ripper executable**
![Johnny settings setup](screenshots/01-johnny-settings-setup.png)

**2. Hash extracted from locked PDF 1 (Online Hash Crack)**
![Hash extraction PDF1](screenshots/02-hash-extraction-pdf1-onlinehashcrack.png)

**3. Hash saved as `hash1.txt`**
![Hash1 saved](screenshots/03-hash1-saved-as-txt.png)

**4. Johnny cracks the password → `good-luck`**
![Johnny cracked good-luck](screenshots/04-johnny-cracked-password-good-luck.png)

**5. 🚩 Flag 1 captured**
![Flag 1 captured](screenshots/05-flag1-captured-pdf1.png)

**6. Hash saved as `hash2.txt`**
![Hash2 saved](screenshots/06-hash2-saved-as-txt.png)

**7. Johnny cracks the password → `password1`**
![Johnny cracked password1](screenshots/07-johnny-cracked-password-password1.png)

**8. 🚩 Flag 2 captured**
![Flag 2 captured](screenshots/08-flag2-captured-pdf2.png)

**9. Hash saved as `hash3.txt`**
![Hash3 saved](screenshots/09-hash3-saved-as-txt.png)

**10. Johnny cracks the password → `1qaz2wsx`**
![Johnny cracked 1qaz2wsx](screenshots/10-johnny-cracked-password-1qaz2wsx.png)

**11. 🚩 Flag 3 captured**
![Flag 3 captured](screenshots/11-flag3-captured-pdf3.png)

### Part 2 — NW Tools Lab (WK3‑PM2)

**12. Networkwalks Hash Calculator extracts the WK3‑PM2 hash**
![NW Hash Calculator](screenshots/12-nw-hash-calculator-wk3-pm2.png)

**13. Dictionary Attack Lab cracks the password → `password1`**
![Dictionary attack lab cracked](screenshots/13-nw-dictionary-attack-lab-cracked.png)

**14. Entering the recovered password into the PDF**
![PDF password entry](screenshots/14-pdf-password-entry-wk3-pm2.png)

**15. 🚩 Final flag captured (WK3‑PM2)**
![Flag 4 captured](screenshots/15-flag4-wk3-pm2-captured.png)

---
*Submitted as part of the Networkwalks Cybersecurity Internship — Batch B084D — Week 3, PM2.*
*Tagging [@Networkwalks](https://www.linkedin.com/company/networkwalks) & [@Waqas Karim CCIE](https://www.linkedin.com/in/waqaskarim) — `#Networkwalks`*

## References ##
John the Ripper (official): https://www.openwall.com/john/
Johnny (official): https://openwall.info/wiki/john/johnny
NetworkWalks Academy: https://www.networkwalks.com/

## Ethical Considerations ##
This project was carried out strictly for educational purposes, as part of an authorized NetworkWalks Cybersecurity training exercise in a controlled lab environment.
Intended for learning password-security concepts and authorized security testing only.
Not intended to encourage or assist cracking passwords on files, accounts, or systems you do not own or have explicit permission to test.
Password auditing should always be performed responsibly, with proper authorization.

## Disclaimer ##
This repository documents a training lab exercise completed as part of NetworkWalks Academy's cybersecurity coursework. It is shared for educational and portfolio purposes only and does not constitute professional penetration-testing services or endorse unauthorized password recovery of any kind.

## 🔗 Connect with Me
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bhargav-nagar-892a54447/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/bhargavnagar8-jpg)

⭐ If you found this walkthrough useful, feel free to star the repo!
