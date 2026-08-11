# PACKAGE MANAGEMENT IN LINUX

## 1. Repository?

Repository basically Linux ka "Play Store" hoti hai. Jaise Kali Linux ki apni repository hoti hai.

Simple, repository ek **online server** hoti hai jahan hazaron packages/software store hote hain. Jab hamein koi software chahiye hota hai to hum command k through install karte hain, aur wo command us package ko online repository/server se fetch karke install kar deti hai.

Install command:

```
sudo apt install nmap
```

Yahan **apt** = **Advanced Package Tool**, ye manager hi hota hai jo package install, remove, update sab karta hai.

Example:

```
sudo apt install vlc -y
```

(-y ka matlab hai ke confirmation ("yes/no") automatically "yes" ho jaye, rukna nahi.)

For Version:

```
nmap --version
nmap -v
```

---

## 2. Tow ways of installing

1. **apt** – seedha online repository se install karta hai, dependencies khud handle karta hai.
2. **dpkg -i** – manually downloaded .deb file se install karta hai, dependencies khud handle nahi karta.

---

## 3. apt update — use

```
sudo apt update
```

Ye command **repo check karti hai** — matlab ye dekhti hai ke repo mein packages ki list mein koi **new version aaya hai ya nahi**. Ye sirf list update karti hai, kuch install NAHI karti. Bas "kya naya aaya hai" ye pata karti hai.

---

## 4. apt upgrade — use

```
sudo apt upgrade
```

Ye command actual mein install karti hai jo naya version apt update ne find kiya tha. Ek level se next level pe, ek version se next version pe le jaati hai (yani actual upgrade karti hai).

---

## 5. Restaurant Example (update vs upgrade)

Socho ek restaurant hai:
- Restaurant ki purani menu list hai (ye hamari local package list hai).
- **apt update** = waiter jaake pata karta hai ke menu list update honi chahiye ya nahi, yani naye items check karta hai (server se new version ki khabar leta hai).
- **apt upgrade** = restaurant actual mein purani menu ko nayi menu se replace kar deta hai (yani asal mein install/upgrade kar deta hai).

Short: **update = search for new updates**, **upgrade = actually apply/install those updates**.

---

## 6. apt search

Ye check karne k liye use hota hai ke koi package repository mein maujood hai ya nahi.

```
apt search nmap
```

---

## 7. apt show

Ye kisi package ki detail information dikhata hai (version, size, dependencies, description waghera).

```
apt show nmap
```

---

## 8. apt install k 5 steps (jab install karte hain to andar kya hota hai)

Jab hum "sudo apt install <package>" likhte hain to ye 5 steps chalte hain:

1. **Package list mein dhoondna** – apt package list mein check karta hai ke package maujood hai.
2. **Dependencies check** – dekha jaata hai is package ko chalne k liye aur kya kya chahiye.
3. **Confirmation** – system batata hai kya install hoga, aur confirm karwata hai (agar -y na diya ho).
4. **Download + GPG verify** – package download hota hai, aur uska signature GPG (GNU Privacy Guard) se verify hota hai — taake pata chale ye original company ka hi package hai, tampered/fake nahi hai.
5. **Installed** – aakhir mein package install ho jaata hai.

**Checking installed packages:**

```
dpkg -l
```

Ye sab installed packages ki list dikhata hai.

---

## 9. Dependencies kya hoti hain

Jab hum koi app install karte hain, to us app ko chalne k liye kabhi kabhi kuch aur cheezein (chhote packages) bhi chahiye hoti hain — inhe **dependencies** kehte hain.

Example: "Uber" app install ki. Uber k andar "Map" bhi ek dependency ki tarah use hoti hai — bina map k Uber sahi se kaam nahi karega.

**apt install ka process is tarah samjho:**

1. apt (tool)
2. Repo (jahan se package aata hai)
3. Authenticity (asli hai ya nahi check hota hai)
4. Signature (original hai ya nahi verify hota hai)
5. Install (aakhir mein install ho jaata hai)

**Rule:** Agar app kisi cheez pe depend karti hai (dependency chahiye), to wo dependency bhi install honi zaroori hai. Agar dependency install nahi hui, to app "broken" ho jaayegi (theek se kaam nahi karegi).

---

## 10. .deb file se manually install karna (dpkg method)

Agar koi package repository mein available na ho, to hum usko **.deb file** se manually install kar sakte hain. Linux/Ubuntu mein .deb files hoti hain software k liye.

**Step 1:** File download karo wget se:

```
wget https://example.com/package.deb
```

**Step 2:** Us .deb file ko dpkg se install karo:

```
sudo dpkg -i package.deb
```

**Step 3:** Agar dependencies missing hone ki waja se install fail ho jaye, to fix karne k liye:

```
sudo apt install -f
```

Yahan **-f** ka matlab hai "fix broken" — ye command khud dhoond k missing dependencies install kar deti hai (kyunke dpkg khud dependencies download nahi karta).

---

## 11. /etc/apt/sources.list? 

Ye file yahan hoti hai:

```
/etc/apt/sources.list
```

Isko **sources list** kehte hain. Is file mein un saari repositories k addresses (links) likhe hote hain jahan se system packages fetch karta hai.

**Restaurant Analogy (sources.list):**
Socho ye file un restaurants (repositories) ki list hai jahan se aapko khana (packages) order karne ki ijazat hai. Linux isi list ko check karta hai ye jaanne k liye ke package kahan se lena hai.

---

## 12. Package genuine/original hai ya nahi — kaise pata chale (install karne se pehle)

Software install karne se pehle system ye cheezein check karta hai taake pata chale package safe aur asli hai:

1. Package **official developer** se aaya ho, kisi random/unofficial jagah se nahi.
2. **Download k dauran** koi bhi (beech mein) file ko change/tamper na kare (isiliye GPG signature verify hota hai — confirm karta hai file change nahi hui).
3. Package ka signature/checksum official source k signature se match karta ho (originality confirm hoti hai).

---

## 13. File System mein location dhoondne wali commands

Ye commands file/program ki location pata karne k liye use hoti hain:

- **ls** → Current location (folder) mein jitni files/folders hain wo list karta hai.
- **which** → Kisi command/program ki exact location (path) batata hai. Example: "which nmap" — ye batayega nmap system mein kahan install hai.
- **whereis** → "which" jaisa hi hai, lekin thoda zyada detail deta hai — binary file, source, aur man page (manual) sab ki location ek saath deta hai.

Example:

```
which nmap
whereis nmap
```
