# Introduction

**Tester(s):**  
- Name: Santeri Saari 

**Purpose:**  
- The purpose of this test was to locate faults in the user authorization process.

**Scope:**  
- Tested components:  Authorization
- Exclusions:  GDPR compliance, other site functionality
- Test approach: Gray-box

**Test environment & dates:**  
- Start: 16.12.1025
- End: 18.12.2025
- Test environment details: Kali Linux VM, using Docker Engine. Chromium browser via Burp Suite/Firefox with ZAProxy.

### **Specs**
The system is accessed via a web browser.
Users can register and, after registration, log in to the system.
A registered and logged-in user acts as either a resource reserver or an administrator.
The administrator can add, remove, and modify resources and reservations.
The administrator can delete the reserver.
A reserver can book a resource if they are over 15 years old.
Resources can be booked on an hourly basis.
The booking system displays booked resources without requiring login, but does not show the reserver's identity

---
### **Discovered links and endpoints**

localhost:8003
localhost:8003/login
localhost:8003/resources
localhost:8003/register
localhost:8003/reservation
localhost:8003/reservation?id=*
localhost:8003/api/resources
localhost:8003/api/reservations
localhost:8003/api/users

wfuzz did not discover URLs or endpoints that hadn't been manually discovered.

---
### **Observations**
Backup correctly enforces authorization except when accessing API endpoints, BurpSuite shows that the site wants to show the Not Found status page but is overridden by the actual page showing, even to Guests.
Site database has a table for admin logs yet there exists no admin panel or other way to generate these logs.
Resources API can be flooded by programs like ZAP in attack mode with code, commands and other garbage data.


---

### **Guest**

---

**✅ Can do**

* Can view booked resources at /
* Can access /login
* Can access /register
* Can access /resources and list a resource successfully
* Can view /api/reservations
* Can view /api/resources
* Can view /api/users
* Cannot see the identity of the reserver when viewing booked reservations at / (spec 8)

---

**❌ Cannot do**

* Can't access /reservation, shows the unauthorized page.
* Can't create an account that is under 15 years of age (spec 6)

---

### **Reserver**

---

**✅ Can do**

* Can book a resource at /reservation and view /api/reservations
* Can list resources at /resources
* Can edit own reservations and others by changing reserver username in form
* Can view api/users and api/resources
* Can start reservations in the past


---

**❌ Cannot do**

* Cannot modify resources (spec 4)
* Reservation end date cannot precede start date
* No useful hidden form fields exist for bypassing priviledge restrictions

---

### **Administrator**

---

**✅ Can do**

* Can add a resource via /resources
* Can view all users via /api/users
* Can access all endpoints and pages
* Can edit both own and others reservations
* Can delete a reservation

---

**❌ Cannot do**

* Can't delete a reserver⚠️
* Can't delete a resource, shows error⚠️
* No existing admin control panel ⚠️
* No meaningful ability to interact with api endpoints ⚠️

---
