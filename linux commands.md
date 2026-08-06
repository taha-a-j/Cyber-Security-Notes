# Linux Commands Cheat Sheet

## 1. Navigation Commands
```
pwd                  → current directory dikhata hai
ls                    → files/folders list karta hai
tree                  → Directory structure visually dikhata hai
ls -a                 → hidden files sameet sab dikhata hai
ls -l                 → detailed listing (permissions ke sath)
ls -R                 → sub-folders sameet poori list
cd foldername         → us folder mein jana
cd ..                 → ek folder peeche jana
cd                    → home directory mein jana
cd /                  → root directory mein jana
```

## 2. File & Folder Management
```
touch filename        → nayi khaali file banana
mkdir foldername       → naya folder banana
rmdir foldername       → khaali folder delete karna
rm filename            → file delete karna
rm -r foldername       → poora folder delete karna
cp                     → file/folder copy karna
mv                     → file/folder move ya rename karna
clear                  → terminal screen saaf karna
date                   → current date/time dikhana
```

## 3. File Content Dekhna
```
cat filename           → poora content ek saath dikhana
less filename           → file page-by-page dikhana
head filename           → shuru ki 10 lines dikhana
head -n 25 filename     → shuru ki 25 lines dikhana
tail filename            → aakhri 10 lines dikhana
tail -n 25 filename      → aakhri 25 lines dikhana
tail -f filename          → file ko live/real-time monitor karna
file filename             → file ki asal type pata karna
nano filename              → file edit karne ke liye kholna
```

## 4. Output/Redirection
```
echo "text"                 → terminal par text print karna
echo "text" > filename        → file mein likhna (overwrite)
echo "text" >> filename        → file mein add karna (append)
printf "a\nb\nc\n" > filename    → multi-line test file banana
```

## 5. Wildcards ke Sath
```
ls *.pdf              → sab .pdf files dikhana
ls ?.txt               → single-character naam wali files
ls file[1-3].txt        → range wale naam match karna
```

## 6. Search Karna (grep)
```
grep "word" filename          → file mein word dhoondna
grep -i "word" filename        → case-insensitive search
grep -n "word" filename         → line number ke sath search
grep -r "word" .                 → poore folder mein search
grep -v "word" filename           → jin lines mein word NAHI hai wo dikhana
grep -c "word" filename            → matching lines ki ginti
grep "word$" filename               → sirf line ke end mein word ho to match
```

## 7. Files Dhoondna (find)
```
find . -name "*.txt"           → naam se file dhoondna
find . -type f -name "pattern"    → sirf files dhoondna
find . -type d -name "pattern"     → sirf folders dhoondna
find . -size +10M                    → 10MB se bari files
find . -size -10M                     → 10MB se choti files
find . -mtime -1                       → pichle 24 ghante mein modify hui files
find . -mtime -7                        → pichle 7 din mein modify hui files
```

## 8. Permissions (chmod, chown, chgrp)
```
chmod 500 filename            → numeric permission set karna
chmod u+x filename              → owner ko execute permission dena
chmod g-w filename               → group se write permission hatana
chmod a+r filename                → sab ko read permission dena
chmod u=rwx filename               → owner ki permission exactly set karna
sudo chown owner:group filename      → owner aur group change karna
sudo chgrp group filename             → sirf group change karna
sudo chown $USER filename              → current user ko owner banana
```

## 9. Process Management
```
ps aux                    → sab processes ka snapshot
ps aux | grep name          → naam se process dhoondna
top                          → live processes dekhna
kill PID                      → process ID se band karna
kill -9 PID                    → forcefully band karna
pkill "name"                    → naam se process band karna
kill all "name"                  → parent + child sab band karna
```

## 10. Services (systemctl)
```
systemctl status ssh          → service ka status dekhna
systemctl enable ssh            → boot par auto-start karna
sudo systemctl start ssh          → service start karna
sudo systemctl restart ssh          → service restart karna
sudo systemctl disable ssh           → auto-start band karna
```

## 11. Package Management (apt/dpkg)
```
sudo apt update             → package list update check karna
sudo apt upgrade              → naye versions install karna
apt search nmap                 → package dhoondna
apt show nmap                    → package ki detail dekhna
sudo apt install nmap             → package install karna
sudo apt install vlc -y             → bina confirmation ke install
nmap --version / nmap -v              → version check karna
dpkg -l                                 → installed packages ki list
wget https://example.com/pkg.deb          → .deb file download karna
sudo dpkg -i package.deb                    → .deb file se install karna
sudo apt install -f                           → missing dependencies fix karna
which nmap                                     → command ki exact location
whereis nmap                                    → binary+source+manual location
```

## 12. Networking Commands
```
ip address                → device ka IP dikhana
hostname -i                 → IP, router IP, MAC address dikhana
ping 8.8.8.8                  → device active hai ya nahi check karna
traceroute google.com          → packet ka poora raasta trace karna
curl https://google.com          → website ka data fetch karna
curl -i https://google.com          → headers ke sath data fetch karna
ssh username@hostname                → remote device se connect karna
```
