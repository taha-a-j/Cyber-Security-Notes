# Cyber Security

## 1. Cyber Security Fundamentals

Cyber Security ka matlab hai apne systems, servers aur data ko unauthorized access, damage ya attack se bachana.

**Risk:**

Risk ka matlab hai kisi loss ya damage hone ki possibility. Har system ka apna level of risk hota hai jo fix nahi kiya ja sakta, sirf kam kiya ja sakta hai. Jaise agar aap ek website bana rahe hain, to us website ke hack hone ka hamesha ek risk maujood rahega. Vulnerability ko fix karna hi actual risk management hai matlab jitni zyada vulnerabilities fix hongi, utna risk kam hoga.

**Vulnerability:**
Vulnerability ka matlab hai "weakness of server ya website". Ye wo kamzoriyan hain jo system mein maujood hoti hain aur jinka fayda utha kar attacker system ko nuksan pohcha sakta hai.

**Threat:** 

Threat "khatra". Ye koi bhi cheez ya person ho sakta hai jo vulnerability ka fayda utha kar system ko harm pohchane ki try kare. (Note: Threat ki detailed types jaise malware, phishing, insider threat

Summary: **Threat** kisi **Vulnerability** ka fayda utha kar **Risk** ko reality mein badal deta hai.

---



## 2. Client Server Model

Client Server Model ye batata hai ke internet par communication kaise hoti hai do main parties hoti hain: **Client** aur **Server**.

- **Client:** Wo device/user jo request bhejta hai (jaise aapka mobile ya laptop browser).
- **Server:** Wo system jo request ko receive karta hai aur response deta hai (jaise website hosting server).

**Example:** Agar client Pakistan mein hai aur server US mein hai, to bhi connection isi model ke through establish hota hai.

**3-Way Handshake:**
Client aur server ke darmiyan connection establish karne ka process "3-way handshake" kehlata hai. Is process mein client aur server ek dusre se **language check** karte hain (yani dono ek hi protocol/language samajhte hain ya nahi) taake connection successfully establish ho sake. Steps generally ye hote hain:

1. Client server ko connection request bhejta hai (SYN).
2. Server acknowledge karta hai aur apni taraf se bhi request bhejta hai (SYN-ACK).
3. Client confirm karta hai (ACK) aur connection establish ho jata hai.

**Request-Response Process:**

1. Server client ki request receive karta hai.
2. Server apne **database** mein jaake required data ko store ya retrieve karta hai.
3. Server database ko check karta hai.
4. Server client ko response deta hai.
5. Ye response client ke **browser** par show ho jata hai.

**Cyber Security ka is model se link:**

Cyber security sab ko cover karti hai  client se le kar server tak, aur beech ke poore communication process tak. Har stage par security measures zaroori hain taake data safe rahe.

---



## 3. Non-Repudiation

Non-Repudiation ka matlab hai ke koi bhi person apne kiye gaye action se inkar (deny) nahi kar sakta, kyun ke uska proof maujood hota hai.

**Example 1 - Messaging:**

Agar koi person apne mobile se kisi doosre ko WhatsApp par message karta hai, to jis device se ye message hua hai, uska record us device ke registered name se link hota hai. Agar us person ke device se kisi company ka data hack ho jaye, to wo is baat se inkar nahi kar sakta ke usne aisa nahi kiya kyun ke device aur account uske naam par register hai. **No chance of denial.**

**Example 2 - Social Media:**
Agar kisi social media account se koi aisi post ki jati hai jo state ke against ho, to us account ka owner hi is action ke liye responsible hoga. Wo ye claim nahi kar sakta ke usne wo post nahi ki.

**Concept Summary:** Non-Repudiation is baat ko ensure karta hai ke digital actions (messages, posts, transactions) ka clear ownership record ho, taake koi bhi apni action se baad mein mukar na sake.

---



## 4. Gap Analysis

Gap Analysis ek process hai jisme ye dekha jata hai ke kisi student ya person ko pehle kitna pata tha aur ab uski knowledge mein kya improvement (gap fill) hui hai.

Jo students shuru mein kisi topic ke baare mein kuch nahi jaante the, ab wo apna gap analyze kar sakte hain ke unhe kya cheezein pehle nahi pata thi aur ab kya naya seekha hai. Ye self-assessment ka ek tareeqa hai jisse learning progress ko track kiya ja sakta hai.

---



## 5. Zero Trust Policy

Zero Trust ek important cyber security concept hai jiska general rule hai: **"No Trust"**  yani kisi bhi user, device ya system par by default trust nahi kiya jata, chahe wo company ke andar hi kyun na ho.

**Zero Trust Policy:**

Is policy ke According, company ke andar sab par same rules apply hote hain kisi ko bhi uski position ya seniority ki wajah se extra trust ya access nahi diya jata. Har user ko har baar apni identity verify karni parti hai, chahe wo pehle bhi verified ho chuka ho.

**Purpose:**
Ye rules is liye banaye jate hain taake company ko hacking aur unauthorized access se save kiya ja sake. Agar sab ko automatically trust kar liya jaye, to ek compromised account puri company ke liye khatra ban sakta hai.

**Company Locker Example:**
Jaise kisi company ke locker (sensitive data/resources) tak sirf company ke **main/authorized persons** hi access kar sakte hain baqi kisi ko bhi bina verification ke access nahi diya jata. Isi tarah Zero Trust mein bhi har access request ko verify kiya jata hai, kisi ko bhi "already trusted hai" samajh kar seedha access nahi diya jata.

---



## Quick Recap

1. **Risk, Vulnerability, Threat** — Cyber security ki basics; risk hamesha maujood rehta hai, vulnerability weakness hoti hai, threat us weakness ka fayda uthata hai.
2. **Client Server Model** — Client request bhejta hai, server database check kar ke response deta hai; 3-way handshake se connection establish hota hai.
3. **Non-Repudiation** — Koi bhi apni digital action se inkar nahi kar sakta, proof hamesha maujood hota hai.
4. **Gap Analysis** — Pehle aur ab ki knowledge ka farq check karna, self-improvement track karne ke liye.
5. **Zero Trust Policy** — Kisi par bhi automatically trust na karna; har access ko verify karna, taake hacking se bacha ja sake.

