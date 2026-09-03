# IP Address Types Aur NAT

## IP Address

**IP Address** har device ki ek **unique identity** hoti hai jo **change** ho sakti hai — matlab ye kabhi bhi change ho sakti hai (MAC address ke bar-aks jo permanent hota hai).

**IP Address Basic Working:**
IP address wo hoti hai jo **network** ke andar device ko access karne ke liye use hoti hai.

**Router Role:** 
Jab bhi koi device network se connect hoti hai, to **router** us device ko ek IP address deta hai.

---

## Network & Device Identity

Jab **network** kisi **device ko access** karta hai, to us device ki **identity** us ke IP address se hoti hai.

**Confirmation Method :**
IP address ke through ye confirm hota hai ke konsa device network mein maujood hai aur kis se data bheja ya liya ja raha hai.

---

## Data Packet & IP Address

**Data Packet Working:**
Har **data packet** ko **destination** tak bhejne ke liye use kiya jata hai.

**Traveling Route:**
Data packet apni destination tak pohanchne ke liye ek specific route follow karta hai — ye route **source IP** se shuru ho kar **destination IP** tak jata hai.

**Example:**
IP address Format
```
192.168.100.1
```
---

## Public IP & Private IP

Network mein IP address do tarah ke hote hain:

### Public IP
**Public IP** wo IP hai jo **internet** par directly accessible hoti hai — matlab ye IP poori duniya se access ki ja sakti hai.

### Private IP
**Private IP** wo IP hai jo sirf **local network** (jaise ghar ya office) ke andar use hoti hai — ye internet par directly accessible nahi hoti.

**IP Address Ranges:**
Har type ki IP address ke apne specific **ranges** hote hain jo batate hain ke wo Public hai ya Private.

---

## Private IP Ranges

Private IP address ke liye kuch specific ranges reserved hain:

**Range 1 (Class A):**
```
10.0.0.0 se 10.255.255.255 tak
```

**Range 2 (Class B):**
```
172.16.0.0 se 172.31.255.255 tak
```

**Range 3 (Class C):**
```
192.168.0.0 se 192.168.255.255 tak
```

Ye teeno ranges hamesha **Private** hi hote hain — inhe internet par directly access nahi kiya ja sakta.

---

## Public & Private IP Address Classes

**Public IP:** Public IP address ka koi bhi range internet par directly accessible hota hai.

**Private IP:** Private IP address **4 classes** mein divide hoti hai — har class ka apna specific range hota hai jo ghar ya office jaise chhote networks ke andar use hota hai.

---

## Request Method — Router to Internet

Jab koi device **request** bhejti hai:

1. Request pehle **router** tak jati hai.
2. Router us request ko aage **ISP (Internet Service Provider)** ko bhej deta hai.
3. ISP se hote hue request internet tak pohanch jati hai.

**IP Address Method:**
Is poore process mein IP address ye batata hai ke request kahan se aa rahi hai aur kahan jaani hai.

---

## NAT — Network Address Translation

**NAT (Network Address Translation)** ek aisa process hai jo **Private IP** ko **Public IP** mein **translate** karta hai.

**NAT Basic Working:**
Jab bhi koi device apni **Private IP** ke sath internet tak pohanchna chahti hai, to router NAT ke through us Private IP ko ek **Public IP** mein convert kar deta hai — taake wo request internet tak safar kar sake.

**Example:**
Agar ghar ke andar kayi devices hon, aur sab ki apni **Private IP** ho, to jab bhi wo internet access karti hain, to router unhe **same Public IP** ke through internet tak bhejta hai — matlab ghar ke sare devices bahar se ek hi Public IP se pehchane jate hain.

---

## Same IP, Different Devices

**Concept:**
**Same number (same IP)** — matlab ek hi **Private IP** **home, office, aur organization** teeno jagah repeat ho sakti hai. Private IP koi globally unique cheez nahi hoti, is liye alag alag networks mein wahi IP address dobara use ho sakta hai.

**Example:**
Agar **ghar ke router** ki IP aur **office ke router** ki IP dono **same** hain, to ye bilkul normal hai — koi masla nahi, kyun ke ye dono **alag locations** par hain.

**Different Location Concept:**
Ek hi Private IP **different locations** par hoti hai — matlab same IP number ghar mein bhi ho sakta hai aur office mein bhi, kyun ke Private IP sirf us local network ke andar hi valid hoti hai, poori duniya mein unique hone ki zaroorat nahi hoti (jaisa Public IP ke sath hota hai).

---

## NAT Practical Working

**NAT Base Request Process:**

1. **Private IP se Request:** Device apni Private IP se ek request bhejti hai.

**Example — Private IP:**
```
192.168.1.1
```

2. **Router Ka Kaam:** Router is Private IP ko apni **Public IP** ke sath translate kar deta hai, taake request internet tak jaa sake.

**Example — Public IP:**
```
203.1.56.134
```

3. **Router Ki Table Mein Entry:** Router ke andar ek **table** hoti hai jis mein ye record store hota hai ke konsi Private IP, konsi Public IP se translate hui thi.

**Table Ka Kaam:**
Router ye table isliye maintain karta hai taake jab response wapas aaye, to usay pata ho ke ye response konsi Private IP (device) ke liye tha.

---

## Website Access Example

**Practical Flow:**
Agar koi device kisi website (jaise google.com) ko access karna chahti hai, to:

1. Device apni Private IP se request bhejti hai.
2. Router us request ko apni Public IP mein translate karta hai.
3. Request google.com tak pohanchti hai.
4. Response wapas aata hai to Router apni **table** dekh kar ye pata karta hai ke ye response kis Private IP (device) ke liye tha.
5. Router response ko wapas usi **original device** tak bhej deta hai — is process ko **"travel back"** kaha ja sakta hai, matlab data wapas apni asal original device tak pohanch jata hai.

**Table Storage:**
Ye poori entry (Private IP aur Public IP ka mapping) router ki table mein **store** hoti hai jab tak request active rehti hai.

**Request Complete Hone Ke Baad:**
Jab request **complete** ho jati hai, to table se wo entry **delete** ho jati hai — matlab ye ek **temporary record** hota hai jo sirf jab tak request active ho tab tak maintain kiya jata hai.

**Naye Request Process:**
Agar dobara koi request aati hai, to Private IP dobara **Public IP** mein convert hoti hai — ye poora process har naye request ke sath dobara hota hai.

---

## Summary

**IP Address Basics:**
- IP address unique hoti hai lekin change ho sakti hai
- Router device ko IP address deta hai
- Data packet destination tak IP ke zariye pohanchta hai

**Public vs Private IP:**
- Public IP → internet par directly accessible
- Private IP → sirf local network ke andar use hoti hai

**Private IP Ranges:**
- Class A: 10.0.0.0 – 10.255.255.255
- Class B: 172.16.0.0 – 172.31.255.255
- Class C: 192.168.0.0 – 192.168.255.255

**NAT (Network Address Translation):**
- Private IP ko Public IP mein translate karta hai
- Router ke andar ek table hoti hai jo Private-Public IP mapping store karti hai
- Response wapas aane par table se check kar ke original device tak bheja jata hai
- Request complete hone ke baad table entry delete ho jati hai

**Practical Flow:**
- Device (Private IP) → Router (NAT translation) → Public IP → Internet → Response wapas → Router table check → Original device tak delivery
