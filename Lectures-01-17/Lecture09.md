# grep Advanced && find Command

## grep Case-Sensitivity

```
grep "linux" notes.txt
```
Ye command tab tak result nahi degi jab tak file mein exactly "linux" (small letters mein) na likha ho.

Isi wajah se hum `-i` flag use karte hain, taake case ka farq na ho:
```
grep -i "Linux" notes.txt
```
Ab ye "Linux", "linux", "LINUX" — sab ko match kar dega. 

## Special Characters (Regex) grep

grep sirf simple words hi search nahi karti, balke kuch special symbols bhi use hote hain jo search ko aur powerful banate hain.

### `$` — Line Ke Aakhir Mein Word Dhoondna

`$` symbol batata hai ke wo word **line ke end** mein hona chahiye, tab hi match hoga. Matlab agar wo word line ke beech mein ho lekin end pe na ho, to match nahi hoga.

**Example:**
```
grep "hardware$" notes.txt
```
Ye sirf un lines ko dikhayegi jin mein line ka **aakhri word** "hardware" ho. Agar "hardware" line ke beech mein kahin aur likha hai (end mein nahi), to wo match nahi hogi.

### `.` — Koi Bhi Ek Character

`.` (dot) ek special character hai jo **kisi bhi ek character** ki jagah use hota hai matlab dot ki jagah koi bhi letter, number ya symbol aa sakta hai, aur wo match ho jayega.

Ye jab kisi pattern mein use hota hai to us jagah "koi bhi ek character ho sakta hai" wala matlab deta hai.

**Test File Banana**

```
printf "cat\ncot\ncut\ncart\n" > file.txt
```

Ye command ek file.txt create karti hai jis mein char words alag-alag lines mein store hote hain: `cat`, `cot`, `cut`, aur `cart`. `\n` newline character hota hai jo har word ko next line par le jata hai.

**Pattern Search Karna**

```
grep "c.t" file.txt
```

**Output:**
```
cat
cot
cut
```

**Explanation:**

Pattern `c.t` mein dot (`.`) exactly ek character represent karta hai "c" aur "t" ke beech koi bhi ek single letter aana chahiye.

- `cat` → match, kyun ke "c" aur "t" ke beech sirf ek letter "a" hai
- `cot` → match, kyun ke beech mein sirf ek letter "o" hai
- `cut` → match, kyun ke beech mein sirf ek letter "u" hai
- `cart` → no match, kyun ke "c" aur "t" ke beech do letters ("a" aur "r") hain, jabke dot sirf ek character allow karta hai

**Key Point:** Dot wildcard hamesha exactly ek character ki jagah leta hai na kam, na zyada. Isi wajah se "cart" is pattern se match nahi hota.

## find Command

`find` command files aur folders ko unke naam, type, size, ya modification time ke basis pe dhoondne ke liye use hoti hai.

**Syntax:**
```
find <kya dhoondna hai> <condition>
```

### Name Basis

`-name` option use hota hai kisi specific naam ki file dhoondne ke liye.

**Example:**
```
find . -name "*.txt"
```
Ye command current folder ke andar sari `.txt` extension wali files dhoond legi. Yahan `*` ka matlab hai "koi bhi naam ho sakta hai", bas extension `.txt` honi chahiye.

### File Type Basis

`-type` option se pata chalta hai ke hum **folder** dhoond rahe hain ya **file**:
- `d` → directory (folder)
- `f` → file

**Syntax:**
```
find . -type <d ya f> -name "pattern"
```

`.` (dot) ka matlab hota hai "same folder", yani current location jahan hum abhi maujood hain.

**Example — Files Dhoondna:**
```
find . -type f -name "*.logs"
```
Ye command current folder ke andar `.logs` extension wali tamam **files** dhoondegi (directories ko chhod kar).

**Example — Folders Dhoondna:**
```
find . -type d -name "*.txt"
```
Ye command current folder ke andar wo tamam **directories (folders)** dhoondegi jin ka naam pattern `*.txt` se match kare.

### Size Basis

`-size` option file ko us ke size ke hisab se dhoondne ke liye use hoti hai.

**Example:**
```
find . -size +10M
```
Ye command un files ko dhoondegi jin ka size **10 MB se zyada** ho. `+` sign ka matlab hai "isse bada".

```
find . -size -10M
```
Ye command un files ko dhoondegi jin ka size **10 MB se kam** ho. `-` sign ka matlab hai "isse chhota".

**Combine With File Type:**
```
find . -type f -size -10M
```
Ye command sirf un **files** (folders nahi) ko dhoondegi jin ka size 10 MB se kam ho.

### Modification Time (mtime) Ke Basis Pe Dhoondna

`-mtime` option files ko unke **modify (last change) hone ke waqt** ke hisab se dhoondne ke liye use hoti hai.

- `-1` → pichle **24 ghanton** ke andar modify hui files
- `-7` → pichle **7 dinon** ke andar modify hui files

**Example — 24 Ghante:**
```
find . -mtime -1
```
Ye command un files ko dikhayegi jo pichle 24 ghanton mein modify hui hain.

**Example — 7 Din:**
```
find . -mtime -7
```
Ye command un files ko dikhayegi jo pichle 7 dinon mein modify hui hain.

**Type && mtime:**
```
find . -mtime -7 -type f
```
Ye command sirf un **files** (folders nahi) ko dhoondegi jo pichle 7 dinon mein modify hui hain.

## Summary

**grep special characters:**
- `$` → sirf line ke end mein word ho to match karega
- `.` → koi bhi ek character represent karta hai

**grep dot (`.`) wildcard:**
- `printf "cat\ncot\ncut\ncart\n" > file.txt` → test file banata hai
- `grep "c.t" file.txt` → "c" aur "t" ke beech ek character wale words match karta hai
- `cart` show nahi karega kyun ke "c" aur "t" ke beech 2 characters hain

**find command options:**
- `-name` → naam ke hisab se file/folder dhoondta hai
- `-type f` → sirf files dhoondta hai
- `-type d` → sirf folders (directories) dhoondta hai
- `-size +10M` → 10 MB se bada size wali files
- `-size -10M` → 10 MB se chhota size wali files
- `-mtime -1` → pichle 24 ghanton mein modify hui files
- `-mtime -7` → pichle 7 dinon mein modify hui files
- `.` (dot) → current folder ko represent karta hai
- `*` → wildcard, koi bhi naam match kar sakta hai
