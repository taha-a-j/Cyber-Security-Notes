# VPN  (Virtual Private Network)

## VPN?

**VPN (Virtual Private Network)** ek **software system/app** hai jo **secure tunneling** create karta hai.

**VPN Basic Working:**
Data ko **lock** kar ke **key** ke sath **send ya receive** kiya jata hai matlab data secure tareeqe se ek jagah se doosri jagah bhejnа possible hota hai.

**Kaun Sa Data Pohanchta Hai:**
Us **send ya receive ko pta ho** (matlab confirm ho) ke ye process "**called**" hai VPN ka poora system isi tarah kaam karta hai.

**Security Maintaince:**
VPN **security maintain** karta hai matlab data ko protect rakhta hai jab wo internet par safar karta hai.

---



## Tunneling — Entire Tunnel Create Hota Hai

**Tunneling?:** Tunneling ka matlab hai ke ek **poora tunnel create** hota hai jis se data guzarta hai.

**Access Lock:**
Is tunneling ke through **access ko lock** kar diya jata hai matlab bahar se koi bhi is tunnel ke andar ka data easily access nahi kar sakta.

**Firewall Role:**
**Firewall** bhi is process mein shamil hota hai jo tunnel ke andar aane jane wale data ko control karta hai.

**Example:** Army Pilot Truck
Jaise army apni movement ko chhupa kar aage barhti hai (jaise ek save raste se), waise hi VPN bhi data ko ek **secure tunnel** ke through bhejta hai jahan bahar se koi observe ya intervene nahi kar sakta.

---



## Firewall Bypass

**Firewall Login:** Agar kisi jagah (jaise office ya school) mein **YouTube** access **restrict** ki gayi ho, to VPN use kar ke us restriction ko **bypass** kiya ja sakta hai matlab VPN firewall ke rules ko avoid karne mein help karta hai.

---



## VPN Encryption & Data Travel

**Data Encrypt + Tunnel Create:**
VPN **do kaam** ek sath karta hai:

1. Data ko **encrypt** karta hai
2. Ek **tunnel create** karta hai jis se data guzarta hai

**Internet Par Data Travel:**
Data **internet ke through travel** karta hai, lekin VPN ki wajah se ye safar **save** hota hai.

---



## VPN Working 

Between Two Devices

**Without VPN:**
Agar VPN use na kiya jaye, to data **do devices ke darmiyan plain text** mein travel karta hai matlab koi bhi is data ko beech mein padh sakta hai.

**With VPN:**
Jab VPN use hota hai, to data **encrypted** shakal mein travel karta hai, jo isay **secure** banata hai.

---



## VPN Networking  (Like Virtual Machine)

**Network Inside Network:**
VPN network ke andar ek doosra **network create** karta hai is process ko is tarah samjho jaise ek **laptop ke andar ek aur "virtual" machine** create ki jati hai.

**CPU, Space Aur Machine Create Karna:**
Jaise virtual machine banate waqt **CPU, space, aur machine** create ki jati hai (jo real computer ke resources use karti hai), waise hi VPN bhi ek "virtual" secure network create karta hai jo asal network ke andar hi operate hota hai.

**Virtual Machine Definition:**
**Virtual machine** wo hoti hai jo **compute (computer) ke andar** ek doosri machine create karti hai is tarah aap **do alag method se** kaam kar sakte hain, ek hi physical device par.

---



## Public WiFi Danger

**Public WiFi Par Koi Bhi Attack Kar Sakta Hai:**
Agar koi **public WiFi** use kare, to is se koi bhi **attack** kar sakta hai kyun ke public WiFi mein security bohat Weak hoti hai.

**HTTP:**
Jo network **"HTTP"** use karta hai (na ke HTTPS), us ka data **encrypted nahi** hota matlab wo **plain text** mein travel karta hai, jise **koi bhi read** kar sakta hai.

---



## ISP (Internet Service Provider) & Hacker Danger

**ISP Activities ability:**
**ISP (Internet Service Provider)** ke paas ye ability hoti hai ke wo user ki **activities dekh sakta hai** kyun ke saara traffic ISP ke through hi guzarta hai.

**Hacker On Same WiFi:**
Agar koi **hacker usi WiFi par** ho jis se aap connect hain, to wo bhi aapke **data ko access** kar sakta hai.

**VPN Working:**
VPN ka basic kaam ye hota hai ke wo data ko is tarah **encrypt** kar deta hai ke chahe ISP ho ya koi hacker, koi bhi **key ke bina** data ko **steal** nahi kar sakta.

**Password Wireshark Se Packet Analyze Karna:**
Agar koi tool (jaise **Wireshark**) use kar ke **packet analyze** kare, to bina VPN ke usay data **"passwordable"** (asani se dekhne layak) mil sakta hai matlab agar encryption na ho to sensitive information (jaise password) bhi packet capture tools se dikh sakti hai.

---



## VPN Server Connection

**Connect With VPN Server:**
VPN ke through **server se secure connect** kiya jata hai, taake data safe way ma transfer ho saky.

**Data Encrypt (Packet Example):**
Agar koi packet **"a812890"** jaisi shakal mein hai (jo random/encrypted data ko represent karta hai), to VPN ke bina wo **easily readable** ho sakta hai. VPN us packet ko is tarah encrypt karta hai ke usay **decode karna mushkil** ho jata hai.

**Tunnel Ke Through Server Tak Pohanchna:**
Data **tunnel ke through server tak pohanchta hai**, aur server se jab **response wapas aata hai**, to wo bhi isi **encrypted tunnel** ke througgh wapas aata hai.

**Data Break Hona:**
Agar tunnel na ho, to data **VPN ke bina break** ho sakta hai matlab bina encryption ke data insecure reh jata hai aur beech mein koi bhi usay intercept kar sakta hai.

---



## Risks When Connecting to Wi-Fi

**Through Wifi Data Steal:**
Agar aap kisi WiFi se connect hain, to koi bhi doosra device jo usi WiFi par ho, wo aapka **data steal** kar sakta hai.

**MAC Address Se Monitoring:**
Agar koi **MAC address dekh le**, to wo bhi aap ke bare mein information collect kar sakta hai is liye MAC address ka secure rehna bhi zaroori hota hai.

**College Wifi Ka Example:**
Jaise agar koi **college** ka WiFi use kare, to wahan bhi ye khatra ho sakta hai ke koi doosra device network access kar ke data dekh sake, agar proper security na ho.

---



## VPN Types

VPN ke **teen main types** hote hain:

### 1. Site-to-Site VPN

Ye **do networks** (jaise do offices) ko aapas mein secure tareeqe se connect karta hai.

### 2. Remote Access VPN

Ye ek **individual user** ko kisi private network se securely connect karne deta hai jaise employee apne ghar se office ke network se connect ho.

### 3. VPN Server

VPN server wo hota hai jis ke through data pass ho kar apni manzil (destination) tak pohanchta hai.

---



### **How a VPN Works**  

### **Step-by-Step Process**

### Step 1: 3-Way Handshake

VPN connection banane ke liye bhi ek **3-way handshake** hoti hai (jaise TCP mein hoti hai) is mein sab se pehle ek **"Hello"** message exchange hota hai taake connection initiate ho sake.

### Step 2: Protocol Ka Use

Is step mein ek **protocol** use hota hai jo tunnel banane mein help karta hai. Common protocols mein include hai:

```
WireGuard, OpenVPN
```



### Step 3: VPN Server Role

VPN server **humany certificate** (yani apna khud ka certificate) provide karta hai, jo **proving** karta hai ke server asli aur trusted hai. Is certificate ko **Public Key** kaha jata hai.

**VPN Server Ka User Se Handshake:**
VPN server, user ke sath bhi is tarah kaam karta hai jaise ek "**Hello**" ka encryption use kiya jata hai, taake dono taraf trust establish ho sake.

### Step 4: Shared Key Banana

Dono taraf  **VPN server aur user**  dono ke paas **shared key** hoti hai. Ye shared key isliye zaroori hai taake dono taraf secure connection establish ho sake.

**Public Key Aur Private Key:**

- **Public Key** → ye sabko pata ho sakti hai, isay data **encrypt** karne ke liye use kiya jata hai
- **Private Key** → ye sirf mालik (owner) ke pass hoti hai, isay data **decrypt** karne ke liye use kiya jata hai

---



## VPN Types



### VPN Types:

1. **Site-to-Site VPN**
2. **Remote Access VPN**
3. **VPN Server**

**Protocol Uses:** VPN mein ek **protocol** use hota hai jo tunnel banane mein help karta hai.

**Speed Aur Complexity:**
Different protocols ki apni **speed aur complexity** hoti hai — kuch protocols **fast (age)** hote hain, jabke kuch zyada **complex** lekin secure hote hain.

**WireGuard Vs Linux:**

```
WireGuard → Linux
```

WireGuard ek modern protocol hai jo Linux systems ke sath acha kaam karta hai.

**IP Se Access:**
VPN ke through **IP se access** kiya jata hai, taake secure connection maintain rahe.

---



## Public IP Encryption — VPN Need

**Public IP With Data Encrypted:**
VPN ka basic role ye hota hai ke jab bhi koi device apni **Public IP** ke sath data bhejti hai, to VPN us data ko **encrypt** kar deta hai taake data save rahe.

**Both VPN Server & User Connecting:**
VPN connection mein **dono taraf VPN server aur user** donon aapas mein **connect** hote hain, is process ko **"handshake"** kaha jata hai.

---



## VPN & Different Countries

**Another Country Mein Appear Hona:**
VPN use karne se user ka device kisi **doosre mulk (country)** mein maujood hota hai matlab jab hum VPN "on" karte hain, to hamari location kisi aur country ki show hoti hai.

**Example:**
Agar hum **US ya UK** ki kisi **company se related** koi cheez use karna chahte hon, to hum VPN ke through us country ka access **use** kar sakte hain.

**Remote Working:**
VPN **remote work** karne mein bhi help karta hai matlab koi bhi employee kahin se bhi apni company ke system tak securely access le sakta hai.

**ISP Se Chupana:**
VPN se **ISP (Internet Service Provider)** se bhi data **chupaya (hide)** ja sakta hai kyun ke jab VPN active ho, to ISP ye nahi dekh sakta ke user asal mein kya access kar raha hai.

**VPN Service:**
VPN service in saray kaamon ko possible banati hai chahe wo geo-restriction bypass karna ho, ya security maintain karni ho.

---



## Full Tunnel — VPN Complete Coverage

**Full Tunnel Kya Hai:**
**Full Tunnel** VPN ka wo mode hai jis mein **poora traffic VPN tunnel se guzarta hai**, na ke sirf kuch specific websites ka.

**Example:**

```
google.com → VPN tunnel → office google
netflix.com → VPN tunnel → netflix
```

Chahe koi bhi website access ki jaye (google ho ya netflix), agar Full Tunnel VPN active ho, to har request usi VPN tunnel se guzregi.

---



## Summary

**VPN Basics:**

- VPN ek software/app hai jo secure tunneling create karta hai
- Data ko encrypt kar ke ek secure tunnel se bhejta hai
- Firewall restrictions ko bypass karne mein madad karta hai

**VPN Need:**

- Public WiFi par attack se bachata hai
- ISP se activities chupata hai
- Hacker se data secure rakhta hai (encryption ki wajah se)
- HTTP jaisi unsecure connections ke khatray se bachata hai

**VPN Types:**

1. Site-to-Site VPN — do networks ko connect karta hai
2. Remote Access VPN — individual user ko private network se connect karta hai
3. VPN Server — data ko destination tak pohanchata hai

**VPN Ka Working Process:**

1. 3-way handshake (Hello message exchange)
2. Protocol use hota hai (jaise WireGuard, OpenVPN)
3. VPN server apna certificate (Public Key) provide karta hai
4. Shared key banti hai (Public Key aur Private Key ke through)

**Public Key Vs Private Key:**

- Public Key → data encrypt karne ke liye, sabko pata ho sakti hai
- Private Key → data decrypt karne ke liye, sirf owner ke pass hoti hai

**VPN & Location:**

- VPN se device doosre country mein appear hota hai
- Isay geo-restricted content access karne aur remote work ke liye use kiya jata hai

**Full Tunnel:**

- Poora internet traffic VPN tunnel se guzarta hai, chahe koi bhi website ho

