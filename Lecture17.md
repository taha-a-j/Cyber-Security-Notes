# Disk Space, System Information & Logs

## Checking disk space

Jab bhi hum koi file **save** karte hain, to wo file **store** ho kar hamare storage device — jaise **HDD (Hard Disk Drive)**, **SSD (Solid State Drive)**, waghera — mein rakhi jati hai.

### df Command 

`df` command us **disk space** ko check karne ke liye use hoti hai — matlab ye batati hai ke disk mein kitni jagah use ho chuki hai aur kitni baaki hai.

**Basic Command:**
```
df
```

**Human-Readable Format:**
```
df -h
```

`-h` flag ka matlab hai **human readable** — ye disk space ko aasan units (jaise KB, MB, GB) mein show karta hai, taake numbers samajhna aasan ho, warna raw numbers samajhna mushkil hota hai.

---

## Checking Folder Size

### du Command

`du` command kisi specific **folder ka size** check karne ke liye use hoti hai.

**Syntax:**
```
du -sh <folder_name>
```

Is command mein:
- `-s` → **size** (sirf total size dikhata hai, andar ki har file ka alag size nahi)
- `-h` → **human readable** (size ko aasan units mein show karta hai)

---

## Checking RAM (Memory)

### free Command

`free` command system ki **free RAM (memory)** check karne ke liye use hoti hai — ye batati hai ke kitni memory use ho rahi hai aur kitni available hai.

**Human-Readable Format Mein:**
```
free -h
```

`-h` flag yahan bhi memory ko aasan units mein (jaise MB, GB) show karta hai.

---

## System Information Commands

### uptime Command

`uptime` command batati hai ke **laptop/system kitne der se ON** hai — matlab last restart ke baad se kitna waqt guzar chuka hai.

```
uptime
```

### uname -a Command

`uname -a` command system ki detailed information dikhati hai, jis mein shamil hai:
- **OS info** → operating system ki information
- **User info** → current user ki information
- **Kernel version** → system ke kernel ka version
- **OS version** → operating system ka version

```
uname -a
```

### lscpu Command

`lscpu` command CPU ki **architecture** check karne ke liye use hoti hai.

```
lscpu
```

**Important Concept:** CPU ek "box" ki tarah hota hai jis ke andar sary **processes chalte** hain — matlab CPU wo jagah hai jahan system ke sare running processes execute hote hain.

### lsblk Command

`lsblk` command system se **connected disks aur unke partitions** ki list dikhati hai.

```
lsblk
```

**Important Note:** Information ya to **RAM** mein hoti hai ya **SSD** par store hoti hai — matlab lsblk hardware level ke storage devices aur unki partitions ko dikhata hai.

---

## Logs

**Logs** wo records hote hain jo system mein hone wali activities ko **save** karte hain.

**Login Logs Ka Example:**
Agar koi system mein **login** karta hai, to us login ki details **logs** ke roop mein **hamesha ke liye save** ho jati hain. Jis bhi type ke folder se related logs generate hoti hain, wo usi type ke folder mein store hoti hain.

**Logs Ka Location:**
```
/var/log
```

Ye directory (folder) system ki sari logs ko store karti hai.

---

## journalctl Command — Logs Dekhna

`journalctl` command system ki **logs ko dekhne** ke liye use hoti hai — ye systemd services aur system events ki detailed logs show karti hai.

**Basic Command — Saari Logs Dekhna:**
```
journalctl
```

**Live Logs Dekhna:**
```
journalctl -f
```

`-f` flag (follow) lagane se logs **live (real-time)** update hoti rehti hain — matlab jaise jaise nayi activity hoti hai, log turant screen par show hoti jati hai.

**Specific Service Ki Logs Dekhna:**
```
journalctl -u ssh
```

`-u` flag ke sath service ka naam likh kar sirf us specific service (jaise `ssh`) ki logs dekhi ja sakti hain.

---

## Log Analysis (SOC — Security Operations Center)

Logs ko analyze karna bohat important kaam hai, khaas tor pe security ke lehaz se. Isay **SOC (Security Operations Center) log analysis** kaha jata hai.

**Log Analysis Mein Dekha Jata Hain:**
- **Kab hua?** — event ka time/date
- **Kisne kiya?** — konsa user ya process involved tha
- **Kahan se?** — event kahan se initiate hua (jaise konsi IP se)

**Log Line Parhna:**
Har log line ko dhyan se **parhna (analyze karna)** zaroori hota hai taake pata chal sake ke system mein kya ho raha hai — kisi bhi suspicious activity ko time par pehchana ja sake.

---

## Summary 

**Disk Space Commands:**
- `df` → disk space check karta hai
- `df -h` → human-readable format mein disk space
- `du -sh <folder>` → folder ka size check karta hai

**Memory Command:**
- `free -h` → free RAM check karta hai (human-readable)

**System Info Commands:**
- `uptime` → system kitni der se ON hai
- `uname -a` → OS info, user info, kernel version, OS version
- `lscpu` → CPU architecture check karta hai
- `lsblk` → connected disks aur unke partitions dikhata hai

**Logs:**
- Logs system ki activities (jaise login) ko hamesha ke liye save karte hain
- Logs ka location: `/var/log`

**journalctl Commands:**
- `journalctl` → saari logs dekhna
- `journalctl -f` → live logs dekhna
- `journalctl -u ssh` → specific service ki logs dekhna

**Log Analysis (SOC):**
- Kab hua, kisne kiya, kahan se hua — ye teeno cheezein check ki jati hain
- Log line ko dhyan se parhna security ke liye zaroori hai
