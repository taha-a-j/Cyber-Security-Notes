## Client-Server Model

Networking ki basic **Client-Server Model** par hoti hai, jis mein do main parts hote hain:

### Client
**Client** wo hota hai jisay **kisi cheez ki zaroorat (demand)** hoti hai — matlab jo user ya device kisi service ya data ko maang raha hota hai. Client ki koi bhi demand ho sakti hai, jaise koi application use karna ho ya Netflix jaisi website par kuch dekhna ho.

### Server
**Server** **data provider** hota hai — matlab wo cheez jo data deti hai. Jab client ki taraf se koi request aati hai, to server us request ko **poora karta hai**, matlab jo mangi gayi cheez hoti hai wo client ko provide kar deta hai.

---

## Network Kya Hai

**Network** **internet ka ek part** hai. Jab **do devices** — chahe **wire** se ho ya **wireless** se — aapas mein connect hoti hain, to unke beech ek **network** ban jata hai.

---

## DHCP — Dynamic Host Configuration Protocol

**DHCP (Dynamic Host Configuration Protocol)** ek protocol hai jo devices ko **automatically IP address assign** karta hai.

### Manual IP Assignment
**Manual** tareeqe mein IP address khud se assign kiya jata hai — matlab koi insaan khud router mein login kar ke IP address set karta hai.

### DHCP (Automatic)
**DHCP** IP address **automatic** tareeqe se assign kar deta hai — insaan ko manually kuch karne ki zaroorat nahi hoti.

**Example (WiFi Password Verification):**
Jab koi device WiFi ka **password verify** karti hai (matlab sahi password enter karti hai), to us waqt DHCP automatically us device ko ek IP address assign kar deta hai — koi manually IP set nahi karta.

---

## Manual IP Assignment

Agar IP address **manually** assign karna ho, to iske liye ye steps hote hain:

**Router Mein Login Karna:**
Router ke andar **login** kar ke IP address **assign** kiya jata hai.

**Manually Check Karna:**
Manually ye check karna parta hai ke **konsa IP address free hai** — taake wahi IP kisi device ko assign kiya ja sake, warna do devices ka IP conflict ho sakta hai.

**Network Aur Internet:**
Ye process network aur internet dono ke context mein ho sakta hai — matlab chahe local network ho ya poora internet, IP assignment ka concept dono jagah lagu hota hai.

---

## Devices Network Kaise Create Karti Hain

Jab **2 devices** ek dusre se connect hoti hain, to network create ho jata hai. Ye connection **wire ke through** ho sakta hai.

**Peer-to-Peer Device:**
Jab do devices seedha aapas mein connect hoti hain (bina kisi beech ke device ke), to isay **peer-to-peer** connection kaha jata hai — is tarah **network create hota hai**.

**Important Question:** Kya **internet** is process par **dependent** hai? — local network banane ke liye internet ki zaroorat nahi hoti, sirf devices ka aapas mein connect hona kaafi hai.

---

## Network Types (LAN, WAN, MAN)

### LAN — Local Area Network
**LAN** ek chhote area (jaise ek ghar, office, ya building) ke andar devices ko connect karta hai.

### WAN — Wide Area Network
**WAN** **country to country** level par devices ko connect karta hai — matlab ye ek bohat bada network hota hai jo mulkon ke darmiyan phaila hota hai.

### MAN — Metropolitan Area Network
**MAN (Metropolitan Area Network)** ek **city (shehar) level** ka network hota hai, jisay **public network** bhi kaha ja sakta hai.

**"Sea Shark Cable Cut" Concept:**
Ye ek interesting real-world concept hai jahan samundar (sea) ke andar bichi hui **underwater cables** ko nuqsan (jaise shark ke katne se ya kisi aur wajah se) pohanchta hai, jis se poore region ka internet connection weak ho sakta hai — ye batata hai ke international level ka internet in physical cables par depend karta hai.

---

## Internet to Devices Flow

**Basic Flow:**
```
Internet → Router → Mobile, Laptop
```

Internet pehle **router** tak pohanchta hai, aur router se ye connection **mobile aur laptop** jaise devices tak jata hai.

### Private & Public Network Diff

- **Router Ke Neeche (Below):** Jo bhi devices included router, router ke **below** connect hoti hain, wo sab **private** hoti hain — matlab ye **private network** kehlata hai.
- **Router Ke Upar (Above):** Router ke **above** jo cheez hoti hai, wo **public** hoti hai — matlab internet ki taraf wala hissa public network hai.

---

## Switch Aur Hub

### Router
**Router** ek **gateway** ki tarah kaam karta hai — matlab ye wo darwaza hai jahan se network ka data internet tak ya andar tak jata hai.

### Switch/Hub Basic Working
Switch aur Hub dono aisi devices hain jo **multiple computers ko aapas mein connect** karne ke liye use hoti hain.

**Example:** Agar **5 computers** hon aur unhe aapas mein connect karna ho, to unhe **switch** ya **hub** ke sath connect kiya ja sakta hai.

**Connection Method:**
Hub se connect hote waqt, devices **wire** ke through connect hoti hain.

---

## Hub Working

**Hub Working Principle:**
Agar 5 computers hain aur **Computer 1** apna data **Computer 5** ko bhejna chahta hai, to hub is process mein ye karta hai:

Hub data ko **sab computers ko bhej deta hai** (broadcast karta hai) — matlab sirf Computer 5 ko nahi, balke connected tamam devices ko wahi data mil jata hai.

**Privacy issuse:**
Hub ke is tareeqe mein **koi privacy nahi hoti (No privacy)** — kyun ke jo data sirf ek device ke liye bheja gaya tha, wo sabko mil jata hai, jo security ke lehaz se acha nahi hota.

---

## Switch Working

**Switch Working Principle:**
Switch se connect hone par, switch sirf **us specific receiver (main receiver)** ko hi data bhejta hai jis device wo data chahiyan tha — baaki sari devices ko wo data nahi jata.

**Switch Benefit:**
Ye Hub ke muqable mein zyada **secure aur efficient** hota hai, kyun ke ye data ko sirf sahi device tak pohanchata hai, poore network mein broadcast nahi karta.

---

## Data Flow — Device to Router

**Poora Flow:**
1. **Device** apna data pehle **switch** ko send karta hai.
2. **Switch** phir wo data **router** ko bhej deta hai.
3. **Router** aage data ko **ISP (Internet Service Provider)** tak bhej deta hai.

Is tarah data device se nikal kar switch, router se hote hue aage ISP tak safar karta hai taake internet tak pohanch sake.

---

## Summary

**Client-Server Model:**
- Client → jisay kisi cheez ki demand ho
- Server → data provider, jo request ko poora karta hai

**Network:**
- Internet ka ek hissa
- Do devices (wire ya wireless) connect ho kar network banati hain

**DHCP:**
- Manual → khud IP assign karna
- DHCP → automatic IP assign hota hai (jaise WiFi password verify hone par)

**Network Types:**
- LAN → local area (chhota area)
- WAN → country to country
- MAN → city level, public network

**Router:**
- Gateway ki tarah kaam karta hai
- Router ke neeche → private network
- Router ke upar → public network (internet)

**Switch vs Hub:**
- Hub → data sab devices ko broadcast karta hai, no privacy
- Switch → data sirf specific/main receiver ko bhejta hai, zyada secure

**Data Flow:**
- Device → Switch → Router → ISP → Internet
