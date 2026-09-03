# IP Subnetting - (Visual Masterclass)

## 1. IPv4 Basics

IPv4 address 32 bits ka hota hai, jo 4 octets (parts) mein divide hota hai. Har octet 8 bits ka hota hai.

8 x 4 = 32 bits (IPv4)

Har octet ki value 0 se 255 tak ho sakti hai (octal range 0-255).

## 2. Networking Basics – Devices Kaise Connect Hoty Hain

Jab 2 devices ko connect karna ho, to data Wi-Fi router ke through jata hai. Router hi devices ke beech data ka rasta banata hai.

**Switch vs Hub:**

- Hub: Hub data ko sab connected devices ko bhej deta hai (broadcast karta hai), chahe wo data kisi ek device ke liye ho. 
- Switch: Switch smart hota hai, ye sirf us specific device ko data bhejta hai jiske liye wo data hota hai, na ke sab ko.

Network private bhi ho sakta hai ya public bhi.

## 3. Ek Ghar/Lab Mein Multiple Devices Example

Agar ek ghar mein 4 PC hain, to wo sab aapas mein data send kar sakty hain.

**Lab Example:** Jab multiple computers ya devices connect hoty hain, to har device ka IP address different hota hai. Sirf last octet (box 4) 1 se 255 tak change hota hai, baki 3 octets same rehte hain.

Example:

- 192.168.1.10
- 192.168.1.11
- 192.168.1.12

**Reason:** Pehle 3 octets "192.168.1" same rehty hain kyunke ye ek hi Lab/Network ko represent karty hain. Sirf last octet alag hota hai jo us lab ke andar har computer/device ko unique identity deta hai. Yani jitne bhi devices ek lab (network) mein honge, unka pehla hissa "192.168.1..." same hi rahega, sirf last number different hoga.

## 4. Private IP Addresses

Private IP addresses hamesha 192.168 se start hoty hain. Ye starting part change nahi ho sakta – ye fixed rehta hai for private networks.

- 192.168.1.10 → Lab 1, Device 10
- 192.168.2.10 → Lab 2, Device 10
- 192.168.4.20 → Lab 4, Device 20

Yani 3rd (1,2,4) octet alag alag Labs/Networks ko represent karta hai, aur 4th (10,10,20) octet us Lab ke andar device number batata hai.

## 5. IP Address Structure (Network Part & Host Part)

Ek IP address do parts mein divide hota hai:

- **Network Part:** Kaunsa lab/network hai, ye batata hai.
- **Host Part:** Us network ke andar kaunsa device/computer hai, ye batata hai.

255 computers tak ek network mein connect ho sakty hain (ek octet ki max range hone ki wajah se).

Example: 192.168.1.10 /24
8 + 8 + 8 + 8 = 32 bits
"/24" ka matlab hai ke pehle 3 boxes (octets) Network ko represent karte hain, aur last octet Host (device number) ko represent karta hai.

## 6. CIDR Notation

CIDR (Classless Inter-Domain Routing) notation IP address ke sath likha jata hai jaise /8, /16, /24, /30, /32 waghera. Ye batata hai ke IP ke 32 bits mein se kitne bits **Network** ke liye reserved hain aur baki kitne bits **Host** ke liye available hain.

**Kyun 2 departments alag rakhy jaty hain:**
Agar ek hi network par 2 departments connect ho jayein, to attack (security breach) ka chance barh jata hai. Isi liye har department/lab ko alag alag network (alag IP range) diya jata hai taake security maintain rahe.

192.168.1.1 par "bit break" (CIDR /number) decide karta hai ke konsa bit Network show karega aur konsa Host show karega.

192.168 → ye class/address group represent karta hai (jese CS ya BS department).
1.1 → ye computer ki number/host ko represent karta hai.

## 7. Octet to Binary Conversion (Method)

Har octet ko binary mein convert karne ke liye ye values use hoti hain:
128, 64, 32, 16, 8, 4, 2, 1

In 8 values ko add/subtract karke octet ki value nikali jati hai, aur jahan value use ho wahan 1, jahan na ho wahan 0 likha jata hai.

**Example: 192.168.1.9**

- 192 = 11000000
- 168 = 10101000
- 1   = 00000001
- 9   = 00001001

Full binary: 11000000.10101000.00000001.00001001 (total 32 bits)

**Example: 192.168.1.14**

- 192 = 11000000
- 168 = 10101000
- 1   = 00000001
- 14  = 00001110

Full binary: 11000000.10101000.00000001.00001110 (32 bits)

## 8. Network Bits & Host Bits

Formula: Host bits = 32 – (CIDR number)

**192.168.1.1 /8**
Host bits = 32 - 8 = 24
Full binary: 11000000.10101000.00000001.00000001
Network part (8 bits): 11000000
Host part (24 bits): 10101000.00000001.00000001

**192.168.1.1 /16**
Host bits = 32 - 16 = 16
Network part (16 bits): 11000000.10101000
Host part (16 bits): 00000001.00000001

**192.168.1.1 /24**
Host bits = 32 - 24 = 8
Network part (24 bits): 11000000.10101000.00000001
Host part (8 bits): 00000001

**192.168.1.14 /28**
Host bits = 32 - 28 = 4
Network bits: 28
Host part (last 4 bits): 1110

**192.168.1.9 /18**
Host bits = 32 - 18 = 14
Network part (18 bits): 11000000.10101000.00
Host part (14 bits): 000001.00001001

**192.168.1.1 /30**
Host bits = 32 - 30 = 2
Network bits: 30
Host part (2 bits): 01

**192.168.1.1 /32**
Host bits = 32 - 32 = 0
Network bits: 32 (poora address hi network/single device ko represent karta hai)
Host bits: 0

Note: Jitna bara CIDR number hoga (jese /30, /32), utne kam devices us network mein fit ho sakty hain, kyunke host bits kam reh jaty hain. Aur jitna chota CIDR number hoga (jese /8), utne zyada devices accommodate ho sakty hain.

## 9. Important Reference IPs

- 192.0.0.0/8 → Network address example
- 192.255.255.255.0
- 129.255.255.255.1
- 192.255.255.255

(Ye reference/example addresses hain jo subnetting practice ke liye likhi gayi.)

## 10. Practical Use – Network Designer Task

Jab ek Network Designer kaam karta hai, to wo alag alag departments/labs ke liye alag subnet (CIDR) design karta hai taake:

1. Har department ka network alag rahe.
2. Security barh jaye (ek department ka attack dusre tak na phaile).
3. IP addresses waste na hon – zaroorat keaccording hi host bits allot ki jayein.

**Firewall role:** Firewall Network ke rules apply karta hai. Network bits lab/department ko represent karty hain, aur Host bits us network ke andar device/computer ko represent karty hain. Firewall inhi rules ke through control karta hai ke konsa traffic allow hoga aur konsa block.
