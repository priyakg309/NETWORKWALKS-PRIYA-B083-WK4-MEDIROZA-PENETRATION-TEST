# M2 - Data Extraction

**Goal:** Crack the encryption on all 3 retrieved PDF files.

## 🔍 Approach

Each of the 3 patient lab reports retrieved in [M1-Initial Access](../M1/) was password-protected. For each file, the process was:

1. Extract a crackable hash from the PDF using the Networkwalks Hash Calculator

2. Run a dictionary attack against that hash using the Networkwalks Password Cracker

3. Open the decrypted PDF with the recovered password

---

## Record 1 - Sipho Dlamini (patient_report_1.pdf)

Extracted the PDF's hash using the Hash Calculator:

![Hash extraction for record 1](./record1-01-hash-extraction.png)

Ran the dictionary attack - cracked on the built-in wordlist:

![Password cracked for record 1](./record1-02-password-cracked.png)

**Password:** `123456`

Opened the decrypted report:

![Decrypted report for record 1](./record1-03-decrypted-report.png)

---

## Record 2 - Priya Reddy (patient_report_2.pdf)

Extracted the PDF's hash using the Hash Calculator:

![Hash extraction for record 2](./record2-01-hash-extraction.png)

Ran the dictionary attack - cracked on the built-in wordlist:

![Password cracked for record 2](./record2-02-password-cracked.png)

**Password:** `password`

Opened the decrypted report:

![Decrypted report for record 2](./record2-03-decrypted-report.png)

---

## Record 3 - Emily Thompson (patient_report_3.pdf)

Ran the dictionary attack with the built-in 100-word list - exhausted with no match:

![Wordlist exhausted for record 3](./record3-01-wordlist-exhausted.png)

Uploaded a larger custom wordlist (`JTR_default_password.txt`, 3,556 words) and re-ran the attack - match found:

![Password cracked with expanded wordlist for record 3](./record3-02-password-cracked-expanded-wordlist.png)

**Password:** `!@#$%^&`

Opened the decrypted report:

![Decrypted report for record 3](./record3-03-decrypted-report.png)

---

## ✅Summary

| File | Password | Notes |
|---|---|---|
| patient_report_1.pdf | `123456` | Cracked on first attempt, built-in wordlist |
| patient_report_2.pdf | `password` | Cracked on first attempt, built-in wordlist |
| patient_report_3.pdf | `!@#$%^&` | Built-in wordlist insufficient; required an expanded custom wordlist |
