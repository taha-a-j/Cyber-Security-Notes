# Tar && Zip

## Tar Aur Zip Kya Hain

Tar aur Zip dono commands folder par apply hoti hain — matlab in ka basic kaam multiple files ya folders ko collect karna hai.

## Tar

Tar ko ek bag ki tarah samjho — jaise ek bag mein hum kai cheezein ikattha kar ke rakh dete hain, waise hi Tar sab kuch (multiple files ya folders) ko ek jagah collect kar deta hai.

**Real-Life Example:**
Agar hum apne doston ko books ek ek kar ke bhejein, to ye kaam complex ho jata hai. Is ke bajaye, agar hum saari books ek bag mein daal dein, to ek hi baar mein multiple items send ki ja sakti hain. Bilkul isi tarah, Tar bhi multiple files ko ek "bag" (tar file) mein daal deta hai taake unhe ek sath handle karna aasan ho jaye — is bag ko `.tar` file kaha jata hai.

## Tar Ke Flags

Tar command mein alag alag kaam karne ke liye kuch specific flags use hote hain:

- **-c (Create):** Nayi tar file banane ke liye use hota hai
- **-t (Table/List):** Tar file ke andar maujood files ki list dekhne ke liye use hota hai
- **-x (Extract):** Tar file ke andar se files ko wapas nikalne (extract karne) ke liye use hota hai
- **-v (Verbose):** Process ke doran detailed information (kya ho raha hai) screen par dikhata hai
- **-f (File):** File ka naam specify karne ke liye use hota hai
- **-z (Gzip Compress):** Tar file ko compress karne ke liye use hota hai, jis se uska size chhota ho jata hai

## Tar Commands — Practical Examples

### Tar File Banana (Create)

Step 1: Sab se pehle current directory ki files list karo:

```
ls
```

Step 2: Ek naya tar file banao:

```
tar -cf project.tar project
```

Yahan `-c` ka matlab hai create, aur `-f` ka matlab hai file. Ye command project naam ke folder ko project.tar naam ki ek nayi tar file mein collect kar deti hai.

Step 3: Verify:

```
ls
```

### Tar File Ke Andar Ki List Dekhna

```
tar -tf project.tar
```

Ye command project.tar file ke andar maujood tamam files/folders ki list dikhati hai, bina unhe extract kiye.

### Tar File Se Extract Karna

```
tar -xf project.tar
```

Ye command project.tar file ke andar se saari files/folders ko wapas nikal (extract) deti hai, taake original format mein dobara access ki ja sakein.

### Verbose Ke Sath Create Aur Extract Karna

**Create With Verbose:**

```
tar -cvf project.tar
```

**Extract With Verbose:**

```
tar -xvf project.tar
```

Yahan `-v` (verbose) lagane se terminal screen par ye bhi show hoga ke konsi files create ya extract ho rahi hain, step by step.

### Important Rule — Flag Ka Order

`-f` flag hamesha last mein aata hai jab bhi combine kar ke likha jaye.

**Sahi Tareeke:**
- -xvf
- -cf
- -xf 

**Ghalat Tareeke:**
- -fx ❌
- -fc ❌

Ye tareeke galat hain — `-f` ko kabhi bhi doosre flags se pehle nahi likhna chahiye.

## Zip

Zip bhi Tar ki tarah multiple items ko collect karta hai, lekin iska benefit ye hai ke ye size ko compress, kam bhi kar deta hai.

**Zip working:**
Agar multiple items ka size 1GB ho, to Zip us size ko compress kar ke chhota kar deta hai — extra space (jagah) remove ho jati hai. Isay is tarah samjho: agar size 1GB hai to zip usay compress kar ke shayad kam kar de (jaise 20% tak).

## Tar vs Zip — difference

- **Tar:** Sirf files ko copy/collect kar deta hai, size compress nahi karta.
- **Zip:** Files ko collect karne ke sath sath unka size bhi kam (compress) kar deta hai.

**Use:**
- Zip zyada tar Windows mein use hota hai.
- Tar zyada tar Linux mein use hota hai.

## Zip Commands — Practical Examples

### Zip File Banana

```
ls
zip -r project.zip project
```

Yahan `-r` (recursive) ka matlab hai ke project folder ke andar ki saari files/subfolders bhi zip mein shamil ho jayein. Ye command project folder ko project.zip naam ki compressed file mein badal deti hai.

### Unzip — File Extract Karna

```
unzip -l project.zip project
```

`-l` (list) flag zip file ke andar ki files list karta hai bina extract kiye.

**Zip & Unzip Working:**
- Zip → files ko collect kar ke unka size kam karta hai
- Unzip → zip file ke andar se files ko wapas extract karta hai

## Combined Command — Tar Aur Zip Ka Ek Sath Use

Kabhi kabhi Tar aur Zip dono ko ek sath bhi use kiya ja sakta hai — matlab pehle files ko tar mein collect karo, phir usay zip (compress) bhi kar do.

**Create With Compression:**

```
tar -czf project.tar.gz project
```

Yahan:
- -c → create
- -z → gzip compression (size kam karna)
- -f → file specify karna

Ye command project folder ko project.tar.gz naam ki ek aisi file mein badal deti hai jo collect bhi ho aur compressed bhi ho.

**Extract With Verbose Aur Compression:**

```
tar -xzvf project.tar.gz
```

Ye command .tar.gz file ko extract karti hai, sath hi verbose mode mein detail bhi dikhati hai.

## Linux & Window

**Tar Ke Flags (Linux):**
- -c → create
- -x → extract
- -v → verbose (detail dikhana)
- -f → file specify karna
- Combine: -cf, -cvf (create ke liye), -xf, -xvf (extract ke liye)

**Zip Ke Flags (Windows):**
- -r → recursive (folder ke andar ki sab files shamil karna)
- -l → list (files ki list dikhana bina extract kiye)
- Combine: -cvzf → create, verbose, zip-compress, file (tar aur zip dono ke combination ke liye)

## Backup Banana — Practical Example

Step 1: Ek naya folder banao jahan backup rakhna hai:

```
mkdir backup
```

Step 2: Compressed tar file ko us backup folder mein extract karo:

```
tar -xvzf project.tar.gz -C backup
```

Yahan `-C` (capital C) us destination folder ko specify karta hai jahan files extract honi hain — is case mein backup folder.

Step 3: Verify karne ke liye list karo:

```
ls
```

## Summary

**Tar & Zip Concept:**
- Tar aur Zip dono multiple files/folders ko collect karte hain
- Tar → sirf collect karta hai (jaise bag mein cheezein daalna)
- Zip → collect karne ke sath size bhi compress karta hai

**Tar Flags:**
- -c → create
- -t → table/list
- -x → extract
- -v → verbose
- -f → file (hamesha last mein aata hai)
- -z → gzip compress

**Tar Commands:**
- `tar -cf project.tar project` → tar file banana
- `tar -tf project.tar` → list dekhna
- `tar -xf project.tar` → extract karna
- `tar -cvf` / `tar -xvf` → verbose ke sath create/extract

**Tar vs Zip:**
- Tar → Linux mein zyada use hota hai, sirf collect karta hai
- Zip → Windows mein zyada use hota hai, size bhi compress karta hai

**Zip Commands:**
- `zip -r project.zip project` → zip file banana
- `unzip -l project.zip project` → list dekhna

**Combined Tar+Zip Commands:**
- `tar -czf project.tar.gz project` → create + compress
- `tar -xzvf project.tar.gz` → extract + verbose + compress format

**Backup Ka Practical Use:**
- `mkdir backup` → naya folder banana
- `tar -xvzf project.tar.gz -C backup` → specific folder mein extract karna
- `-C` → destination folder specify karta hai
