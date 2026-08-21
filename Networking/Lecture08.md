# TCP & UDP

## TCP/UDP Kya Hain

**TCP** aur **UDP** dono **protocols** hain matlab ye **set of rules** hote hain jinhe devices **follow** karti hain jab wo aapas mein **communication** karti hain.

**Example (Language):**
Jaise **same language** agar ek insaan English bolta hai to doosra insaan bhi English samajhta hai, tabhi communication possible hoti hai. Bilkul isi tarah, devices ke darmiyan bhi **communication ke liye ek common set of rules** hona zaroori hota hai.

**Rules Ka Follow Hona:**
Kuch **rules** hote hain jinhe devices **poore internet mein (across the internet)** follow karti hain. Jab do devices communicate karti hain, to unki **ports active** hoti hain, aur wo **TCP ya UDP** mein se kisi ek ke rules follow karti hain.

---

## TCP — Transmission Control Protocol

### 3-Way Handshake

TCP mein connection banane ke liye ek process hota hai jise **3-way handshake** kaha jata hai.

**Example — 2 Devices (Sender & Receiver):**

1. **Sender:** `SYN` message send karta hai "connection krny k liya"
2. **Receiver:** `SYN-ACK` (Synchronize-Acknowledge) wapas bhejta hai "connection ka responce deny k liya"
3. **Sender:** `ACK` (Acknowledge) bhej kar connection confirm karta hai

Is poore process ko **3-way handshake** kaha jata hai, kyun ke isme teen steps involve hote hain.

### TCP Data Packet Delivery

TCP data packet ka protocol **TCP** hota hai. Sender data packet ko receiver ko send karta hai.

**Packet Loss Handle Karna:**
Agar koi packet **loss** ho jaye (raste mein kho jaye), to TCP wo packet **dobara bhejta hai** matlab TCP ye guarantee deta hai ke poora data successfully deliver ho.

**Example — Data Travel Aur Error Handling:**
Agar ek message **"200K"** travel kar raha ho aur usme koi error aaye (jaise **"404" error**), to devices apas mein ek tarah ka **code word** use karti hain matlab agar sab kuch theek hai to **"200K"** wapas confirm hota hai, warna error code milta hai.

**TCP Ka Order Maintain Karna:**
TCP data packets ko is tarah bhejta hai ke **order mein hi deliver** hon matlab koi packet apni sahi sequence ke bina deliver nahi hota, aur agar koi packet loss ho, to wo **order kharab nahi hone deta**, balke usay dobara bhej kar sahi order maintain karta hai.

---

## UDP — User Datagram Protocol (The Fast One)

**UDP** ko **"the fast one"** bhi kaha jata hai kyun ke ye TCP se **tez (fast)** hota hai.

**UDP Importance:**
UDP mein **protocol, header, aur delivery** to hoti hai, lekin is mein **handshake nahi hota** matlab devices bina kisi confirmation process (jaise TCP ka 3-way handshake) ke **directly packet send** kar deti hain.

**Sequence & Order:**
UDP mein packets ki koi **sequence ya order guarantee nahi** hoti packets jaise bhi pohanchein, unhe usi tarah accept kar liya jata hai.

**Example — Packet Loss:**
Agar 3 packets bheje jayein jinke numbers **1000, 1001, 1002** hain, aur agar **1001** wala packet **loss** ho jaye, to sirf **2 packets** (1000 aur 1002) hi deliver hote hain UDP us missing packet ko dobara nahi bhejta.

**UDP Mein Deliver Ya Loss:**
UDP mein jo packet deliver ho jata hai wo ho jata hai, aur jo **loss** ho jata hai wo bas **loss hi reh jata hai** data **wapas nahi manga jata**. Ismein **na to order hota hai, na hi sequence** ki guarantee hoti hai.

---

## TCP Vs UDP — Diff

**TCP:**
- Agar koi packet **loss** ho jaye, to TCP usay **dobara bhejta hai**
- Data hamesha **order (sequence)** mein bheja jata hai

**UDP:**
- Agar packet loss ho jaye, to wo **loss hi reh jata hai** dobara nahi bheja jata
- Speed zyada hoti hai lekin **reliability kam**

**Use Cases:**
- **Text (jaise messages)** → **TCP** use hota hai, kyun ke har lafz sahi order mein aur complete pohanchna zaroori hai
- **Video (jaise live streaming)** → **UDP** use hota hai, kyun ke speed zyada important hoti hai, aur agar koi frame miss ho bhi jaye to video chalti rehti hai

Chahe TCP ho ya UDP, dono mein data hamesha **packet** ki shakal mein hi internet par travel karta hai.

---

## 3-Way Handshake — Dono Sides Se (Client Aur Server)

TCP ka **3-way handshake** dono taraf se hota hai — **client** aur **server** ke darmiyan.

**Port Numbers Ka Example:**
- **Web Server:** Port **443** (HTTPS ke liye common port)
- **Client:** Port **49821** (ye ek random/temporary port hota hai jo client ki taraf se use hota hai)

**Handshake Process (Step by Step):**

1. **Client → Server:** `SYN` bheja jata hai
2. **Server → Client:** `SYN-ACK` bheja jata hai
3. **Client → Server:** `ACK` bheja jata hai — connection establish ho jata hai

Jaise hi ye teeno steps complete ho jate hain, to **connection established** ho jata hai, aur is state ko "Client: ESTABLISHED" aur "Server: ESTABLISHED" kaha jata hai.

**In Simple Words:**
```
SYN → SYN-ACK → ACK
```
Ye pattern taqreeban **har web connection** ka basic tareeqa hai jab bhi koi browser website open karta hai.

---

## Connection Closing Process

Jab connection **band** hoti hai, to bhi ek specific process follow hota hai:

**Client Side:**
```
Client: FIN-WAIT
```
Client ki taraf se connection close karne ka signal `FIN` (Finish) bheja jata hai, aur client "FIN-WAIT" state mein chala jata hai.

**Server Side:**
```
Server: CLOSE-WAIT
```
Server "CLOSE-WAIT" state mein chala jata hai, jab tak connection poori tarah band nahi ho jati.

**Basic Concept:**
Jaise connection **open** hai teen steps (SYN, SYN-ACK, ACK) ke sath, waise hi connection **band** hone ka bhi apna specific process hota hai dono taraf (client aur server) ko is process mein shamil hona parta hai.

---

## Summary

**TCP/UDP Ka Basic Concept:**
- Ye dono protocols hain, jo communication ke liye rules define karte hain
- Dono internet ke through devices ke darmiyan data bhejte hain

**TCP Importance:**
- 3-way handshake use karta hai: SYN → SYN-ACK → ACK
- Packet loss hone par dobara bhejta hai
- Data order (sequence) mein deliver karta hai
- Use case: Text/messages

**UDP Importance:**
- Handshake nahi hota, direct packet send hota hai
- Packet loss hone par dobara nahi bheja jata
- Order ya sequence ki guarantee nahi hoti
- Speed zyada hoti hai (isliye "the fast one" kaha jata hai)
- Use case: Video/streaming

**3-Way Handshake (Connection Open):**
1. SYN — Client se Server
2. SYN-ACK — Server se Client
3. ACK — Client se Server

**Connection Close Process:**
- Client: FIN-WAIT
- Server: CLOSE-WAIT

**Common Port Numbers:**
- Web Server (HTTPS) → Port 443
- Client → Random port (jaise 49821)
