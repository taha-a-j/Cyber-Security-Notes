# CIA Principle Aur AAA — Cybersecurity Basics

## CIA Triad

Cybersecurity ke basics **principles** ko **CIA** ke naam se jana jata hai. CIA ka matlab hai:

1. **Confidentiality**
2. **Integrity**
3. **Availability**

---
 
## 1. Confidentiality

**Confidentiality** ka matlab hai **identity**  ye ensure karta hai ke sirf sahi authorized banda hi kisi data tak pohanch sake.

**Example — Employee Ka Data:**
Ek **employee doosre employee ka data access nahi kar sakta** matlab har employee ki apni alag identity aur permission hoti hai, aur wo sirf apna hi data dekh sakta hai, kisi aur ka nahi.

**Confidentiality Zero Hona:**
Agar koi **account miss-use** ho jaye (matlab Kisi unauthorized person ka kisi ke account mein bina permission ke access mil jana.), to us waqt **Confidentiality "zero"** ho jati hai  matlab confidentiality ka principle poori tarah break ho jata hai.

---



## 2. Integrity

**Integrity** ka matlab hai ke **data ko change nahi hona chahiye** data hamesha **100%** apni original halat mein rehna chahiye, Bina kisi unauthorized change ke.

**Example — Student Ka Message:**
Ek **student doosre student ko message** bhej sakta hai.

**Hacker's Scenario:** Agar koi **hacker message ko hack kar le**, ya **WhatsApp hack kar ke message ko change kar de**, to is se **Integrity "0" (zero)** ho jati hai matlab **Integrity loss** ho jati hai, kyun ke data apni original shakal mein nahi raha, usay change kar diya gaya.

---



## 3. Availability

**Availability** ka matlab hai ke data ya service **hamesha available** honi chahiye jab bhi usay zaroorat ho matlab authorized users ko system ya data tak bina kisi problem ke access milna chahiye.

---



## AAA Framework

Cybersecurity mein ek aur important framework hai jise **AAA** kaha jata hai:

1. **Authentication**
2. **Authorization**
3. **Accountability**

---



## Authentication

**Authentication** ka matlab hai **identity ko authenticate karna** matlab ye confirm karna ke banda wahi hai jo wo dawa kar raha hai.

**Website Login Example:** 

Jaise koi website ka **"Authenticator"** hota hai jab hum kisi website par **login** karte hain, to system pehle ye verify karta hai ke hum wahi banda hain jo hum bata rahe hain.

**Practical Example:**
Kisi bhi **profile mein login karna** jab tak koi apni sahi identity (jaise username/password) provide na kare, tab tak wo authenticate nahi ho sakta.

---



## Authorization

**Authorization** ka matlab hai ke authenticate hone ke baad user ko **kya karne ki permission** hai.

**Normal User:**
Ek **normal user** sirf website tak **reach** kar sakta hai aur **input de sakta hai** matlab uski permissions limited hoti hain.

**Admin Example:** 

**Admin** jab website mein login karta hai, to usay zyada **authority** hoti hai admin **input dene** ke sath sath **delete, update, aur upgrade** bhi kar sakta hai.

**Authorization Difference:**

 Is tarah Authentication aur Authorization mein farq ye hai:

- **Authentication** → pehchan (identity) verify karna
- **Authorization** → verify hone ke baad kya karne ki ijazat milegi, ye decide karna

---



## Accountability

**Accountability** ka matlab hai ke system ke andar hone wali har **activity ka record rakha jaye**, taake baad mein pata chal sake ke kis ne kya kiya.

**Example:** 

**3 Students, Alag Modules:** Agar **3 students** ho aur har ek **alag module cover** kar raha ho, to **different activities** hoti hain.

**Cybersecurity Mein Activities Ka Record:**
**Cybersecurity mein** jitni bhi **activities perform** ki jati hain, un sab ki **logs** save ki jati hain taake baad mein verify kiya ja sake ke kya hua tha.

**Example — Account Hack:** Agar kisi ka **account hack** ho jaye ya us se **misuse** ho, to **Accountability** ke through pata chalta hai ke exact us waqt kya activity hui thi aur kis ne wo activity ki thi is se responsibility fix karna asan ho jata hai.

---



## Summary

**CIA Triad:**

1. **Confidentiality** → sirf sahi banda hi data access kar sake; agar account misuse ho, to confidentiality zero ho jati hai
2. **Integrity** → data 100% original rahe, bina change ke; agar hack ho ya data change ho, to integrity zero/loss ho jati hai
3. **Availability** → data/service hamesha zaroorat ke waqt available ho

**AAA Framework:**

1. **Authentication** → identity verify karna (jaise login karna)
2. **Authorization** → verify hone ke baad kya permissions milengi (normal user vs admin)
3. **Accountability** → har activity ka record/log rakhna, taake baad mein pata chal sake ke kis ne kya kiya

**Authentication Vs Authorization:**

- Authentication → "Tum kaun ho?" ye confirm karna
- Authorization → "Tumhe kya karne ki ijazat hai?" ye decide karna

**Accountability Benefits:**

- Agar account hack ho ya koi misuse ho, to logs ke through exact activity aur responsible banda pata chal sakta hai

