### **Solution:**  
**1. Root User se `oracle` ko Sudoers me Add Karna:**  
- Pehle `root` user ya kisi aise user se login karo jo `sudo` access rakhta ho.  

```bash
su - root
```

**2. Edit the Sudoers File:**  
```bash
visudo
```
- Ye file `/etc/sudoers` location pe hoti hai.  
- Ye command `vi` editor me open karega, aur ye safest way hai sudoers file ko edit karne ka.  

---

**3. Add the Following Line:**  
```bash
oracle ALL=(ALL) NOPASSWD:ALL
```

- **Explanation:**
  - `oracle`: User ka naam.  
  - `ALL`: Har system pe valid hai.  
  - `(ALL)`: Har user ke tarah command chala sakta hai.  
  - `NOPASSWD`: `sudo` karne pe password nahi mangega.  
  - `ALL`: Sabhi commands chala sakta hai.  

---

**4. Save and Exit:**  
- `Esc` press karo, phir `:wq` likho aur `Enter` daba do.  

---

**5. Verify the Changes:**  
```bash
su - oracle
sudo ls /root
```
- Agar `ls` command root directory me chal jaye bina kisi error ke, to changes sahi hai.  

---

### **Note:**  
- Agar security concern hai, to `NOPASSWD` ko hata sakte ho taaki `oracle` user se `sudo` commands chalane pe password maange.  
- Agar `visudo` ka use nahi karna hai, to direct edit bhi kar sakte ho:  
```bash
sudo nano /etc/sudoers
```
Lekin `visudo` best practice hai kyunki ye syntax check karta hai.
