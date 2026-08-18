# IP Addressing, Routers, NAT, DNS & Binary Conversion

---

## 1. IP Address?

**IP Address** har device ka ek unique address hota hai jiske through internet par devices ek dusre ko identify aur pehchan karte hain — jaise har ghar ka apna address hota hai taake dak (post) sahi jagah pohanch sake.

**Example diya gaya:** `192.168.1.1` , `192.168.1.2` , `192.168.1.3` , `192.168.1.4`

Ye IP addresses **private network** ke andar devices ko diye jate hain (jaise ghar/office ke andar).

---



## 2. Router Kaise Kaam Karta Hai (Public vs Private IP)

Jab hum kisi website/server ko request bhejte hain to poora process kuch is tarah hota hai:

1. Aapka device request bhejta hai internet ki taraf
2. Router aapki request ko **public IP address** ke through internet tak pohanchata hai
3. Server (website) response wapas usi **public IP** par bhejta hai
4. Response **router** tak wapas aata hai
5. Router dekhta hai ke — "ye public IP hai, aur mere paas is se link private IP hai"
6. Router pehchan leta hai ke **konsa device** us private IP ka malik hai
7. Router phir wo data sahi device tak forward kar deta hai

**Simple flow:**

```
Device (private IP) → Router → Internet (public IP se request jati hai)
Server response → Public IP → Router → Router pehchanta hai konsa device → Sahi Device tak data pohanchta hai
```

**Key point:** Router ek tarah ka "receptionist" hai — bahar (internet) ko sirf ek public IP nazar aata hai, lekin andar (local network) mein router jaanta hai ke ye data asal mein kis device ke liye hai.

**Public IP ka real example:**

```
223.123.124.206
```

Ye wo IP address hai jo **koi bhi website dekhti hai jab aap us se connect karte hain** — yani internet ki nazar mein yahi aapki "pehchan" hai (poori identity nahi, sirf routing address).

---



## 3. Packets Kaise Transfer Hote Hain

- Data ko chote-chote hisso mein tor kar bheja jata hai jinhe **packets** kehte hain
- Ye packets IP address se IP address tak safar karte hain
- Ye transfer **milliseconds** (bohat kam waqt) mein ho jata hai — is liye internet itna fast lagta hai

---



## 4. IPv4 Address Ki Structure — "4 Boxes" Concept

Har IP address ko **4 boxes (octets)** mein divide kar ke socho.

```
[ Box 1 ] . [ Box 2 ] . [ Box 3 ] . [ Box 4 ]
```

- Har box ke darmiyan ek **dot (.)** hota hai
- Har box mein number **0 se 255** tak ho sakta hai
- Har box **8-bit** ka hota hai (binary mein)
- 4 boxes × 8-bit = **32-bit address** (total)

**Example:** `192.168.1.1` → Box1=192, Box2=168, Box3=1, Box4=1

---



## 5. Binary → Decimal Conversion (Bit Position Table)

### Bit Position Table


| Bit Position | 2⁷  | 2⁶  | 2⁵  | 2⁴  | 2³  | 2²  | 2¹  | 2⁰  |
| ------------ | --- | --- | --- | --- | --- | --- | --- | --- |
| **Value**    | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |


**Idea ye hai:** har position ki apni fix value hoti hai (128, 64, 32, 16, 8, 4, 2, 1). Jahan binary mein "1" ho, wahan ki value ko jama (add) kar lo — jahan "0" ho usay ignore kar do. Total jama = decimal number.

### Example: IP `172.168.12.1`


| Octet | Binary     | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | Decimal Result |
| ----- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- | -------------- |
| Box 1 | `10101100` | 1   | 0   | 1   | 0   | 1   | 1   | 0   | 0   | **172**        |
| Box 2 | `10101000` | 1   | 0   | 1   | 0   | 1   | 0   | 0   | 0   | **168**        |
| Box 3 | `00001100` | 0   | 0   | 0   | 0   | 1   | 1   | 0   | 0   | **12**         |
| Box 4 | `00000001` | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 1   | **1**          |


**Calculation kaise hui (Box 1 — 172 ka example):**

```
128 + 32 + 8 + 4 = 172
(jahan binary mein 1 tha, sirf unhi values ko jama kiya)
```

**Final IP address:** `172.168.12.1`

### Manual Subtraction Method (Decimal → Binary)

Bade number se chota karte jao (subtraction method), taake pata chale kaun se bits "1" hain. Ye Box 2 (`168`) ka example tha:


| Step | Calculation  | Result               | Bit Decide Hua       |
| ---- | ------------ | -------------------- | -------------------- |
| 1    | 168 − 128    | 40 (bacha)           | 128 ki jagah **1**   |
| 2    | 40 − 64      | Nahi ho sakta (X)    | 64 ki jagah **0**    |
| 3    | 40 − 32      | 8 (bacha)            | 32 ki jagah **1**    |
| 4    | 8 − 16       | Nahi ho sakta (X)    | 16 ki jagah **0**    |
| 5    | 8 − 8        | 0 (bacha)            | 8 ki jagah **1**     |
| 6    | Baqi (4,2,1) | 0 bacha hai to sab 0 | 4,2,1 ki jagah **0** |


**Result:** `168` = `10101000` ✅ (ye wahi answer hai jo table mein bhi mila)

**Simple tareeqa yaad rakhne ka:**

- Sabse bari value (128) se shuru karo
- Agar number us value se bara ya barabar hai → subtract karo, us position par **1** likho
- Agar number us value se chota hai → us position par **0** likho, aur agli (chhoti) value try karo
- Jab tak number 0 na ho jaye, yehi process repeat karo

---



## 6. Quick Recap


| Topic          | Kya seekha                                                                                    |
| -------------- | --------------------------------------------------------------------------------------------- |
| IP Address     | Har device ka unique identifier — internet par pehchan ke liye                                |
| Router         | Public IP se aane wala data sahi private-IP device tak forward karta hai                      |
| Public IP      | Bahar ki duniya (websites) ko yahi IP nazar aata hai (e.g. 223.123.124.206)                   |
| Packets        | Data chote hisso mein bant kar milliseconds mein transfer hota hai                            |
| IPv4 Structure | 4 boxes (octets), har ek 0-255, 8-bit = total 32-bit address                                  |
| Binary→Decimal | Bit position table (128,64,32,16,8,4,2,1) se convert karna — jahan 1 ho wahan value jama karo |
| Decimal→Binary | Subtraction method — bari value se chota karte jao, 1/0 decide karo                           |


---

