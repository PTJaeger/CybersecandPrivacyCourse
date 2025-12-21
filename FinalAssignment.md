### *CyberSec Course Final Assignment* ###

---
## 1️⃣**PortSwigger** ##
<img width="800" height="600" alt="DashboardScS" src="https://github.com/user-attachments/assets/9335ce05-a57d-4a0b-a887-1a0d03767fd5" />

List of labs done:
1.SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

2.SQL injection vulnerability allowing login bypass

3.SQL injection attack, querying the database type and version on Oracle

4.SQL injection attack, querying the database type and version on MySQL and Microsoft

5.SQL injection attack, listing the database contents on non-Oracle databases

6.Reflected XSS into HTML context with nothing encoded

7.Stored XSS into HTML context with nothing encoded

8.DOM XSS in document.write sink using source location.search

9.DOM XSS in innerHTML sink using source location.search

10.DOM XSS in jQuery anchor href attribute sink using location.search source

11.DOM XSS in jQuery selector sink using a hashchange event

12.Reflected XSS into attribute with angle brackets HTML-encoded

13.File path traversal, simple case

14.Unprotected admin functionality

15.Unprotected admin functionality with unpredictable URL

16.User role controlled by request parameter

17.User role can be modified in user profile

18.Username enumeration via different responses

19.2FA simple bypass

20.Password reset broken logic


---
## 2️⃣**Booking System Project** ##

***1. Phase 1***<br>
What took the most time with Phase 1 was setting up the test environment and fixing all the little issues with it and the VM. ZAProxy active scans tended to freeze the VM completely so I had to alter the VBox settings to give it far more resources.<br>
What worked fine was getting Docker and the compose files up and running, no real issues during the entire project.<br>
Learned the role and usage of tools like ZAP and how to set up Docker on Linux.<br>
***2. Phase 2***<br>
What took the most time here was the experimental bruteforcing attempts.<br>
Cracking most of the passwords using hashcat worked well, though getting it to read the wordlist file properly was more involved that it needed to be.<br>
Learned about the general process of password cracking and using tools like hashcat.<br>
***3. Phase 3***<br>
Writing the report took the longest as there were many things to try and keep track of.<br>
Using wfuzz to sniff for hidden sites and endpoints was straightforward, though unnecessary as I had found all endpoints in browser testing manually.<br>
Learned about the general workflow on this type of pentesting and using wfuzz.<br>
***4. Phase 4***<br>
What took the longest here were the policy files, even with AI assistance.<br>
Doing the checklist was simple if not a bit unsure due to the limits of the booking system project.<br>
Learned about what sort of rules sites have to enforce and follow for GDPR compliance.<br>
***Reflection***<br>
Overall I feel like I gained quite a lot of insight and knowledge on how pentesting is done and what tools are used by both hackers and security experts, and how not to code and design web apps and sites. Along with that I am also even more aware of the fact that most web applications and sites are still likely highly insecure.<br>
I certainly look at websites I visit with different eyes now. Learning a bit on how to better use Kali Linux was also a boon.

## 3️⃣**Logbook** ##
---
https://github.com/PTJaeger/CybersecandPrivacyCourse/

***Total hours spent: 64 hours***

Per subject:<br>
| Subject | Hours |
|:---     | :---: |
|Netacad course | 5 |
|Repo setup | 1 |
|PortSwigger labs | 25 |
|Phase 1 | 9 |
|Phase 2 | 6 |
|Phase 3 | 8 |
|Phase 4 | 8 |
|Final assignment | 2 |
---

