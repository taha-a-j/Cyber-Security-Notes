# ARP — Address Resolution Protocol

## ARP Kya Hai

**ARP (Address Resolution Protocol)** ek protocol hai jo **IP Address** ko **MAC Address** ke sath **resolve match** karne ke liye use hota hai.

**IP Address Aur MAC Address:**
- **IP Address** → device ki network ke andar identity
- **MAC Address** → **NIC (Network Interface Card)** ka permanent address, jo har device ke hardware ke sath connent hota hai

---

## ARP Ki Zaroorat Kyun Hoti Hai

**Practical Scenario:**
Agar **router** par **5 devices connect** hon, to har device ko apna **IP address pata hota hai**, lekin usay doosre devices ka **MAC address pata nahi hota**.

**ARP Ka Kaam:**
Agar kisi device ko **MAC address pata karna ho**, to us ke liye **ARP** use hota hai.

**ARP Limitation:**
ARP sirf ek **house (ghar/local network) ke andar** use ho sakta hai — **out of house (bahar ke network mein)** ye kaam nahi karta. Matlab ARP sirf **local area network (LAN)** ke andar hi kaam karta hai.

---

## Example

**Real-Life Analogy:**
Humein pata hota hai ke hamare **dost 132 Street** (jo IP address ki tarah hai) par rehte hain, lekin humein ye nahi pata ke wo us building ke **Apartment 4B** (jo MAC address ki tarah hai) mein rehte hain.

Is tarah IP address hamein sirf "kaunse street" (network) tak le jata hai, lekin exact device (apartment/MAC) tak pohanchne ke liye ARP ki zaroorat parti hai.

---

## Data Kaise Send Hota Hai (Laptop Se Mobile Tak)

Jab **laptop se mobile** tak data **send (signal)** karna ho, to:

**Data Send Hone Ke Liye Zaroori Cheezein:**
Data send karne ke liye **MAC address aur IP** dono ki zaroorat hoti hai.

**Pata Chalne Ka Method:**
- **IP address** pehle se hi **pata chal jata hai**
- **MAC address (ARP) ke through pata chalta hai**

**Header Mein Shamil Cheezein:**
Data packet ke header mein ye information hoti hai:
- **Source IP**
- **Destination IP**
- **Source MAC Address**
- **Destination MAC Address**

---

## ARP Request Kaise Hoti Hai

**Request Purposez:**
ARP request **MAC address** ke liye hoti hai jab kisi device ko **target ka IP pata hota hai** lekin uska **MAC address pata nahi hota**, to wo device ARP request bhejta hai.

**Scenario:**
Target device ka **IP pata hai**, lekin uska **MAC address pata nahi**. Is liye device ek **packet send karta hai** taake pata chal sake ke **router par konsa device connect hai** jo us IP se match karta hai.

**Request Ka Wording:**
Ye request kuch is tarah hoti hai: **"I'm looking for..."** matlab device network mein sabko puchta hai ke "mujhe is IP wale device ka MAC address chahiye."

---

## Target Device Reply

Jis device ka **IP address match** hota hai, wo apna **MAC address bhej deta hai**.

**Response Wording:**
Target device reply deta hai: **"That's me! My MAC address is..."** matlab wahi device jawab deta hai jis ka IP match hua ho.

---

## Router & Switch Role

**Router/Switch Se Poochna:**
Router ya **switch se bola jata hai** ke "ye MAC address kis device ka hai, use dhoond kar do."

**Switch Working:**
**Switch** se ye request **bhej di jati hai** agar **5 devices connect** hon, to switch un sab tak ye request **bhej deta hai**.

**Reply Packet:**
Sirf sahi device se **reply packet aata hai** baaki devices koi response nahi bhejte, kyun ke unka IP match nahi hota.

---

## Broadcast

ARP request sab devices ko ek sath **bhej di jati hai**, is process ko **Broadcast** kaha jata hai.

**Broadcast Working:**
Jis bhi device ka **IP match hota hai**, wo hi apna **MAC address wapas bhejta hai** baaki sari devices is request ko **ignore** kar dete hain kyun ke unka IP match nahi hua hota.

---

## ARP Kaise Kaam Karta Hai — One Way Ya Two Way

**Data Ya Request Reply:**
Data ya request ka jawab **ek tareeqe (one way)** mein ho sakta hai, ya phir **ek device se doosre device tak** (matlab do devices ke darmiyan) ho sakta hai.

**Unicast:**
Jab response sirf **ek specific device** ko bheja jata hai (na ke sab ko), to isay **Unicast** kaha jata hai matlab broadcast ke baad jab sahi device jawab deta hai, to wo jawab sirf us device (jisne request ki thi) tak jata hai, unicast tareeqe se.

---

## arp -a Command

**arp -a** ek command hai jo device ki **ARP table** ko dikhane ke liye use hoti hai is mein wo saari entries hoti hain jo device ne pehle se **cache (yaad)** ki hui hoti hain.

---

## Real Mapping & App Cache Table

**Real Mapping:**
Ye ek question hai ke kya ye mapping **real** hoti hai matlab kya IP aur MAC address ka relation hamesha sahi accurate rehta hai.

**App Cache Table:**
Device ke andar ek **cache table** hoti hai jis mein **MAC address cache (store)** hota hai. Is data se pata chalta hai ke **konsi IP** par **konsa MAC address** hai taake baar baar ARP request na karni pare.

**IP Neigh Command:**
```
ip neigh
```
Ye command bhi network ke neighboring devices ki IP aur MAC address mapping dikhane ke liye use hoti hai.

---

## ARP Kab Use Hota Hai

**Question — Ye Kis Application Mein Hota Hai?**
ARP ka use tab hota hai jab ye poochna ho ke **"ARP kab hota hai?"** matlab konse specific waqt par ye process trigger hota hai.

### DHCP Connention

Jab **DHCP** ke through ek **IP address kisi device ko assign** hoti hai, to us waqt bhi ARP involved hota hai.

**Manual IP Assignment Mistake:**
Agar **manually IP assign** ki jaye, to is se **mistake (ghalti) hone ke chances** hote hain jaise agar galti se do devices ko same IP assign ho jaye, to ye conflict paida karta hai. Isi wajah se automatic (DHCP) method zyada reliable hota hai.

---

## ARP Spoofing Attack

**ARP Spoofing?:**
**ARP Spoofing Attack** ek aisa attack hai jis mein network mein **fake device show kiya jata hai** matlab attacker khud ko ek asli device (jaise router) ki tarah show karta hai.

**Attack Method:**
Attacker **router se identity exchange** kar ke khud ko router ki tarah **show karwata hai**.

**Devices Involved:**
```
Laptop, Mobile — WiFi, Switch, Router
```

**Attack Kaise Kaam Karta Hai:**
Normal method mein, jab **laptop se data send** karna ho, to wo pehle **router ke pass jata hai**, phir **mobile tak pohanchta hai**. Lekin ARP Spoofing Attack mein, attacker khud ko **"middle man"** bana leta hai.

**Middle Man Attack:**
Attacker **router** ko yaqeen dilata hai ke **"main laptop hoon"**, aur **mobile** ko yaqeen dilata hai ke **"main router hoon"** is tarah attacker beech mein aa kar dono devices ke darmiyan poora data intercept kar leta hai, bina unhe pata chale.

---

## HTTP Vs HTTPS — Data Security Farq

**HTTP:**
Jo devices **HTTP** use karti hain, un ka data **koi bhi read kar sakta hai** kyun ke HTTP mein data **plain text** mein travel karta hai, koi encryption nahi hoti.

**HTTPS:**
Jo devices **HTTPS** use karti hain, un ka data **plain text mein nahi hota** matlab HTTPS data ko **encrypt** kar deta hai, is liye beech mein koi (jaise ARP Spoofing attacker) usay asani se parh nahi sakta.

**Restricted (Trusted) WiFi:**
Agar koi **restricted (trusted/known) WiFi** use kare, to koi bhi doosra device us WiFi par **website access nahi kar sakta** aur na hi kisi doosre device ka **HTTP traffic dekh sakta hai** is liye trusted network use karna zaroori hai, warna device ka data **plain text** mein expose ho sakta hai.

---

## Summary

**ARP Basic Concept:**
- ARP IP address ko MAC address ke sath resolve karta hai
- Sirf local network (LAN) ke andar kaam karta hai, out of house nahi

**ARP Process:**
- Request → jab MAC address maloom na ho, IP se poocha jata hai
- Response → jis device ka IP match hota hai, wo apna MAC bhejta hai
- Broadcast → request sab devices ko bhejni parti hai
- Unicast → response sirf specific device ko wapas jata hai

**Commands:**
- `arp -a` → ARP table dikhata hai
- `ip neigh` → neighboring devices ki IP-MAC mapping dikhata hai

**App Cache Table:**
- Device apne andar IP aur MAC address ki mapping cache karta hai, taake baar baar ARP request na karni pare

**ARP Kab Hota Hai:**
- DHCP ke through IP assign hote waqt
- Manual IP assignment mein mistake hone ke chances zyada hote hain

**ARP Spoofing Attack:**
- Attacker khud ko fake device (jaise router) ki tarah show karta hai
- Attacker "middle man" ban kar laptop aur mobile ke darmiyan aa jata hai
- Router ko lagta hai attacker hi laptop hai, aur mobile ko lagta hai attacker hi router hai

**HTTP Vs HTTPS Security:**
- HTTP → plain text, koi bhi data read kar sakta hai
- HTTPS → encrypted, data secure rehta hai
- Trusted/restricted WiFi use karna security ke liye zaroori hai
