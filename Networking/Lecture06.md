# OSI Model

## OSI Model Kya Hai

Agar koi kisi ko **message bhejna** chahta hai, to wo message **7 layers** ko cross kar ke guzarta hai, tabhi jaake wo message doosri taraf **deliver** hota hai. Ye 7 layers milkar **OSI Model** banate hain, jo data ke safar ko organize karte hain.

##  7 Layers

1. **Application**
2. **Presentation**
3. **Session**
4. **Transport**
5. **Network**
6. **Data Link**
7. **Physical**

---

## Layer 7: Application Layer

Application layer wo pehli layer hai jahan se data ka safar shuru hota hai.

**Text Kaise Travel Karta Hai:**
Data ya to **plain text** mein travel karta hai ya **encrypted** tareeqe se ye is baat par depend karta hai ke konsa **protocol** use ho raha hai (jaise HTTP).

**Request Generate Hona:**
Jab user koi action leta hai (jaise website open karna), to is layer par **request generate** hoti hai aur ye tay hota hai ke konsa protocol (jaise HTTP) use hoga.

**Content Length:**
Is layer par ye bhi decide hota hai ke content ki **length** kya hogi.

### HTTP Aur HTTPS

**HTTPS:** Ye ek **encrypted way** hai jis mein data travel karta hai matlab data secure tareeqe se bheja jata hai.

**HTTP:** Is mein data **plain text** mein travel karta hai matlab bina encryption ke, jo kam secure hota hai.

**HTTP Ke Types:**

```
HTTP/1.1
```



### Header Ke Components

Har request/response ke sath ek **header** hota hai, jis mein ye information shamil hoti hai:

- **Source** → data kahan se aa raha hai
- **Destination** → data kahan jana hai
- **Type** → data ka type kya hai
- **Content** → asal data/message
- **Content Length** → data ki length kitni hai



### Body

**Body** wo hissa hota hai jo asal **request ya message** hoti hai jaise agar koi simple "Hello" message bheja jaye, to "Hello" khud **body** kehlata hai.

### Cookies

**Cookies** bhi is layer se related hoti hain — ye small pieces of data hoti hain jo websites user ke browser mein store karti hain taake user ki information yaad rakhi ja sake.

---



## Layer 6: Presentation Layer

Presentation layer **2nd level** hoti hai jahan hum data ko dekhte hain.

**Encryption Ka Kaam:**
Is layer par data (jo pehle **plain text** ho sakta hai) ko kuch **algorithms** use kar ke **encrypt** kiya jata hai — taake data ki **privacy** maintain rahe.

---



## Layer 5: Session Layer

**Session Kya Hai:**
Session ek **period/time** hota hai jis ke doran do devices aapas mein connected rehti hain.

**Session Kaise Create Hota Hai:**
Client apni taraf se ek **"Hello"** jaisa message server ko bhejta hai. Is process ko **SYN request** kaha jata hai.

**Session Establishment Process:**

**Step 1 — SYN (Session ID):**

```
Client → SYN (Session ID) → Server
```

Client server ko "Hello" bhejta hai aur sath hi ek **Session ID** bhi generate ho kar bheji jati hai.

**Step 2 — SYN-ACK (Acknowledge):**

```
Server → SYN-ACK (Acknowledge) → Client
```

Server client ki request ko acknowledge karta hai matlab confirm karta hai ke usay client ki request mil gayi hai.

**Step 3 — ACK (Connection Established):**

```
Client → ACK (Connection Established) → Server
```

Client server ko final acknowledgment bhejta hai, jis se **connection establish** ho jata hai is poore process ko **3-way handshake** kaha jata hai.

**Session Purpose:** Jab dono devices ke darmiyan connection ban jata hai, to session create ho jata hai is ke baad data ka aadan-pradan (exchange) ho sakta hai.

**Session Kab Terminate Hota Hai:** Jab kaam compelete ho jata hai aur devices **disconnect** ho jati hain, to session bhi **terminate (khatam)** ho jata hai matlab session ka time "expire" ho jata hai.

**Real-Life Example:** Jaise agar tum apne dost ko call kar ke koi cheez share karna chahte ho, to jab tak call chalti hai, wo ek "session" hai jaise hi call katti hai, session bhi khatam ho jata hai.

---



## Layer 4: Transport Layer

**Segment Banna:**
Transport layer par data **segments** mein toot jata hai matlab jo bhi message hai, wo chhote chhote hisson (segments) mein divide ho jata hai.

**Data Packet Ki Form:**
Data **packet** ki form mein move karta hai. Agar koi message "Hello" hai, to ye "Hello" bhi packet ki form mein hi travel karta hai.

**Port Number Assign Hona:**
Is layer par har packet ke liye ek **port number** decide hota hai phir us port ke through data bheja jata hai.

**Port Number Ka Kaam:**
"Hello" jaisa message packet ki shakal mein tayar hota hai, aur us packet ko ek **number diya jata hai**, phir us port ko **label** kar diya jata hai.

**Loss Hone Par Kya Hota Hai:**
Agar koi packet **loss** ho jaye (raste mein kho jaye), to us waqt system dobara **request generate** karta hai, taake data phir se travel kar sake aur successfully pohanch sake.

### Segment Ka Structure

Jab data **distribute** hota hai, to wo **segments** mein bant jata hai.

**Example:** Agar message "Hello" hai, to ye 3 segments mein divide ho sakta hai Segment Number 1, 2, 3. Har segment ke liye ek **port number label** kiya jata hai.

**Segment Ka Structure:**

```
Segment 1: Port Number
Segment 2: [data]
Segment 3: [data]
```

---



## Layer 3: Network Layer

Network layer par **source aur destination IP address** ka kaam hota hai.

**SRC (Source) Aur DST (Destination):**

- **Source (SRC)** → jahan se data bheja ja raha hai, us jagah ki IP address
- **Destination (DST)** → jahan data ko pohanchna hai, us jagah ki IP address

**IP Add Hona:**
Segment ke andar bhi **IP address add** ki jati hai matlab jo bhi data header mein hota hai, us mein source aur destination ki IP shamil ki jati hai.

**Packet Banna:**
Jab **source aur destination IP** dono mil jati hain, to us waqt asal **packet** ban jata hai jo aage safar karne ke liye tayar ho jata hai.

---



## Layer 2: Data Link Layer

**MAC Address:** Is layer par **source ya destination ka MAC address** packet mein add hota hai.

**Frame Ban Jana:**
Jaise hi MAC address packet mein add ho jata hai, to wo packet ab **frame** kehlata hai matlab data ab is layer par "frame" ki shakal kar leta hai.

---



## Layer 1: Physical Layer

**Frame Ka Conversion:**
Physical layer par jo bhi **frame** taiyar hua tha, wo **binary** (0s aur 1s) mein **convert** ho jata hai taake wo physically (jaise cables, wireless signals) ke through transmit ho sake.

---



## Receiver Side — Poora Process Ulta Hota Hai

Jab data receiver tak pohanchta hai, to wahan par **ulta process (reverse order)** hota hai matlab data neeche se upar ki taraf sari layers se guzarta hai:

```
Physical → Data Link → Network → Transport → Session → Presentation → Application
```

Is poore reverse process ke doran data apni original shakal mein wapas convert hota jata hai, jab tak wo **application layer** tak nahi pohanch jata — jahan par receiver ko asal message (jaise "Hello") mil jata hai.

---



## Summary

**7 Layers (Sender Side):**

1. Application → request generate hoti hai, protocol decide hota hai (HTTP/HTTPS),header,body
2. Presentation → data encrypt hota hai plain text sy (secure)
3. Session → connection establish hota hai (3-way handshake: SYN, SYN-ACK, ACK)
4. Transport → data segments mein banta hai, port number assign hota hai
5. Network → source aur destination IP address add hoti hai, packet banta hai
6. Data Link → MAC address add hoti hai, frame banta hai
7. Physical → frame binary mein convert hota hai

**HTTP vs HTTPS:**

- HTTPS → encrypted, secure
- HTTP → plain text, kam secure

**Header Ke Components:**

- Source, Destination, Type, Content, Content Length

**Session Establishment (3-Way Handshake):**

1. SYN (Session ID) — Client se Server
2. SYN-ACK (Acknowledge) — Server se Client
3. ACK (Connection Established) — Client se Server

**Receiver Side:**

- Data reverse order mein tamam layers se guzarta hai: Physical → Data Link → Network → Transport → Session → Presentation → Application
- Ye poora process TCP/IP ke through hota hai

