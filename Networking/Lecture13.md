# Subnetting

## Subnetting Kya Hai

**Subnetting** ka matlab hai **ek network ko sub-networks (chhote chhote networks) mein divide karna** matlab ek bade network ko divide kar ke usay kayi **small networks** mein badalna.

**Subnetting Purpose:**

 Subnetting is liye ki jati hai taake network ko behtar tareeqe se organize kiya ja sake aur resources (jaise IP addresses) ko waste hone se bachaya ja sake.

---

## /26 Subnet Kya Hai

**Total Range:**

```
0 - 255
```

Ek normal IP address ki host range 0 se 255 tak hoti hai.

### Total Bits & Network Bits

**Network Bits:**

```
/26
```

Is subnet mein **26 bits** network ke liye reserve hote hain.

**Total Bits:**

```
32 bits
```

Har IPv4 address mein total **32 bits** hote hain.

### Host Bits Calculatation

**Host Bits Ka Formula:**

```
Total Bits - Network Bits = Host Bits
32 - 26 = 6
```

Matlab **6 bits** host addresses ke liye bache hain.

### Total Addresses Calculation

**Formula:**

```
2^6 = 64
```

Chunk ke **6 host bits** hain, is liye total **64 addresses** is subnet mein present hain.

### Usable Hosts Calculation

**Formula:**

```
64 - 2 = 62
```

In 64 addresses mein se **2 addresses reserve** hote hain (ek Network Address ke liye aur ek Broadcast Address ke liye), is liye baaki **62 addresses** hi **usable** hote hain  jo actual devices (jaise computers, printers) ko assign kiye ja sakte hain.

**Kyun /26 Address Use Karte Hain:**
`/26` address ka use is liye kiya jata hai taake network ko **safe aur organized** rakha ja sake matlab har chhoti subnet mein sirf itni hi IP addresses hon jitni zaroorat ho, taake koi waste na ho aur security bhi maintain rahe.

**Usable Addresses Kis Ke Liye:**
Ye 62 usable addresses **computers, printers**, aur doosre devices ke liye use hote hain jo network ka hissa banty hain.

---



## Subnet Address & Range (Lab 1)

**Subnet Address:**

```
192.168.1.0/26
```

**Usable Range:**

```
192.168.1.1 - 192.168.1.62
```

**Broadcast Address:**

```
192.168.1.63
```

Is subnet mein `192.168.1.0` **network address** hai (jo devices ko assign nahi hoti), aur `192.168.1.63` **broadcast address** hai (jo bhi devices ko assign nahi hoti). In dono ke darmiyan `192.168.1.1` se `192.168.1.62` tak ki addresses **usable** hain.

---



## Lab 2 — Second Subnet

**Subnet Address:**

```
192.168.1.64/26
```

**Usable Range:**

```
192.168.1.65 - 192.168.1.126
```

**Broadcast Address:**

```
192.168.1.127
```

Is doosri subnet mein `192.168.1.64` network address hai, aur `192.168.1.127` broadcast address hai. Darmiyan mein `192.168.1.65` se `192.168.1.126` tak ki addresses **62 usable hosts** ke liye available hain.

---



## Network & Broadcast Address Concept

**Har Network Ke Liye:**
Har subnet mein **network address** aur **broadcast address** ek jaisa pattern follow karte hain matlab:

- **Network Address** → subnet ka pehla address hota hai (jo range start karta hai)
- **Broadcast Address** → subnet ka last address hota hai (jo range ko khatam karta hai)

**The 1st & Last Addresses Are Not Used:**

Har subnet ka **pehla address** (network address) aur **last address** (broadcast address) kisi bhi device ko assign nahi kiya jata ye dono addresses reserve hote hain, aur sirf mid wale addresses hi **usable** hote hain.

**Broadcast Address Working:** 

Broadcast address ka use tab hota hai jab kisi ko **poori subnet ke sab devices ko ek sath data bhejna** ho matlab agar broadcast address par koi data bheja jaye, to wo us subnet ke sari devices tak pohanch jata hai. (like group)

---



## Summary

**Subnetting Basic:**

- Ek bade network ko chhoti chhoti sub-networks mein divide karna
- Is se network organized rehta hai aur IP addresses waste nahi hote

**/26 Subnet Ki Calculation:**

- Total bits: 32
- Network bits: 26
- Host bits: 32 - 26 = 6
- Total addresses: 2^6 = 64
- Usable hosts: 64 - 2 = 62 (2 reserve hote hain: Network aur Broadcast Address ke liye)

**Lab 1 (Subnet 1):**

- Subnet Address: 192.168.1.0/26
- Usable Range: 192.168.1.1 - 192.168.1.62
- Broadcast Address: 192.168.1.63

**Lab 2 (Subnet 2):**

- Subnet Address: 192.168.1.64/26
- Usable Range: 192.168.1.65 - 192.168.1.126
- Broadcast Address: 192.168.1.127

**Important Points:**

- Har subnet ka pehla address (Network Address) aur last address (Broadcast Address) kisi device ko assign nahi hota
- Sirf mid wale addresses hi usable hote hain
- Broadcast address se subnet ke sari devices ko ek sath data bheja ja sakta hai

