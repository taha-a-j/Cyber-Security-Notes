# SSH 

## 1. SSH?

* **Full Form:** Secure Shell (SSH)
* **Default Port:** Port 22
* **Purpose:** SSH ek secure network protocol hai jo kisi bhi remote system ya server ko securely access aur control karne ke liye use hota hai.
* **Working?** Jab hum apne laptop ya device se kisi doosri device ko access karte hain, toh SSH hamara login ID aur password direct plain text mein nahi bhejta. Yeh poore data aur connection ko encrypt kar deta hai.
* **Telnet && ssh:** Telnet mein hum jab request bhejte hain (ID/password), toh data plain text mein jata hai. Agar beech mein koi hacker sniffing ya man-in-the-middle (MITM) attack kare, toh wo easily password steal kar sakta hai. Is liye Telnet insecure hai aur SSH ek secure protocol hai.

---

## 2. SSHD (SSH Daemon)?

* **Full Form:** SSH Daemon (`d` ka matlab Daemon hota hai, jo Linux mein background process ko kehte hain).

* **Role / Purpose:** `ssh` ek client tool hai (jis se hum connection ki request bhejte hain), jab ke `sshd` wo background service hai jo **Server** par run ho rahi hoti hai aur incoming SSH connections ko listen (Port 22 par) aur handle karti hai.

* **Working** Jab aap client machine se `ssh username@ip` chalate hain, toh server side par `sshd` service aap ki request ko receive karti hai, password ya SSH key verify karti hai, aur verification sahi hone par aap ko server ka access deti hai.

* **Main Configuration File:** Linux servers par is ki settings `/etc/ssh/sshd_config` file mein hoti hain (jahan se Port number change karna ya password login disable karna configure kiya jata hai).

---

## 3. SSH Keys && Purpose

Remote system ko access karne ke liye baar baar password lagane ki zaroorat na pare, is ke liye hum SSH Keys ka istemal karte hain. Yeh password-based login se zyada secure authentication method hai.

### Key Pair Concept (Lock & Key)
SSH keys mein 2 parts hote hain:

1. **Public Key (Lock):**
   * Yeh key server par save hoti hai aur public hoti hai (is ko koi bhi dekh sakta hai).
   * **Standard File Path:** `~/.ssh/id_ed25519.pub` (ya `id_rsa.pub`)

2. **Private Key (Key):**
   * Yeh key aap ki apni local machine/laptop par rehti hai aur secret hoti hai. Is ko kisi ke sath share nahi kiya jata.
   * **Standard File Path:** `~/.ssh/id_ed25519` (ya `id_rsa`)

* **Access Control:** Jab private key (Key) public key (Lock) ke sath match hoti hai, tab bina password ke system securely unlock hota hai aur access mil jata hai.

---

## 4. SSH Command Basics & Examples

SSH ko Linux Terminal, Windows Command Prompt, ya PowerShell se run kiya ja sakta hai.

* **Basic Syntax:**
```
 ssh username@hostname_or_ip
 ```

* **Example (Bandit Game/CFT Challenge):** 
```
  ssh bandit0@bandit.labs.overthewire.org
```

* **Custom Port Example:** 
```
  Agar Port 22 ke alawa koi custom port ho toh `-p` flag lagaya jata hai:
  ssh -p 2220 bandit0@bandit.labs.overthewire.org
```

## 5. Operating Systems Support

**Linux:** Linux mein SSH by default built-in Terminal ke zariye fully supported hota hai. 

**Windows:** Windows mein Terminal, Command Prompt, PowerShell, ya third-party SSH clients (jaise PuTTY / MobaXterm) ke zariye use kiya ja sakta hai.

