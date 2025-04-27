# UAP CyberSeige Networking Writeups


## 1.

![image](https://github.com/user-attachments/assets/20845662-6f79-4c66-b526-869872bdcfad)


From the dumped file, found a `test.html` file. Opened it in the browser and retrieved the flag.
![image](https://github.com/user-attachments/assets/80430258-5203-4836-a088-27c1164145cd)
![image](https://github.com/user-attachments/assets/5e42617d-1243-41f3-82fe-33448eac72f0)



**Answer:**
```
CS{ironman@xyz_passwordforxyz}
```

---

## 2. 
![image](https://github.com/user-attachments/assets/b659e867-533f-44e3-a3b1-016aaaac8936)


In the dumped `.htaccess` file, found a suspicious string. 
![image](https://github.com/user-attachments/assets/68dfefe6-f57d-4b91-9eeb-0d850d746aa0)

Applied ROT13 brute-force and retrieved the hidden flag.

**Answer:**
```
CS{7h1S_1s_7He_H1Dd3N_Fl4G}
```

---

## 3.
![image](https://github.com/user-attachments/assets/c1ab0605-d454-45ed-bf9a-f5b5b9705694)

Grep for 'fuzz' keyword inside traffic:
```
strings traffic.pcapng | grep -i 'fuzz'
```
Found the User-Agent string:
```
Fuzz Faster U Fool v2.1.0-dev
```

**Answer:**
```
CS{ffuf_v2.1.0-dev}
```

---

## 4. 
![image](https://github.com/user-attachments/assets/30aa5c59-7e52-46a6-86c4-e1300289eee8)

Searched HTTP traffic in Wireshark for "access_code".

Noticed one access code had a different length compared to others.
![image](https://github.com/user-attachments/assets/70ab5c91-4c9f-4755-a886-d9cf6d23cebb)


**Answer:**
```
CS{5425}
```

---

## 5. 
![image](https://github.com/user-attachments/assets/339f14df-994b-4799-8cf0-9813b75eafe5)

During web register attempt, found username:
```
ksadm1n
```

**Answer:**
```
CS{ksadm1n}
```

---

## 6. 
![image](https://github.com/user-attachments/assets/75b91bae-bfb8-4f84-ad25-f27b8d13b78e)

From the dumped `debug.html` file, found a Base64 encoded string.

Decoded it to find the flag.
![image](https://github.com/user-attachments/assets/6d4d94bf-e0dd-42ec-92a7-e8a52f6e02d7)


**Answer:**
```
CS{TdGnDjUfKdLWKgUdVIfUkfUfkfUfKdLWfJfUeVK}
```

---

## 7. 
![image](https://github.com/user-attachments/assets/6b16bea4-1412-4e73-9431-126b359b24df)

The command is sent in a POST request to `/ai`:

In JavaScript:
```javascript
axios.post("http://192.168.1.6:8000/ai", { caseDescription });
```
The command prefix used was `!dmc:`.

**Answer:**
```
CS{ai_!dmc:}
```

---

## 8. 
![image](https://github.com/user-attachments/assets/f6b46fc0-0e48-44f6-be38-7642b8995bd1)

Grep for AI model references:
```
strings traffic.pcapng | grep -i 'gemini'
```
Found:
```
gemini
Gemini
```

**Answer:**
```
CS{gemini}
```

---

## 9. 
![image](https://github.com/user-attachments/assets/3bb914bb-f7e3-4796-a8a6-29a559044f95)

Found reverse shell setup in `ai.json` file:
```
export RHOST="192.168.1.9"; export RPORT=6542;
```
Thus, port `6542` was used for the reverse shell.

**Answer:**
```
CS{6542}
```

---

## 10. 
![image](https://github.com/user-attachments/assets/a6890b27-324f-456c-b00d-0855c3b3e0d1)

From `AiController.php`, backend points to:
```
http://127.0.0.1:8564/generate
```
Thus:
- Endpoint: `/generate`
- Port: `8564`

**Answer:**
```
CS{generate_8564}
```

---

## 11. 
![image](https://github.com/user-attachments/assets/f5e96fb2-2670-4f1c-92a6-c45175f7b580)

Found `dashboard.html` in dumped files.
![image](https://github.com/user-attachments/assets/32684343-b377-4512-a69b-0fdb9f13a5e0)

Observed user role as:
```
journalist
```

**Answer:**
```
CS{journalist}
```

---

# End of Writeups
---


