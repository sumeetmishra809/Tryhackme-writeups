# TryHackMe – Corridor Walkthrough

## 🧠 Room Overview

**Room Name:** Corridor – Can You Escape?
**Platform:** TryHackMe
**Difficulty:** Easy

---

## 🎯 Objective

The goal of this room is to analyze the web application and identify a method to retrieve the hidden flag by exploiting weaknesses in how resources are referenced.

---

## 🔍 Key Learning Outcomes

* Understanding **Insecure Direct Object Reference (IDOR)** vulnerabilities
* Identifying and analyzing **hashed values** within web applications
* Recognizing **predictable patterns** in application logic
* Applying basic **hash cracking techniques**

---

## ⚙️ Methodology

1. **Application Analysis**

   * Inspected the webpage using browser developer tools
   * Identified multiple hashed values embedded within the HTML source

   <img width="1263" height="494" alt="room1" src="https://github.com/user-attachments/assets/9859ca67-8181-4d97-b264-6f4128822c2c" />

2. **Pattern Recognition**

   * Observed that the hashes were being used as part of URL paths
   * Hypothesized that these hashes might correspond to predictable inputs such as numeric IDs

3. **Hash Cracking**

   * Used an online hash-cracking tool to decode the identified hashes
   * Successfully mapped hashes back to their original values

   <img width="1266" height="643" alt="room2" src="https://github.com/user-attachments/assets/9cd79b32-8546-4ea2-9627-e0c1016ce6d4" />

4. **Verification Using Local Hashing**

   * Verified the hash for a known value (`0`) using a local command:

   ```bash
   echo -n "0" | md5sum
   ```

   * Compared the generated hash with the values observed in the application to confirm the pattern

5. **Exploitation**

   * Iterated through the decoded values
   * Navigated through corresponding endpoints
   * Identified the correct path leading to the flag

---

## 🛠 Tools Utilized

* Browser Developer Tools
* Online Hash Cracking Tool
* Linux Command Line (md5sum)

---
 
```

---

## 📌 Key Takeaway

This exercise highlights how improper handling of object references can lead to **IDOR vulnerabilities**. Even when data is hashed, predictable patterns and lack of access control can allow attackers to enumerate resources and gain unauthorized access.

---

## 🔗 Room Link

https://tryhackme.com/room/corridor
