# IP Addressing, IPv6 & Hexadecimal-Binary Conversion

---

### 1. IP Address Kya Hota Hai

IP address har device ka unique address hota hai — har device jo network par connect hota hai (chahe wo phone ho, laptop ho ya khud router), uska apna IP address hota hai. Network ke andar kisi bhi device ko identify ya search karne ke liye IP address use hota hai.

IPv4 address 4 hisso (bytes/octets) ka hota hai — example: `192.168.100.1`

Jab data packets network ke andar bhejay jate hain, to wo hamesha do IP addresses ke darmiyan travel karte hain:

- **Source IP** — jahan se data bheja ja raha hai
- **Destination IP** — jahan data pohanchna hai

---



### 2. Public IP & Private IP

IP addresses ko alag alag ranges categories mein divide kiya gaya hai taake unhein organize kiya ja sake.

- **Private IP Address:** Ye wo IP address hai jo sirf ek ghar ya office (local network) ke andar use hoti hai. Ye internet par direct kaam nahi karti — sirf andar ke devices ek dusre ko isi se pehchante hain.
- **Public IP Address:** Ye wo IP address hai jo internet par device ki pehchan karti hai. Jab andar (private network) se koi request bahar internet ki taraf router ke through agli ISP tak jati hai, to usi waqt wo request ki IP **"public"** ban jati hai — taake bahar ki duniya (internet) us device ko pehchan sake.

---



### 3. Maximum Value & Broadcast Address

Ek IP address (jaise `192.168.100.1`) ka har hissa (octet) zyada se zyada **255** tak ja sakta hai.

`255.255.255.255` bhi ek IP address hai, lekin ye ek khaas maqsad ke liye use hoti hai — isay **"Broadcast Address"** kehte hain. Ye ek sath sab devices ko data bhejne ke liye use hoti hai.

---



### 4. Private IP Address 3 Standard Ranges

- **1st Range:** `10.0.0.0` through `10.255.255.255`
- **2nd Range:** `172.16.0.0` through `172.31.255.255`
- **3rd Range:** `192.168.0.0` through `192.168.255.255`

Ye teen ranges hi wo IP addresses hain jo private networks (ghar/office) ke andar use hoti hain.

---



### 5. Public IP Kaise Banta Hai

Jab bhi router se koi request agli ISP (Internet Service Provider) ki taraf bheji jati hai, to us waqt wo IP **next public IP** ban jati hai NAT transltor k through — matlab andar ki private IP ab bahar ke liye ek public IP ki shakal mein represent hoti hai.

---



## IPv6



### 1. IPv6 Kya Hai

IPv6 ek naya IP addressing system hai jo IPv4 ki addresses khatam hone ki problem ko solve karne ke liye banaya gaya. IPv6 address **hexadecimal** format mein likha jata hai, aur har hissa **colon (:)** se separate hota hai.

**Example:**
`28ba : 239a : 5678 : 5555 : 09bc : 6756 : bdfe : 0987`

### 2. IPv6 Ki Structure

- Poora IPv6 address **8 groups (boxes)** mein hota hai
- Har group **16-bit** ka hota hai
- 8 groups × 16-bit = **128-bit total address**
- Har group **4 hexadecimal digits** (0-9, a-f) par mushtamil hota hai
- Har hex digit **4-bit binary** ke barabar hota hai (isi liye 4 hex digits × 4-bit = 16-bit ek group)



### 3. Hexadecimal → Binary Conversion (Method)

Method: Har hex digit ko uske 4-bit binary code se replace karo, aur sab ko ek sath jorh do — yehi 16-bit group ban jata hai.

**Example 1 — Group "28ba":**

- 2 = 0010
- 8 = 1000
- b = 1011
- a = 1010
- **Binary = 0010 1000 1011 1010** (16 bits)

**Example 2 — Group "239a":**

- 2 = 0010
- 3 = 0011
- 9 = 1001
- a = 1010
- **Binary = 0010 0011 1001 1010** (16 bits)

**Example 3 — Group "5678":**

- 5 = 0101
- 6 = 0110
- 7 = 0111
- 8 = 1000
- **Binary = 0101 0110 0111 1000** (16 bits)

Ye 16 bits ek group (box) mein store hoti hain — aur jab sab 8 groups yun hi convert kar liye jayein, to poora IPv6 address 128-bit ka ban jata hai.

**Quick Summary:**

- IPv4 = 32-bit (4 groups × 8-bit)
- IPv6 = 128-bit (8 groups × 16-bit) — hex digits use karta hai, isi liye zyada addresses accommodate kar sakta hai

---



## Hexadecimal to Binary



### Hexadecimal System Kya Hai

Hexadecimal ek number system hai jismein total **16 characters** hote hain: `0,1,2,3,4,5,6,7,8,9` aur phir `A,B,C,D,E,F` (jo decimal ke 10 se 15 ko represent karte hain).

Har hex character ko represent karne ke liye **4 bits (4-bit binary)** kaafi hoti hain — kyunke 4-bit binary se total **16 combinations** (0000 se 1111 tak) ban sakti hain, aur hexadecimal mein bhi 16 hi characters hain. Isi wajah se **1 hex digit = 4 binary bits** hamesha barabar hote hain.

### Table Method (Step by Step)

1. Decimal 0 se 15 tak ginti likho
2. Har decimal number ko 4-bit binary mein convert karo (bit position method use karo: 8, 4, 2, 1)
3. Jahan number 8 se bara/barabar ho → 1 likho, subtract karo; warna 0 likho aur agli value try karo (yehi process 4,2,1 ke sath bhi repeat karo)
4. 10 se 15 tak ke numbers ko hex letters (A-F) se represent karo:
  - 10 = A, 11 = B, 12 = C, 13 = D, 14 = E, 15 = F
5. Ab teen columns bana lo: **Decimal | Hex | Binary**



### Table


| Decimal | Hex | Binary |
| ------- | --- | ------ |
| 0       | 0   | 0000   |
| 1       | 1   | 0001   |
| 2       | 2   | 0010   |
| 3       | 3   | 0011   |
| 4       | 4   | 0100   |
| 5       | 5   | 0101   |
| 6       | 6   | 0110   |
| 7       | 7   | 0111   |
| 8       | 8   | 1000   |
| 9       | 9   | 1001   |
| 10      | A   | 1010   |
| 11      | B   | 1011   |
| 12      | C   | 1100   |
| 13      | D   | 1101   |
| 14      | E   | 1110   |
| 15      | F   | 1111   |




### Method

- 0-9 tak hex aur decimal same hote hain
- 10 se 15 tak letters use hote hain: **A, B, C, D, E, F** (alphabetical order mein 10 se shuru)
- Binary hamesha 4-bit ki hoti hai (chahe number chota ho jaise 1 = `0001`, leading zeros zaroor likho)



### Is Table Ka Use — IPv6 Mein

Jab IPv6 address ka koi bhi hex digit (jaise `b` ya `a`) convert karna ho, to bas isi table mein us letter ko dhoondo aur uski 4-bit binary utha lo. Yehi tareeqa upar IPv6 conversion examples (`28ba`, `239a`, `5678`) mein use hua hai.

---



## Recap


| Topic             | Key Point                                                                         |
| ----------------- | --------------------------------------------------------------------------------- |
| IP Address        | Har device ka unique identifier, network par pehchan ke liye                      |
| Private IP        | Sirf local network (ghar/office) ke andar use hoti hai                            |
| Public IP         | Internet par device ki pehchan — router se ISP tak jate hi ban jati hai           |
| Broadcast Address | `255.255.255.255` — sab devices ko ek sath data bhejne ke liye                    |
| Private Ranges    | 10.0.0.0–10.255.255.255 / 172.16.0.0–172.31.255.255 / 192.168.0.0–192.168.255.255 |
| IPv4 Size         | 32-bit (4 octets × 8-bit, range 0-255 har octet)                                  |
| IPv6 Size         | 128-bit (8 groups × 16-bit, hexadecimal format)                                   |
| Hex-Binary Rule   | 1 hex digit = 4 binary bits (kyunke 16 hex symbols = 2⁴ combinations)             |


