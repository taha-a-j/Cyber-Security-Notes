# Process Management, Services aur Ports

## Program Aur Process Diff:

**Program:** Program wo hota hai jo **install** kiya jata hai — matlab koi bhi application jo system mein hoti hai lekin abhi chal nahi rahi hoti.

**Process:** Jab koi program **run** krty hai, to wo ek **process** ban jata hai. Matlab process ek program ka wo halat hai jab wo actively CPU ke andar perform ho raha hota hai.

**Example:**
Agar hum ek file ko **click** karte hain, to us waqt wo file ek **process** ban jati hai jo current active window mein run ho rahi hoti hai. Matlab jab tak program sirf installed hai, wo "program" hai — jaise hi wo run hota hai, wo "process" ban jata hai.

**Important:** Ek hi program (jaise koi application) ke **multiple processes** bhi ho sakte hain — matlab ek program ko agar ek se zyada dafa ya alag alag windows/tabs mein chalaya jaye, to har ek ka apna separate process hoga.

---

## PID Aur PPID

Har process ki apni identity hoti hai jo do numbers se pehchani jati hai:

### PID (Process ID)

**PID** har process ki apni **unique identity number** hoti hai — jaise har insaan ka apna CNIC number hota hai, waise hi har process ka apna PID hota hai.

**Example:**
```
PID: netflix → 20
```
 Netflix process ki PID `20` hai.

### PPID (Parent Process ID)

**PPID** us process ki ID hoti hai jo **doosre process ko generate (create) karta hai** — matlab jis process ne is process ko start kiya hai, uski ID PPID kehlati hai.

**Example:**
```
PPID: youtube (child) → PID: 20
```
Agar YouTube process, Netflix process se generate hua ho, to Netflix ki PID (`20`) hi YouTube process ki PPID banegi — kyun ke Netflix (parent) ne YouTube (child) ko start kiya.

**Real Example (Web Service):**
```
PPID: sub PID (child) → PPID (web service)
```
Agar koi service (jaise web service) apne andar chhote sub-processes create karti hai, to un sab child processes ki PPID us parent web service ki PID hogi.

---

## PID Aur PPID Concept — Multiple Processes

Ek process apne andar **kai chhote processes perform** karta hai — matlab ek bada process (parent) chalte waqt apne andar kayi chhote-chhote tasks/processes (child) bhi generate kar sakta hai.

**Example:**
Agar ek file ko click kiya jaye to wo file **current active process** ban jati hai, jo ussi waqt run ho rahi hoti hai.

**PID Aur PPID Ka Basic Rule:**
- **PID** har process ki apni **individual/unique** identity hoti hai.
- Ek process ke andar **multiple child processes** ho sakte hain, aur un sab child processes ki apni alag PID hoti hai, lekin sab ka **PPID same** hota hai (jo parent process ki PID hoti hai).

---

## Process Commands (ps aux)

`ps aux` command system ke processes dekhne ke liye use hoti hai.

**Example 1: Kisi Process Ko Naam Se Dhoondna**
```
ps aux | grep brave
```
Ye command sry processes mein se sirf "brave" (Brave browser) se related process ko dhoond kar dikhati hai. `|` (pipe) symbol ek command ka output doosri command ko pass karta hai — is case mein `ps aux` ka output `grep brave` ko diya ja raha hai taake sirf "brave" wali line filter ho kar screen pe aaye.

**Example 2: SSH Process Ko Dhoondna**
```
ps aux | grep ssh
```
Ye command sary processes mein se sirf "ssh" se related process ko dhoond kar dikhati hai.

---

## Foreground vs Background Process

Linux mein processes do 2 se chal sakte hain:

- **Foreground Process:** Wo process jo terminal ko **lock kar deta hai** — matlab jab tak wo process chal raha hai, terminal us waqt tak **free** nahi hota aur user koi doosra command nahi likh sakta. ""For Example Terminal"" 
- **Background Process:** Wo process jo terminal ko lock nahi karta — terminal **free** rehta hai aur user usi waqt doosre commands bhi likh sakta hai jabke process background mein chal raha hota hai.

---

## ps Command — Process Snapshot

`ps` command system ke chal rahe processes ka ek **snapshot (ek waqt ki image)** deta hai — matlab ye ek dafa run hoti hai aur us waqt ke processes dikha deti hai, live update nahi karti.

**Syntax:**
```
ps aux
```

Is command mein:
- `a` → sab users ke processes dikhata hai
- `u` → user-friendly format mein detail dikhata hai
- `x` → un processes ko bhi dikhata hai jo kisi terminal se attached nahi hain

---

## top Command — Live Process View

`top` command bhi processes dikhati hai, lekin `ps` se farq ye hai ke `top` **live (real-time)** update deta hai — matlab processes ki information continuously refresh hoti rehti hai.

**Syntax:**
```
top
```

**Farq — ps vs top:**
- `ps aux` → sirf ek waqt ka snapshot (static)
- `top` → live, continuously update hone wala view

---

## kill Command

`kill` command kisi chal rahe process ko **stop karne** ke liye use hoti hai. Ye process ko **signals** bhej kar band karti hai.

**Method 1: PID (Process ID) Se Kill Karna**

Sab se pehle process ka ID (PID) pata karna hota hai (ps ya top se milta hai), phir:

```
kill 2847
```

Yahan `2847` process ki ID (PID) hai. Ye command us specific PID wale process ko band kar deti hai.

**Method 2: Signal Number Ke Sath Kill Karna**

```
kill -9 786
```

Yahan `-9` ek **signal number** hai jo process ko **forcefully** band karne ke liye use hota hai, aur `786` us process ki PID hai.

---

## Process Ko Naam Se Kill Karna

Kabhi kabhi process ki PID pata karne ke bajaye seedha uska **naam** use kar ke bhi process band ki ja sakti hai.

**Example 1: Frontend Process Kill Karna**
```
kill "process_name"
```
Ye command diye gaye naam wale process ko band kar deti hai (jaise frontend process).

**Example 2: Firefox Kill Karna**
```
pkill "firefox"
```
`pkill` command process ka naam use kar ke usay directly band kar deti hai — is mein PID dhoondne ki zaroorat nahi.

---

## all Kill — Parent Aur Uske Child Processes Ko Band Karna

Kabhi kabhi ek process (parent) ke sath kai chote processes (child) bhi chal rahe hote hain, jinki apni PID aur PPID (Parent Process ID) hoti hai.

```
kill all "browser_name"
```
Ye command us browser ke tamam processes — parent aur uske child processes dono — ko ek sath band kar deti hai.

**Example:**
```
kill all firefox
```
Ye Firefox ke sary open processes jaise multiple tabs/windows jo alag processes mein chal rahe hoty hain inko ek sath band kar deti hai.

---

## CPU Aur Multiple Core Processes

CPU **multiple core** wala hota hai — matlab ek CPU ke andar kai processing units (cores) hoti hain, jo ek sath alag-alag kaam kar sakti hain.

Har process ki apni ek unique **ID (PID)** hoti hai. Agar ek process ke kai child processes hon, to un sab ke apne **PID** hote hain lekin sab ka **PPID (Parent Process ID)** same hota hai — jo ye batata hai ke wo sab ek hi parent process se related hain.

---

## Services

**Services** wo programs hote hain jo **background mein chalte rehte hain** — user ko unka pata nahi chalta lekin wo continuously kaam kar rahe hote hain.

**Real-Life Example (Hotel):**
Jaise ek hotel mein reception, cleaning staff, security — ye sab "services" hain jo hamesha kaam karte rehte hain, chahe guest unhe directly na dekhe. Isi tarah system mein bhi kai services background mein chalti rehti hain taake system smoothly chal sake.

**Examples of Services:**
- **Database** → data ko store aur manage karne wali service
- **ssh** → ye service background mein chal kar remote connections handle karti hai
- **httpd** → web server service jo websites/web requests ko handle karti hai

---

## systemctl Command — Services Ka Manager

`systemctl` ek command hai jo Linux mein services ko **start, stop, enable, disable** aur **manage** karne ke liye use hoti hai. Isay services ka "manager" kaha ja sakta hai, jo batata hai ke koi service **start** hai ya **active** hai ya nahi.

**Service Ka Status Check Karna:**
```
systemctl status ssh
```
Ye command batati hai ke ssh service is waqt chal rahi hai (active) ya band hai.

**Service Ko Enable Karna:**
```
systemctl enable ssh
```
Ye command ssh service ko enable kar deti hai — matlab system start hone par ye service automatically chalna shuru ho jayegi.

**Service Ko Start Karna:**
```
sudo systemctl start ssh
```
Ye command ssh service ko turant start kar deti hai. Chunke ye system-level change hai, is liye `sudo` (root permission) ki zaroorat hoti hai.

**Service Ko Restart Karna:**
```
sudo systemctl restart ssh
```
Ye command ssh service ko band kar ke dobara start kar deti hai — agar service mein koi problem ho ya settings update hui hon to restart karne se wo apply ho jati hain.

**Service Ko Disable Karna:**
```
sudo systemctl disable ssh
```
Ye command ssh service ko disable kar deti hai — matlab ab ye service system start hone par automatically nahi chalegi.

---

## Ports

**Port** ek tarah ka **virtual door (darwaza)** hota hai jis se koi bhi program ya service **network ke through connect** ho sakti hai — matlab jaise ghar mein alag alag darwaze hote hain alag alag kaamon ke liye, waise hi computer mein alag alag ports hote hain alag alag services ke liye.

**Charging Port Example:**
Jaise mobile mein ek charging port hota hai jahan se hum kisi cheez ko connect kar ke use kar sakte hain (jaise charging cable), waise hi computer mein bhi ports hote hain jinse different services connect hoti hain.

**Online Port:**
Jab koi program ya service **internet/network** ke through kaam karti hai, to wo ek specific port use karti hai.

**Examples:**
- **Web/HTTP** → websites aur web requests handle karne ke liye use hone wala port

---

## Summary

**Program vs Process:**
- Program → installed application (abhi chal nahi rahi)
- Process → jab program run hota hai to wo process banta hai
- Ek program ke multiple processes ho sakte hain

**PID aur PPID:**
- PID → har process ki unique identity
- PPID → parent process ki ID jis ne child process ko generate kiya
- Multiple child processes ka PPID same hota hai (unke parent ki PID)

**Process Search:**
- `ps aux | grep <name>` → specific naam process

**Process Types:**
- Foreground → terminal lock ho jata hai
- Background → terminal free rehta hai

**Process Monitoring Commands:**
- `ps aux` → ek waqt ka snapshot dikhata hai
- `top` → live/real-time processes dikhata hai

**Process Kill Commands:**
- `kill <PID>` → PID se process band karta hai
- `kill -9 <PID>` → forcefully process band karta hai
- `kill "name"` ya `pkill "name"` → naam se process band karta hai
- `kill all "name"` → parent aur uske sab child processes ek sath band karta hai

**CPU aur Processes:**
- Multiple core CPU ek sath kai processes handle kar sakta hai
- Har process ka apna PID hota hai, child processes ka PPID same hota hai (parent ke sath)

**Services:**
- Background mein chalne wale programs
- Examples: Database, ssh, httpd

**systemctl Commands:**
- `systemctl status <service>` → status check karta hai
- `systemctl enable <service>` → boot par auto-start enable karta hai
- `sudo systemctl start <service>` → service start karta hai
- `sudo systemctl restart <service>` → service restart karta hai
- `sudo systemctl disable <service>` → auto-start disable karta hai

**Ports:**
- Virtual door jis se services network ke through connect hoti hain
- Online port example: Web/HTTP
