# Internet, Network Aur Web Tools

## Internet Kya Hai

**Internet** ek aisa network hota hai jo **region** (jaise Asia, Atlantic) ya **multiple countries** ko aapas mein connect karta hai. Ye ek bohat bada network hai jo poore world ko jorta hai.

**Scope according difference:**
- **Region/Country Level:** Internet ek poori region ya multiple countries ko connect karta hai.
- **City Level:** Isi tarah agar sirf ek city ke andar multiple offices ya houses connect hon, to wo bhi ek network hai lekin chhote scale par.
- **House/Office Level:** Ek ghar ya office ke andar bhi devices aapas mein ek chhota network bana sakte hain.

**Data Sharing:** Jab devices ek network ke andar aapas mein data share karte hain, to us poore system ko **network** kaha jata hai — aur jab ye network **country ke level** tak phel jata hai, to usay **internet** kehte hain.

---

## Network Kya Hai

**Network** wo tareeqa hai jis se ek network ke andar devices ek doosre se, ya ek network se doosre network tak, **connect ho sakte hain**.

Matlab network sirf devices ko aapas mein jodne ka system hai — chahe wo ek ghar ke andar do computers hon, ya poori duniya ke devices.

---

## IP Address

**IP (Internet Protocol) Address** har device ki apni ek unique identity hoti hai network ke andar, jis se wo pehchana jata hai.

**Example:** Home router ek IP address rakhta hai jis se wo network mein pehchana jata hai.

### NIC — Network Interface Card

Har device (jaise laptop) ke andar ek **Network Interface Card (NIC)** hota hai. Jab bhi koi device internet se connect hoti hai, to us device ka apna NIC hota hai jo connection banane mein madad karta hai.

### MAC Address

Jab koi device banai jati hai, to us par **MAC address** likh diya jata hai — ye ek permanent (fixed) address hota hai jo har device ke NIC ke sath hamesha ke liye juda hota hai.

**Kaam Karne Ka Tarika:**
Agar koi mobile device ko wifi router se connect karna chahe, to router us mobile ka **MAC address** dekhta hai aur badle mein us device ko ek **IP address** assign kar deta hai — taake wo device network mein pehchani ja sake.

### MAC Address vs IP Address — difference

- **MAC Address:** Kabhi **change nahi hota** — ye device ke sath permanently juda hota hai (hardware level identity).
- **IP Address:** **Change ho sakta hai** — jab bhi device kisi naye network se connect hoti hai, to usay naya IP address mil sakta hai.

**IP Address Kaun Deta Hai:**
IP address hamesha **router** deta hai, jis se device internet use kar sakti hai.

---

## Network Commands

### `ip address`
Ye command device ka **IP address** dikhane ke liye use hoti hai.

### Loopback (lo)
**Loopback** ek special network interface hota hai jo device ko **apne aap ko hi call karne** ke liye use hota hai — matlab isay "local host" bhi kaha jata hai. Ye khud device ke andar internal testing/communication ke liye use hota hai.

**Important Point:** Loopback ka address **permanent** hota hai — ye kabhi change nahi hota.

### wlan0
**wlan0** wo interface hai jo **direct WiFi se connect** hone par active ho jata hai. Agar device mein WiFi maujood na ho, to `wlan0` interface bhi list mein nahi aayega.

### eth0
**eth0** wo interface hai jo **wire (cable) se connect** hone par use hota hai — matlab jab device Ethernet cable ke zariye internet se juda hota hai.

### `hostname -i`
Ye command device ka **IP address**, **router ka IP**, aur **MAC address** — teeno information ek sath show karti hai.

---

## Ping Aur Traceroute

### Ping
**Ping** command kisi doosre device ko **"Hello" kehne** jaisa kaam karti hai — matlab ye check karti hai ke koi device **active (alive)** hai ya nahi.

**Ping work:**
Ping ek data ka packet resi device ko bhejti hai taake pata chal sake ke wo device abhi active hai ya nahi. Data packets ke zariye ek device doosre device ko data send karti hai.

**Important Note:** Agar kisi device par **firewall** ya **VPN** use ho raha ho, ya device **off** ho, to us waqt ping kaam nahi karegi — response nahi milega.

**Example — Ping Ek Fixed IP Ko:**
```
ping 8.8.8.8
```

**Example — Ping Local Network Address Ko:**
```
ping 192.168.100.1
```

**Ping Output Ka Result:**
```
64 bytes from 192.168.100.1: icmp_seq=1
```

Is result mein:
- **64 bytes** → packet ka size hai
- **icmp_seq** → packet ki sequence number hai (har baar ping bhejne par ye number badhta hai)

```
ttl=64 time=4.24 ms
```

- **ttl (Time To Live)** → batata hai ke packet kitne "hops" (network devices, stop) tak travel kar sakta hai qabl is ke wo drop ho jaye
- **time** → response aane mein kitna time laga (milliseconds mein)

**Important Point:** Jaise jaise ping ka **time (response time) kam hota jaye**, iska matlab hai ke connection **fast aur stable** ho raha hai.

### Traceroute
**Traceroute** command ye check karti hai ke data packet **kin kin devices (hops,stops)** se guzar kar apni final location tak pohanchta hai — matlab ye poora raasta (path) trace karti hai jahan se packet guzarta hai.

**Example:**
```
traceroute google.com
```

Ye command root se lekar **google.com** tak jane wale route ko trace karti hai — ye dikhati hai ke packet kin kin devices ke through guzar kar, kitni requests dene ke baad apni location tak pohancha.

**Hop Limit:**
```
hop: 30 max
```
Traceroute maximum **30 hops** tak track karti hai.

**TTL Example (Google):**
```
ttl=64
```

**Packet Ka Safar (Google Example):**
Jab hum internet par koi request bhejte hain, to sabse pehle wo hamare **device** se **router** ke through **ISP** tak pohanchata hai, jahan pehle **DNS resolve** hota hai — yani jis website ka naam humne dala hai, uska IP address maloom kiya jata hai. Uske baad request internet ke **kai intermediate routers (hops, stop)** se guzarti jati hai, jab tak wo apni **destination server** (jaise Google ke data center) tak nahi pohanch jati. Wahan se server response taiyar karta hai aur wahi response ulte raste se wapis hamare device tak pohanch jata hai.

```
Device → Router → ISP → DNS → Internet (hops,stop) → Server → wapis Device
```

---

## curl Command

**curl** command kisi bhi website ya URL ka data terminal mein directly fetch karne ke liye use hoti hai.

**Basic Example:**
```
curl https://google.com
```

**Detailed Info Ke Sath:**
```
curl -i https://google.com
```

`-i` flag lagane se curl **general information (headers)** bhi dikhata hai — jaise response status, server info, wagera.

**curl Ka Use — Safety Check:**
`curl` ka use kisi website ki safety check karne ke liye bhi hota hai — is se URL ki **location, format**, aur response dekha ja sakta hai, taake pata chale ke wo link sahi hai ya nahi.

---

## wget Command

**wget** command files ya poori websites ko **download** karne ke liye use hoti hai.

**Example (Real-Life Analogy):**
Jaise agar hum kisi restaurant ki website ka data download karna chahen, to `wget` us website ka content local system mein save kar deta hai.

**wget Ka Kaam:**
- Install (agar zaroorat ho) kar ke internet se cheezein download karta hai
- **Background mein** kaam karta hai, matlab download hote waqt terminal ko lock nahi karta
- Poore **files aur folders** download kar sakta hai (na ke sirf ek page)

**curl vs wget:**
- `curl` → data ko fetch kar ke **screen par dikhata** hai
- `wget` → data ko **download kar ke save** karta hai

---

## Browser

**Browser** ek software (application) hota hai jo humein internet par websites dekhne aur unse interact karne deta hai.

**Browser Ki Functionality:**
- Websites ko **load aur display** karta hai
- **Search engine** ke zariye information dhoondne mein madad karta hai
- URLs ko process kar ke unka content screen par show karta hai

---

## SSH — Secure Shell

**SSH (Secure Shell)** ek protocol hai jo **remote device** ko secure tareeke se connect aur control karne ke liye use hota hai.

**SSH importance:**
SSH ka connection **encrypted** hota hai — matlab is ke through bheja gaya data secure rehta hai aur beech mein koi asani se access nahi kar sakta.

**SSH Use:**
SSH ke through koi bhi apne **laptop ya device mein remotely login** kar sakta hai — matlab ek device se doosre device ko dur se access kiya ja sakta hai.

**SSH Connection Ka Format:**
```
ssh <username>@<hostname_ya_IP>
```

**Example:**
```
ssh banait@banait.labs
```

Is format mein username ke baad IP address bhi likha ja sakta hai us jagah jahan hostname likha hai.

**SSH Ka Port Number:**
```
SSH: 22
```
SSH by default **port 22** use karta hai communication ke liye.

---

## Telnet

**Telnet** bhi SSH ki tarah remote device ko connect karne ke liye use hota hai, lekin iska nuqsan ye hai ke ye **secure nahi** hota.

**Telnet issuse:**
Telnet ka connection **unencrypted** hota hai — matlab is ke through bheja gaya data **attackers** asani se dekh ya chura sakte hain. Isi wajah se aaj kal Telnet ki jagah SSH zyada use hota hai kyun ke wo secure hai.

---

## Summary

**Internet aur Network:**
- Internet → region/country level ka network
- Network → devices ke aapas mein connect hone ka tareeqa
- Data sharing → network ke andar hota hai

**IP aur MAC Address:**
- NIC → device ka network interface card
- MAC address → permanent, kabhi change nahi hota
- IP address → change ho sakta hai, router deta hai

**Commands:**
- `ip address` → IP dikhata hai
- Loopback (lo) → apne aap ko call karna, permanent address
- wlan0 → WiFi se connect hone par active
- eth0 → cable se connect hone par active
- `hostname -i` → IP, router IP, aur MAC address dikhata hai

**Ping aur Traceroute:**
- Ping → device active hai ya nahi check karta hai
- Traceroute → packet ka poora raasta (path) trace karta hai
**""Device → Router → ISP → DNS → Internet (hops,stop) → Server → wapis Device""**
- ttl → packet ki max hops ki limit
- Traceroute max 30 hops tak track karta hai

**Web Tools:**
- curl → data fetch kar ke screen pe dikhata hai
- curl -i → detailed info (headers) ke sath
- wget → files/websites download karta hai (background mein)
- Browser → websites dekhne aur search karne ka software

**Remote Access:**
- SSH → secure, encrypted remote connection, port 22
- Telnet → unsecure, easily attackable, isi liye SSH zyada use hota hai
