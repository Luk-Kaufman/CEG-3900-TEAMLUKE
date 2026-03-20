# Neverwinter Bank Notes

Neverwinter Bank is a cybersecurity challenge in the game Neverwinter Nights that contains intentional flaws. Challengers must be able to point out these flaws in the web app to be able to drain another user's account. The bank in the game provides additional storage for items and can be expanded to accommodate more bags and shared bank slots. Through this challenge, people can learn about and practice identifying, exploiting, and understanding security flaws such as:
- authentication bypasses
- session manipulation
- insecure client-server interactions

---

## Why Is The Challenge Important?

The Neverwinter Bank challenge provides:
- hands-on experience with real-world web vulnerabilities
- aid in developing offensive security skills
- reinforcement of understanding of how web applications function internally
- bridging of gaps between theoretical knowledge and practical application
- preparation for CTFs, penetration testing, and security careers
- learning in a safe, legal environment

---

## Concepts

### Authentication & Authorization
- Login mechanisms (username/password validation)
- Authentication bypass techniques (e.g., manipulating requests, cookies)
- Role-based access control (e.g., user vs admin)

### Session Management
- Use of cookies to maintain sessions
- Cookie tampering
- Session hijacking and fixation concepts

### Web Vulnerabilities
- Injection flaws
- Cross-site scripting
- Insecure Direct Object References (IDOR)
- Misconfigured authentication logic

### Tools & Techniques
- Browser DevTools (inspect, modify requests/responses)
- Intercepting proxies (e.g., Burp Suite)
- Manual HTTP request crafting
- Payload testing and fuzzing

### HTTP Fundamentals
- Understanding HTTP requests and responses
- Headers, methods (GET, POST), and status codes
- How data flows between client and server

### Client-Side vs Server-Side
- Difference between client-side controls (JavaScript) and server-side validation
- Why client-side changes (like modifying cookies) may not work
- Importance of server-side enforcement

---

## Lab Solutions
