# SSH (Secure Shell)

SSH ek secret ya secure tool/service hota hai jo kisi remote location par bethay hue apne system ko access karne ke liye use hota hai. Iska matlab hai ke aap kahin bhi baithay hoein, aap kisi doosray computer ya server ko us tarhan control kar saktay hain jaisay aap us ke samne physically baithay hoein.

SSH ki sab se important cheez ye hai ke iski poori communication **encrypted** way mein hoti hai, yani data ko itna scramble/mix kar diya jata hai ke agar koi beech mein data chura bhi le, to wo usay samajh nahi sakta. Isi wajah se SSH ko secure remote access ka tareeqa mana jata hai.

## SSH Kyun Use Hota Hai
- Kisi doosri location par mojood system ko remotely access aur manage karne ke liye.
- Do systems ke darmiyan files ko securely transfer karne ke liye.
- Remote server par bina physically wahan jaye commands run karne ke liye.
- Connection ko hackers se save rakhne ke liye, kyun ke data encrypted hota hai.

## Example
**Home aur Office ka Scenario:**
agar apne office ke laptop mein rakhi hui koi file chahiye. Ab office jane ki bajaye, aap SSH use kar ke ghar baithay baithay apne office laptop mein securely login kar saktay hain aur wo file access kar saktay hain.

---

# Port

Port ek **virtual door** ki tarhan hota hai kisi computer ya server par. Jaisay kisi building mein alag alag maqasid ke liye alag darwazay hotay hain (entry, exit, service door, waghera), waisay hi ek computer system mein bhi kayi virtual door hotay hain jinhein "ports" kaha jata hai, aur har door kisi khaas service ya communication ke liye use hota hai.

## Ports Important Points
- Har service jo computer par chal rahi hoti hai (jaisay website, email, file transfer, waghera) apna alag port use karti hai internet par communicate karne ke liye.
- Internet par bohat saray ports available hotay hain, aur har ek kisi alag service ke liye assign hota hai.
- Port us data ko system mein aane aur bahar jane deta hai jo kisi specific application/service se related ho.

## Common Ports
- **HTTP** (jo normal websites ke liye use hota hai) ka apna ek dedicated port hota hai.
- **HTTPS** (jo secure websites ke liye use hota hai, ye HTTP ka encrypted version hai) ka bhi apna alag dedicated port hota hai.
- Isi tarhan doosri services jaisay SSH, FTP, Email, waghera — in sab ke apnay apnay unique port numbers assigned hotay hain.

## Summary
computer ko ek badi building samajh lein, aur us mein chal rahi har service (jaisay website, email, ya remote login) ka apna alag door (port) hota hai jis se wo apna data bhejti aur receive karti hai. Isi tarhan sab services ka traffic organized rehta hai aur mix nahi hota.
