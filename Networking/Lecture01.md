# Network

Network devices se milkar banta hai. Jab phone, laptop, computer aur doosre devices aapas mein connect hotay hain, to wo mil kar ek network banate hain. Ye sab devices ek router ke sath connect hotay hain, aur router hi in sab ke darmiyan communication ko possible banata hai.

--- 

# Private Network

Private network us waqt banta hai jab ek router ke sath multiple devices connect hoti hain. Misal, ek ghar mein agar koi person doosre person ko data send karna chahta hai, to jab dono devices ek hi router se connect hoti hain, to wo ek private network ban jata hai. Is network ka access sirf unhi devices ko hota hai jo us specific router se connect hain — bahar ki koi device is network ka hissa nahi ban sakti.

---

# Public Network

Public network wo hota hai jab ek device internet ke through kisi doosre server ya website (jaise Google) se data mangti hai. Jab hum apne device se koi request (jaise Google par kuch search karna) bhejte hain, to ye request pehle apne router se guzar kar internet tak jati hai. Is tarah ka network jo internet ke through connect hota hai, use public network kaha jata hai.

**Private aur Public Network Diff:**
- Private network sirf ek local router ke andar limited hota hai, jismein sirf wahi devices include hoti hain jo us router se connect hain.
- Public network internet ke through duniya bhar ki services aur servers se connect hone ki facility deta hai.

Simple Rule:

Agar beech mein koi company ka server/cloud involve ho (WhatsApp, Instagram, Google, koi bhi website) → Public network

Agar data seedha ek device se doosre device tak jaye, koi server na ho (Bluetooth, AirDrop, direct WiFi-to-printer, LAN cable se do PC connect karna) → Private network

---

# MAC Address

Har device ka apna ek unique **Physical Address** hota hai jise **MAC Address** kaha jata hai. Ye address har device ke liye alag aur permanent hota hai, jaisay device ka identity card ho.

Jab bhi koi naya device router se connect hota hai, to router us device ka MAC address record kar leta hai. Router ke andar ek chhota sa **table** hota hai jisay hum "router table" keh saktay hain, jismein wo sari devices ke MAC addresses aur unke corresponding IP addresses store karta hai.

**MAC Address ka kaam:**
- Router ko pata chalta hai ke konsi device physically us se connect hai.
- Communication ke doran devices ko identify karne ke liye MAC address use hota hai.
- Router in addresses ki help se decide karta hai ke data kis device tak bhejna hai.

---

# IP Address

IP address bhi har device ko diya jata hai taake wo network par communicate kar sake. Jab bhi koi device router se connect hoti hai, router us device ko ek IP address assign karta hai.

**IP Address Assign:**

IP address assign hona ek verify hone ka process hai. Iska matlab ye hai ke jab bhi koi naya device network se connect hoti hai, router pehle us device ko verify karta hai, phir usay ek IP address deta hai.

**Example:**
Maan lein wifi ka naam "Home-WiFi" hai. Jab koi device is wifi se connect hoti hai, to router us device ka MAC address apni table mein store kar leta hai, aur us device ko ek IP address assign kar deta hai.

**DHCP (Dynamic Host Configuration Protocol):**

Ye ek aisa method hai jo IP address assign karne ka kaam automatic method se karta hai. DHCP protocol ki help se router khud b khud har naye device ko IP address de deta hai, bina kisi manual configuration ke.

**Important Point:**
IP address change ho sakta hai — yani agar device disconnect ho kar dobara connect ho, to usay naya IP address mil sakta hai. Lekin MAC address kabhi change nahi hota, wo har device ke liye fix (permanent) rehta hai.

---

# Device Connection Process

Jab koi device network mein pehli baar connect hoti hai, to us waqt uska koi fix IP address nahi hota. Jab wo device router se connect hoti hai, to router us device ka physical address (MAC address) identify karta hai aur usay apni table mein record kar leta hai.

Router in MAC addresses ki help se communication establish karta hai. Har device ko network mein alag pehchanne ke liye router IP address bhi assign karta hai, taake data sahi device tak pahunch sake.

**Router Table Ka Kaam:**
- Devices ke MAC address store karna.
- Un MAC addresses ko corresponding IP addresses ke sath maintain karna.
- Ye table communication ke doran devices ko identify karne mein router ki help karti hai.

---

# Wired && Wireless Network

Network do tareeqon se connect ki ja sakti hai — **Wired (Wire wali)** aur **Wireless (bina wire ke)**. In dono ka basic maqsad ek hi hai, yani devices ko aapas mein connect karna, lekin inka tareeqa alag hota hai.

## Wired Network

Wired network mein devices ek physical cable (jaise Ethernet cable) ke through router ya switch se connect hoti hain. Is tarah ka connection zyada stable aur fast hota hai, kyun ke data cable ke through direct transfer hota hai aur ismein signal loss ya interference ka chance kam hota hai.

**Wired Network Features:**
- Connection stable aur reliable hota hai.
- Speed zyada hoti hai, kyun ke koi signal interference nahi hota.
- Security ke lihaz se behtar hai, kyun ke bina physical access ke koi device connect nahi ho sakti.
- Nuqsan ye hai ke devices ko cable se jorna parta hai, is liye mobility limited hoti hai — device ko idhar udhar move nahi kiya ja sakta.

## Wireless Network

Wireless network mein devices bina kisi physical cable ke, radio signals (jaise Wi-Fi) ke through router se connect hoti hain. Ye connection zyada convenient hota hai kyun ke devices ko kahin bhi, router ke range ke andar, move kiya ja sakta hai.

**Wireless Network Features:**
- Devices ko cable ki zaroorat nahi hoti, is liye mobility zyada hoti hai.
- Multiple devices ek hi waqt mein aasani se connect ho sakti hain (jaise phone, laptop, tablet, etc.).
- Signal ki strength distance aur walls jaisi rukawaton se kam ho sakti hai.
- Security thori kam hoti hai wired ke muqable mein, is liye password aur encryption (jaise WPA2/WPA3) zaroori hoti hai taake koi unauthorized device connect na ho sake.

## Wired vs Wireless — Farq

- Wired network cable ke through connect hoti hai, jabke wireless network radio signals (Wi-Fi) ke through connect hoti hai.
- Wired network zyada fast aur stable hoti hai, jabke wireless network mein mobility zyada hoti hai lekin speed thori kam ho sakti hai.
- Wired network ki security zyada strong hoti hai kyun ke physical connection zaroori hai, jabke wireless network ko secure karne ke liye password aur encryption ka istemal karna parta hai. 

---

# LAN (Local Area Network)

LAN ek chhoti aur local network hoti hai jo limited area (jaise ek ghar, office, ya building) mein devices ko aapas mein connect karti hai.

**LAN Concept:**
LAN mein sari devices ek hi local network ke andar connect hoti hain, aur wo aapas mein bina internet ke bhi data share kar sakti hain. Ye network chhoti range ke liye design ki gayi hoti hai.

**Home Example:**
Ek ghar mein jitne bhi devices (phone, laptop, computer, printer, etc.) ek hi wifi router se connect hoti hain, wo sab mil kar ek LAN banate hain. In devices ke darmiyan data transfer local level par hota hai, jaisay ek computer se doosre computer ko file bhejna, ya printer ko share karna — ye sab LAN ke through mumkin hota hai.

**LAN Features:**
- Ye ek limited area (ghar, office, school) tak mahdood hoti hai.
- Devices aapas mein high speed par connect hoti hain.
- Internet ke bina bhi local devices aapas mein data share kar sakti hain.
- Security ke lihaz se private aur controlled hoti hai, kyun ke sirf authorized devices hi is network ka hissa ban sakti hain.
