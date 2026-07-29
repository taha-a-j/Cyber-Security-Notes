# Linux Users aur Permissions

## Linux Ke 2 Types Ke Users

Linux mein do tarah ke users hote hain:

### 1. Basic User
Basic user ko **child** ki tarah samjho jaise ek bacha apne parents pe depend karta hai aur uski activities limited hoti hain. Basic user ke paas bhi **limited access** hota hai system mein.

### 2. Root User
Root user ko **parent** ki tarah samjho jaise parents ke paas ghar mein har cheez ka full control hota hai. Root user ke paas **unlimited access** hota hai poore system mein.

**Kaam Karne Ka Tarika:**
Basic user ko agar koi kaam karna ho jo uski limit se bahar ho, to wo Root user se **request** karta hai. Basic user sirf apne diye gaye limited permissions ke andar hi kaam kar sakta hai — jaise **read, write, create, delete** — jo Root level ki access maangte hain wo sirf root user hi de sakta hai ya khud kar sakta hai.

## sudo Command

Basic user agar apna normal kaam karte karte kisi aisi cheez tak pohanchna chahta hai jo **root level ki permission** maangti hai, to wo `sudo` command use karta hai.

`sudo` command basic user ko temporarily root level ki permission provide karta hai taake wo wo kaam kar sake jo normally sirf root user hi kar sakta hai.

## Owner, Group Aur Multiple Users Concept

Ek system mein **multiple users** aur **multiple groups** hote hain matlab ek hi machine pe alag-alag log kaam kar rahe hote hain aur wo alag-alag groups mein organize hote hain.

**Example:**
- Developer team: 2 members
- Graphic team: 2 members

Har team ek alag group hai, aur har group ke apne specific permissions hote hain.

### Owner Kya Karta Hai

**Owner** wo hota hai jo decide karta hai ke kis ko kya permission milegi.

Owner ke paas ye power hoti hai ke wo:
- **Permission allow** kar sakta hai
- Decide kar sakta hai ke koi user/group kaunsi **activities perform** kar sakta hai aur kaunsi nahi kar sakta

**Important Rule:** Jis user ya group ko jo permission di jayegi, wo sirf wahi kaam kar sakega jis ki usay permission di gayi hai.

## File Aur Folder Default Permissions

Linux mein files aur folders ki apni **default permissions** hoti hain jab wo naye banaye jate hain:

- **Files ke liye default permission:** `rw` (read aur write) matlab file naye create hone par by default sirf read aur write ki ijazat hoti hai.
- **Folders ke liye default permission:** `rwx` (read, write, execute) folder ke liye teesri permission "execute" bhi hoti hai, jis se folder ke andar jaana (navigate karna) possible hota hai.

**IMPORTANT:** File aur folder par alag-alag rules hote hain — dono ki default permissions same nahi hoti.

### Example (David Machine)

Linux mai David name machine mein:
- 1 folder hai
- 3 files hain
- 3 groups hain

Teeno groups ki alag permissions set ki gayi hain:
- **Group 1** ke paas sirf **read (r)** permission hai
- **Group 2** ke paas **read-write (r-w)** permission hai
- **Group 3** ke paas folder ko **read-write-execute (r-w-x)** karne ki permission di gayi hai

## Permission Structure (ls -l Command)

`ls -l` command file ya folder ki detailed listing dikhata hai, jis mein permissions bhi show hoti hain.

Linux mein permissions **3 parts** mein divide hoti hain:

```
-rw-rw-r--
```

Is structure ko teen parts mein parh sakte hain:

1. **Owner Permission** — file/folder banane wale (creator) ki permission
2. **Group Permission** — us group ki permission jis se ye file/folder belong karti hai
3. **Others Permission** — baaki tamam users ki permission jo owner ya group ka hissa nahi hain

**Example Breakdown:**
- Owner: `rw-` → read aur write permission
- Group: `rw-` → read aur write permission
- Others: `r--` → sirf read permission

Har permission block mein 3 letters hote hain:
- `r` = read
- `w` = write
- `x` = execute

Agar koi permission nahi di gayi ho to us jagah `-` (dash) show hota hai.

## Numeric (Octal) Permission Values

Permissions ko numbers ke through bhi represent kiya ja sakta hai, jo `chmod` command mein use hote hain:

- `r` (read) = **4**
- `w` (write) = **2**
- `x` (execute) = **1**

In numbers ko add kar ke ek digit banta hai jo ek group (owner/group/other) ki poori permission represent karta hai.

**Examples:**
- `4 + 2 + 1 = 7` → `rwx` (full permission — read, write, execute)
- `4 + 1 = 5` → `r-x` (read aur execute, write nahi)
- `4 + 2 = 6` → `rw-` (read aur write, execute nahi)
- `4` → `r--` (sirf read)
- `0` → `---` (koi permission nahi)

Chmod command mein 3 digits use hote hain — pehla digit **owner** ke liye, dusra **group** ke liye, aur teesra **others** ke liye hota hai.

## chmod Command Use

`chmod` command file ya folder ki permissions **change** karne ke liye use hota hai.

**Step 1: File Ka Content Dekhna**
```
cat secret.txt
```
Ye command secret.txt file ka content screen pe show karta hai.

**Step 2: Current Permissions Check Karna**
```
ls -l
```
Ye command current permissions list karta hai taake pata chale file ki abhi kya permissions hain.

**Step 3: Owner Ko Read-Execute Permission Dena**
```
chmod 500 secret.txt
```

Is command ka result:
```
-r-x------
```

**Explanation:** `500` ka matlab hai:
- Owner: `5` = `4+1` = **r-x** (read aur execute, write nahi)
- Group: `0` = **---** (koi permission nahi)
- Others: `0` = **---** (koi permission nahi)

Yahan sirf **owner ki permission** set hui hai, group aur others ke paas koi access nahi.

**Step 4: Group Ko Full Permission Dena**
```
chmod 070 secret.txt
```

Is command ka result:
```
----rwx---
```

**Explanation:** `070` ka matlab hai:
- Owner: `0` = **---** (koi permission nahi)
- Group: `7` = `4+2+1` = **rwx** (read, write, execute — full permission)
- Others: `0` = **---** (koi permission nahi)

Yahan sirf **group ki permission** set hui hai — owner aur others ke paas koi access nahi raha.

## Summary

**Users:**
- Basic user → limited access (child jaisa)
- Root user → unlimited access (parent jaisa)
- `sudo` → basic user ko temporarily root-level permission deta hai

**Owner aur Group:**
- Owner decide karta hai ke kis ko kya permission milegi
- Ek system mein multiple users aur multiple groups ho sakte hain

**Default Permissions:**
- File → `rw` (read, write)
- Folder → `rwx` (read, write, execute)

**Permission Structure (ls -l):**
- 3 parts: Owner, Group, Others
- Har part mein: `r` (read), `w` (write), `x` (execute)

**Numeric Values (chmod):**
- `r` = 4, `w` = 2, `x` = 1
- Values ko add kar ke ek digit banta hai (jaise 7 = rwx, 5 = r-x, 0 = ---)

**chmod Command:**
- 3 digits hote hain: owner, group, others (is order mein)
- `chmod 500 file` → owner ko r-x, group aur others ko koi permission nahi
- `chmod 070 file` → group ko rwx, owner aur others ko koi permission nahi
