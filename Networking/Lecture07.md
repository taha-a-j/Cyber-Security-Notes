# TCP/IP Model

## TCP/IP Model Kya Hai

**TCP/IP** ek networking model hai jo **4 layers** based hota hai. Ye OSI Model ki tarah hi kaam karta hai, lekin usay simplify kar ke sirf 4 layers mein divide kiya gaya hai.

## TCP/IP  (Sender Side)

4Layers

1. **Application**
2. **Transport**
3. **Internet**
4. **Network Access**

---

## Layer 4: Application Layer

**Request Generate:**
Is layer par **request generate** ki jati hai jaise agar koi WhatsApp par message bhejta hai, to wo request yahin se shuru hoti hai.

**Text Format:**
Message pehle **plain text** ki shakal mein hota hai.

**Encryption:**
Is layer par data ko **encrypt** kiya jata hai matlab "simple text" ko multiple **algorithms** use kar ke ek "lock" laga diya jata hai, taake data secure ho jaye.

**HTTP Aur HTTPS:**

```
HTTP, HTTPS
```

Ye dono protocols is layer par kaam karte hain HTTPS encrypted hota hai jabke HTTP plain text mein hota hai.

**Content:**
Is layer par **content ki cheezein** dekhi jati hain, jin mein included hai:

- **Encryption**
- **Data**

**Header Components:**
Header mein ye information hoti hai:

- **Header**
- **Body**
- **Content**
- **Label Info** → jis mein **SRC (Source)** aur **DST (Destination)** shamil hote hain
- **IP Address**
- **Location**

**Box (Format Example):**
Data ka format kuch is tarah hota hai:

```
Post
Host
Content
```

---



## Layer 3: Transport Layer

**Sequence Number & Data:**
Is layer par **sequence number**, **data**, aur **port number** ka kaam hota hai.

**Data Segment Mein Convert Hona:**
Data ab **segment** mein convert ho jata hai segment wo hota hai jise ek specific **numbering** di jati hai.

**Pages Ki Tarah Numbering:**
Isay is tarah samjho jaise kisi letter ke **multiple pages/parts** hote hain (jaise Part 1, Part 2, Part 3). Bilkul isi tarah data bhi **multiple parts** mein segment ho kar convert hota hai.

**Data Loss Hone Par:**
Agar data ka koi **part loss** ho jaye (raste mein kho jaye), to **TCP** dobara us **missing part** ko deliver karne ki koshish karta hai — matlab TCP ye ensure karta hai ke poora data successfully pohanche.

**Data Ka Deliver Hona (Easy Way):**
Data ko **slice** kar ke segments mein convert kiya jata hai, taake data ko **easy way** se deliver kiya ja sake.

---



## Layer 2: Internet Layer

**Header Information:**
Internet layer par packet ke header mein ye cheezein include hoti hain:

- **SRC (Source)**
- **DST (Destination)**
- **IP**
- **IP Version**
- **TTL (Time To Live)**
- **Protocol**
- **Flags**

**Example Values:**

```
IPv4
TTL: 58
Protocol: TCP
```

**TCP Ka Data Loss Handle Karna:**
Agar **TCP** mein data **loss** ho jata hai, to wo **dobara missing data** ko final taur par **deliver** karta hai is process ko **Flag: DF (Don't Fragment)** ke through control kiya jata hai.

**Data Packet Banna:**
Is layer par data ab **packet** ban jata hai. Packet mein **SRC IP** aur **DST IP** enter ki jati hain:

- **Source IP**
- **Destination IP**

**Path Find Karna:**
Sabse **near** aur **closest path** find ki jati hai taake data ko **deliver** kiya ja sake.

---



## Layer 1: Network Access Layer

**MAC Address Role:**
Is layer par:

- **DST MAC** (Destination MAC address)
- **SRC MAC** (Source MAC address)

Ye dono MAC addresses packet mein add hoti hain.

**Convert into Binary:**
Data ab **binary** mein convert ho jata hai matlab data `0, 1, 0, 1` jaisi shakal mein change ho jata hai.

**Data's Physical Travel:**
Data **radio waves, light, ya copper (cable)** ke through move karta hai depend karta hai ke konsa medium use ho raha hai.

**Frame & Raw Signal:**
Data **frame** aur **raw signal** mein convert ho jata hai. Ye process **NIC (Network Interface Card)**, **switch**, ya **WiFi Access Point (AP)** ke through **process** hota hai.

**Security — MAC Address Tracking:**
Ek **hacker** ko **MAC address** se **track** kiya ja sakta hai ye security ke way se important point hai.

**MAC Address Fake Karna:**
Log apni identity chhupane ke liye **fake MAC address** bhi use karte hain.

**Virtual Machine Ka Example:**
**Virtual machine** jaisi cheezein **fake MAC address** use karti hain taake asal device ki identity trace na ho sake.

---



## Receiver Side

Jab data receiver tak pohanchta hai, to is layer ka process **ulta (reverse order)** mein chalta hai matlab data neeche se upar ki taraf sari layers se guzarta hai:

```
Network Access → Internet → Transport → Application
```

**Step-by-Step Reverse Process:**

1. **Network Access Layer:** Sab se pehle receiver ka device data ko **binary signal** ki shakal mein receive karta hai — jo **NIC, switch, ya WiFi AP** ke through process hota hai. Is data ko wapas **frame** mein convert kiya jata hai, aur **MAC address** verify ki jati hai ke ye packet asal mein isi device ke liye tha ya nahi.
2. **Internet Layer:** Frame se **packet** nikala jata hai, aur us mein maujood **Source IP aur Destination IP** ko check kiya jata hai taake confirm ho sake ke ye data sahi device ke liye aaya hai.
3. **Transport Layer:** Packet se **segments** nikale jate hain, aur unki **sequence number** ke according se unhe **wapas order mein jorha (reassemble)** kiya jata hai. Agar koi segment **missing** ho, to **TCP** dobara us missing part ki request bhejta hai taake poora data complete ho sake.
4. **Application Layer:** Last mein saare segments jorne ke baad, agar data **encrypted** tha, to usay **decrypt** kiya jata hai, aur receiver ko asal **original message** (jaise "Hello" ya jo bhi content tha) mil jata hai.

Is tarah data sender se receiver tak safar karta hai, aur receiver side par wahi process **reverse order** mein ho kar data ko wapas apni original shakal mein la deta hai.

---



## Summary

**4 Layers (Upar Se Neeche):**

1. Application → request generate, encryption, HTTP/HTTPS, header/body/content
2. Transport → data segments mein convert, sequence number, port number, data loss handle karna (TCP)
3. Internet → SRC/DST IP, IP version, TTL, protocol, flags, packet banna
4. Network Access → SRC/DST MAC address, binary conversion, frame/raw signal

**Data's Travel (Sender Side):**

- Application (text/encryption) → Transport (segments) → Internet (packet + IP) → Network Access (frame + binary)

**Receiver Side (Reverse Process):**

- Network Access (binary se frame, MAC verify) → Internet (packet se IP check) → Transport (segments reassemble) → Application (decrypt aur original message)

**Security Note:**

- MAC address se hacker track ho sakta hai
- Fake MAC address use ho sakta hai (jaise virtual machines mein) taake identity chhupayi ja sake

