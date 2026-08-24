# Data, Frontend-Backend & Firewall

## Data Kya Hai

**Data** **text, call, ya document** ki shakal mein ho sakta hai — ye computer ko as a **input** diya jata hai.

**Data Working:**
- Data ko **display** karne ke liye use kiya jata hai
- Data ko **store** karne ke liye use kiya jata hai

**Website Ka Example:**
Isi tarah **websites** bhi data **store** karti hain — jab koi website kaam karti hai, to us mein bhi data store aur display hone ka yehi process hota hai.

---

## Frontend & Backend

### Frontend
**Frontend** ko **human body** jaisa samjho — jaise insaan ka body wo hissa hai jo **dikhta** hai aur jis se log interact karte hain, waise hi frontend wo hissa hai jo user ko website par **nazar aata** hai.

### Backend
**Backend** **server aur host** hota hai — matlab wo hissa jo peeche (background) mein kaam karta hai aur data ko manage karta hai, lekin user ko seedha nazar nahi aata.

**Frontend & Backend Relation:**
**Frontend** se ek **request** **backend** tak jati hai. Jab user frontend par koi action leta hai jaise button click karna, to us waqt ek **request generate** hoti hai jo backend tak pohanchti hai.

**Handshake Example:**
Ye poora process ek **handshake** ki tarah kaam karta hai matlab frontend aur backend ke darmiyan communication ek logical tareeqe se hoti hai, jaisa network handshake mein hota hai.

---

## Firewall

**Firewall** ek aisi cheez hai jo **antivirus** ki tarah kaam karti hai matlab ye system ko surakshit (protect) karne ke liye use hoti hai.

### Firewall 2 Types

Firewall **2 forms** mein aata hai:
- **Software Firewall**
- **Hardware Firewall**

---

## Firewall Working

**Real-Life Analogy Room Ka Example:**
Samjho jaise ek **room** hai. Agar us room mein **firewall na ho**, to koi bhi asani se andar **enter** ho sakta hai. Lekin agar **firewall ho**, to us room mein dakhil hone ke liye pehle **rules follow** karne parte hain.

### Firewall Is a Bouncer

**Firewall ko "bouncer" samjho** jaise kisi club ya event ke bahar bouncer khada hota hai jo check karta hai ke kisay andar jane dena hai aur kisay nahi, waise hi firewall bhi network traffic ko check kar ke decide karta hai ke kisay allow karna hai aur kisay block karna hai.

**Example — 3 Devices:**
Agar **3 devices** hon, aur ek **router se request** aaye, to us request ko **firewall** check karta hai firewall ye dekhta hai ke request kis **IP** se aa rahi hai aur kis **port** se guzar rahi hai, us ke baad hi request ko pass hone diya jata hai.

**Example:**
**Office time** ke doran agar YouTube **open nahi hoti**, to iski wajah **firewall ke rules** hote hain matlab organization ne apne firewall mein aisa rule set kiya hota hai jo specific websites ko block kar deta hai office hours mein.

---

## Firewall Rules Allow Ya Block

Firewall ke **rules** ye decide karte hain ke kisi request ko **allow** krna hai ya **block** krna hai.

**Example — Allow Karna:**
```
Allow Port 88
Allow Port 443, 444
```

Ye ports agar **allow** kiye gaye hon, to un ports se aane wali requests ko firewall guzarne deta hai.

---

## Port Block Karna

**Port Block:**
Firewall specific **ports** ko bhi **block** kar sakta hai matlab agar koi port block hai, to us port se aane wali koi bhi request pass nahi ho sakti.

**ACL — Access Control List**
**ACL (Access Control List)** ek aisi list hoti hai jo ye define karti hai ke konsi requests **allow** hongi aur konsi **block** hongi ye firewall ke rules ka ek organized set hota hai.

**Network Layer Par Firewall:**
Firewall **network layer** par kaam karta hai matlab ye network ke andar aane jane wali traffic ko is layer par control karta hai.

### Firewall Ke Rules Example

**Rule:** Jo bhi request **port 0** ke opar upar ho, wo **block** kar di jati hai.

**Example:**
```
Port 443 → Allow
Port 23 (Insecure/Unencrypted) → Request allow nahi honi chahiye
```

**Matlab:** Port `443` (jo secure hai, HTTPS ke liye) allow hai, lekin port `23` (jo insecure/unencrypted hai) se aane wali requests ko allow nahi karna chahiye, kyun ke ye secure nahi hoti.

---

## Common Port Numbers

**Common Ports** & associated services:

- **Port 20** → **FTP Data** (File Transfer Protocol — Data transfer ke liye)
- **Port 21** → **FTP Control** (File Transfer Protocol — Control commands ke liye)
- **Port 22** → **SSH** (Secure Shell — remote login ke liye, secure)
- **Port 23** → **Telnet** (Not Secure — ye port secure nahi hota)
- **Port 25** → **SMTP** (Simple Mail Transfer Protocol — email bhejne ke liye)
- **Port 53** → **DNS** (Domain Name System — website names ko IP mein convert karta hai)
- **Port 80** → **HTTP** (websites ke liye, unencrypted)
- **Port 443** → **HTTPS** (websites ke liye, encrypted/secure)
- **Port 3306** → **MySQL** (database ke liye)
- **RDP** → Remote Desktop Protocol (remote access ke liye)

**Port Security Ka Usool:**
Jo **ports secure nahi** hote, unhe **close** kar diya jata hai, aur jo **secure** hote hain unhe **open** rakha jata hai.

**Firewall Kaise Chalta Hai:**
Firewall **ACL Rule** ke through chalta hai matlab firewall **apni marzi se nahi** chalta, balke wo hamesha ek **"Rule Book"** ke hisab se chalti hai, jis mein pehle se define kiya gaya hota hai ke kya allow hai aur kya block hai.

---

## Firewall Rule Table

 **Protocol, Port, Source IP, aur Action (Allow/Block)** par mabni hote hain:

**Rule 1:**
Protocol: **UDP**, Port: **23**, Source IP: **192.168.1.10** → **Not Allowed**

**Rule 2:**
Protocol: **TCP**, Port: **88**, Source IP: **192.168.1.10** → **Allowed**

**Rule 3:**
Protocol: **TCP**, Port: **3306**, Source IP: **192.168.1.10** → **Not Allowed**

**In Order — Top to Bottom:**
Firewall in rules ko **top to bottom** ke order mein **check** karta hai matlab pehla rule sab se pehle check hota hai, phir doosra, aur is tarah aage badhta hai jab tak koi matching rule na mil jaye.

---

## Stateless Firewall **bhoolne wala**

**Stateless Firewall** wo firewall hai jo har request ko **individually alag alag** check karta hai, bina kisi pichli connection history ko dekhe.

**Example:**
Agar koi **request google.com** ko **port 80** par bheji jaye, aur us ka **random reply port 49532** par aaye, to Stateless Firewall **connection ka 3-way handshake dekh kar** decide karta hai ke request ko allow karna hai ya block.

**Working Principle:**
Stateless firewall har packet ko independent tarah se dekhta hai ye pichle packets ki state ya history track nahi karta.

---

## Stateful Firewall **yaad rakhne wala**

**Stateful Firewall** wo firewall hai jo **connection ki state halat** ko track karta hai matlab pehle packet se lekar poori connection tak, sab kuch record rakhta hai.

**First Packet:**
Jab **pehli baar WiFi se connect** kiya jata hai, to us waqt firewall check karta hai ke konse **ports open** hain jin mein **malicious activities** doondi ja sakti hain.

**Connection Establish Process:**
Jab koi **connection establish** karta hai, to Stateful Firewall us poori connection ki state ko yaad rakhta hai taake aage aane wale packets ko is history ke hisab se allow ya block kiya ja sake. 

**Stateful Vs Stateless — Differ:**
- **Stateless Firewall:** Har packet ko **individually** check karta hai, koi history yaad nahi rakhta
- **Stateful Firewall:** Connection ki **poori state** yaad rakhta hai aur us history ke basis par decisions leta hai

---

## Summary

**Data & Frontend-Backend:**
- Data → text, call, document (input ke roop mein)
- Frontend → jo user ko dikhta hai (human body jaisa)
- Backend → server/host, jo peeche kaam karta hai
- Frontend se request backend tak jati hai

**Firewall Basics:**
- Firewall antivirus ki tarah system ko protect karta hai
- 2 types: Software Firewall, Hardware Firewall
- Firewall ko "bouncer" samjha ja sakta hai jo traffic control karta hai

**Firewall Rules:**
- ACL (Access Control List) rules define karti hai
- Firewall network layer par kaam karta hai
- Insecure ports (jaise 23) allow nahi hone chahiye
- Secure ports (jaise 443) allow hote hain

**Common Ports:**
- 20 → FTP Data
- 21 → FTP Control
- 22 → SSH
- 23 → Telnet (Not Secure)
- 25 → SMTP
- 53 → DNS
- 80 → HTTP
- 443 → HTTPS
- 3306 → MySQL
- RDP → Remote Desktop Protocol

**Firewall Rule Checking:**
- Rules top-to-bottom order mein check hote hain
- Har rule mein Protocol, Port, Source IP, aur Action (Allow/Block) hote hain

**Stateless Vs Stateful Firewall:**
- Stateless → har request individually check hoti hai, history track nahi hoti
- Stateful → connection ki poori state track hoti hai, first packet se le kar connection establish hone tak
`