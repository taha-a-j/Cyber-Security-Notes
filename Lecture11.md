# chmod Symbolic Mode, chown aur chgrp

## chmod: Change Mode
## chown: Change Owner
## chgrp: Chnage Group

`chmod` command file ya folder ki permissions **change** ki jti h **symbolic mode** way mein. 

## chmod Symbolic Notation

Symbolic mode mein kuch specific letters use hote hain jo batate hain ke permission **kis ke liye** hai:

- `u` = **owner** (user) — file/folder ka banane wala
- `g` = **group** — jis group se ye file/folder belong karti hai
- `o` = **other** — baaki sb users
- `a` = **all** — owner, group, aur others teeno ke liye ek sath

Aur ye symbols batate hain ke permission **add** honi hai, **remove** honi hai, ya **exactly set** honi hai:

- `+` = **add permission** — koi permission add karni ho to ye use hota hai
- `-` = **remove permission** — koi permission hatani ho to ye use hota hai
- `=` = **set permission** — exactly wahi permission set karta hai jo likhi gayi hai, baaki sab hata deta hai

## File Permissions Change Karna

### Permission Add Karna (Execute)

**Task:** run.sh file ko "read, write, execute" permission dena

```
chmod u+x run.sh
```

Ye command owner (`u`) ke liye **execute (`x`)** permission **add** kar deti hai.

```
ls -l
```
Ye command permissions ko verify karne ke liye use hoti hai — current permissions dikhata hai.

### Group Se Write Permission Remove Karna

**Task:** Group se write permission hatani hai

```
chmod go-w run.sh
```

Ye command group (`go`) se **write (`w`)** permission **remove** kar deti hai.

### Sab Se Read Permission Remove Karna

**Task:** Koi bhi user file ko read na kar sake

```
chmod a-r run.sh
```

Ye command **all (`a`)** — matlab owner, group, aur others — teeno se **read (`r`)** permission remove kar deti hai. Is ke baad koi bhi user file ko read nahi kar sakega.

```
ls -a
```
Ye command hidden files included sari files ko list karta hai.

### Sab Ko Read Permission Dena

**Task:** Har user (owner, group, others) ko file read karne ki ijazat dena

```
chmod a+r run.sh
```

Ye command **all (`a`)** ke liye **read (`r`)** permission **add** kar deti hai.

```
ls -l
```

### Group Ko Write Permission Dena

**Task:** Group ko write permission dena

```
chmod g+w run.sh
```

Ye command group (`g`) ke liye **write (`w`)** permission **add** kar deti hai.

```
ls -l
```

---

## Folder Permissions Change Karna

Folder par bhi **read, write, execute** teeno permissions hoti hain, bilkul files ki tarah lekin folder ke case mein `execute` permission ka matlab hota hai ke koi user us folder ke andar ja (navigate kar) sakta hai ya nahi.

### Owner Se Execute Permission Remove Karna

**Task:** Owner se folder ke liye execute permission hatani hai

```
chmod u-x vault
```

Ye command owner (`u`) se **execute (`x`)** permission remove kar deti hai  is ke baad owner us folder ke andar navigate nahi kar sakta.

```
ls -l
```

### Owner Ko Execute Permission Wapas Dena

```
chmod u+x vault
```

Ye command owner (`u`) ke liye **execute (`x`)** permission **add** kar deti hai.

```
ls -l
```

### Owner Se Write Permission Remove Karna

```
chmod u-w vault
```

Ye command owner (`u`) se **write (`w`)** permission remove kar deti hai — owner ab folder mein koi changes (jaise nayi file banana) nahi kar sakta.

```
ls -l
```

### Owner Ko Exactly Full Permission Set Karna

**Task:** Owner ko poori (read, write, execute) permission set karni hai

```
chmod u=rwx vault
```

Yahan `=` sign use ho raha hai, jo owner ki permission ko **exactly** `rwx` set kar deta hai — chahe pehle jo bhi permission thi, ab wo overwrite ho kar `rwx` ho jayegi.

```
ls -l
```

### Owner Se Read Permission Remove Karna

```
chmod u-r vault
```

Ye command owner (`u`) se **read (`r`)** permission remove kar deti hai.

```
cd vault
```
Ye command folder ke andar jaane ke liye use hoti hai — agar execute permission na ho to ye command fail ho jayegi.

```
ls -l
```
Result mein permissions kuch is tarah show hongi jahan owner ke liye read permission missing hogi.

----

## chown Command — Owner Change Karna

`chown` command kisi file ya folder ka **owner change** karne ke liye use hoti hai.

**Syntax:**
```
sudo chown <naya_owner>:<group> <filename>
```

**Example:**
```
sudo chown root:David notes.txt
```

Ye command notes.txt file ka owner **root** set kar deti hai aur us ka group **David** set kar deti hai.

**Important Note:** Chunke `chown` system-level (sensitive) change hai, is liye ye command execute karte waqt system **password** mangta hai (root/admin permission verify karne ke liye).

---

## chgrp Command — Group Change Karna

`chgrp` command sirf kisi file ya folder ka **group** change karne ke liye use hoti hai (owner change nahi hota, sirf group).

**Syntax:**
```
sudo chgrp <naya_group> <filename>
```

**Example:**
```
sudo chgrp root notes.txt
```

Ye command notes.txt file ka group **root** set kar deti hai.

```
ls -l notes.txt
```
Ye command file ki current owner aur group information verify karne ke liye use hoti hai.

**Example — User Ko Group Set Karna:**
```
sudo chown $USER notes.txt
```

Ye command current logged-in user (jo `$USER` variable mein store hota hai) ko notes.txt ka owner set kar deti hai — `$USER` ek environment variable hai jo automatically current user ka naam le leta hai.

---

## Summary

**chmod Symbolic Mode Letters:**
- `u` → owner
- `g` → group
- `o` → other
- `a` → all (owner + group + others)

**chmod Symbolic Mode Operators:**
- `+` → permission add karta hai
- `-` → permission remove karta hai
- `=` → permission ko exactly set karta hai (overwrite)

**File Permission:**
- `chmod u+x file` → owner ko execute permission
- `chmod g-w file` → group se write permission hatana
- `chmod a-r file` → sab se read permission hatana
- `chmod a+r file` → sab ko read permission dena
- `chmod g+w file` → group ko write permission dena

**Folder Permission:**
- `chmod u-x folder` → owner se execute (navigate) permission hatana
- `chmod u+x folder` → owner ko execute permission dena
- `chmod u-w folder` → owner se write permission hatana
- `chmod u=rwx folder` → owner ki permission exactly rwx set karna
- `chmod u-r folder` → owner se read permission hatana

**Ownership Commands:**
- `chown` → file/folder ka **owner aur group** dono change karta hai (root/password chahiye)
- `chgrp` → sirf file/folder ka **group** change karta hai
- `$USER` → current logged-in user ka naam represent karta hai
