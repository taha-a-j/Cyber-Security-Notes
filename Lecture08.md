# Grep aur CLI Basics

## GUI vs CLI

GUI (Graphical User Interface) matlab jo hum click kar ke use karte hain, screen pe dekh kar. CLI (Command Line Interface) matlab commands likh kar system ko instructions dena.

CLI easy hai data search karne ke liye. Simple data command se easily mil jati hai agar material zyada ho to CLI aur bhi zyada useful ho jati hai kyun ke bohat sara data GUI se manually dhoondna mushkil aur slow hota hai, lekin CLI mein commands se jldi mil jata hai.

## Library Wali Example (Real Life Se Samjho)

Socho ke ek library hai:

- Agar tumhe book ke andar se koi specific material nikalna ho, to us ke liye "find" command use hoti hai.
- Isi tarah PDF files ya student ka data dhoondna ho to manually har file kholne ke bajaye seedha command se search kar sakte ho.



## grep Command Kya Hai

`grep` command hai jo kisi file ke andar se specific word ya pattern dhoondne ke liye use hoti hai.

**Syntax:**

```
grep "search_word" <filename>
```

**Examples:**

Ye command notes.txt file ke andar "Linux" word dhoondegi aur sirf wahi lines dikhayegi jahan ye word mila.

```
grep "Linux" notes.txt

```

`-i` flag lagane se search case-insensitive ho jati hai, matlab "Linux", "linux", "LINUX" sab match ho jayenge, chahe capital letters hon ya small.

```
grep "Linux" -i notes.txt
```

`-n` ke sath `-i` lagane se line number bhi show hota hai matlab case-insensitive search ke sath ye bhi pata chalta hai ke word kis line number pe mila.

```
grep -i -n "Linux" notes.txt
```



## grep Ke Options (Flags) Ki Poori Detail



### 1. `-i` (Ignore Case)

Search ko case-insensitive banata hai — chahe word capital mein likha ho ya small, dono match ho jayenge.

### 2. `-n` (Line Number Dikhana)

Har matching line ke sath us ki line number bhi show karta hai, taake pata chal sake ke word exactly file mein kahan mila.

### 3. `-r` (Recursive Search)

Ye ek folder ke andar mojood **saari files** (aur subfolders) mein search karta hai, sirf ek file ki bajaye.

### 4. `.` (Current Folder mai)

**Example:**

```
grep -i -n -r "Password" .
```

Ye command "Password" word ko case-insensitive tareeke se, line number ke sath, aur poore folder mein (subfolders) dhoondegi. Yahan `.` ka matlab hai "is current folder mein".

**Practical Example (Student Result):**

```
grep -i -n -r "Ali"
```

Ye command "Ali" naam ko poore folder ki files mein dhoondegi jaise agar bohat sari result files hon aur ek specific student ka result nikalna ho to ye useful hai.

### 4. `-v` (Invert Match / Word Ko Exclude Karna)

Ye un lines ko dikhata hai jin mein wo word **nahi** hota. Matlab jo word specify kiya hai, us wali lines ko (remove) kar ke baaki saari lines show karta hai.

**Example:**
Ye notes.txt ki wo saari lines dikhayega jin mein "Linux" word nahi hai.

```
grep -v "Linux" notes.txt
```

Same kaam karta hai, lekin case-insensitive tareeke se matlab "Linux", "linux", "LINUX" har form wali lines exclude ho jayengi.

```
grep -v -i "Linux" notes.txt
```



### 5. `-c` (Count — Matches Ginna)

Ye matching lines ko dikhane ke bajaye sirf un ki **total count (number)** batata hai.

**Example:**
Ye batayega ke notes.txt mein "Linux" word kitni lines mein hai (total count).

```
grep -c "Linux" notes.txt
```

Same kaam, lekin case-insensitive "Linux" ke har case variation ko count karega.

```
grep -c -i "Linux" notes.txt
```
### Extra: 

**grep -in "linux" .      # case ignore + line number dono**

**grep -rv "Linux" .      # (r:folder aur subfolders ) jin lines mein Linux NAHI hai, sirf wo dikhao**

**grep -rc "Linux" .      #  kitni lines mein Linux mila, 1,2,3... ginti**

## Summary

- `-i` → Case ignore karta hai (capital/small farq nahi karta)
- `-n` → Matching line ka number dikhata hai
- `-r` → Poore folder aur subfolders mein recursively search karta hai
- `-v` → Ulta match karta hai (jo word specify kiya us ke bina wali lines dikhata hai)
- `-c` → Matching lines ki total ginti (count) dikhata hai
