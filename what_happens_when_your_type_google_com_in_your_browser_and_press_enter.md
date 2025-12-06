# 🚀 What Really Happens When You Type **https://www.google.com** and Hit Enter  

We type URLs every day without thinking what happens behind the scenes.. Or do you only care knowing when its about your favorite movie series.. How about you walk through it with me and understand **what actually happens**, step by step, when you hit *Enter*.

---

## 🌐 1. DNS: "Who on Earth Is Google?" 
Your browser doesn’t understand "google.com." It needs an **IP address**.  

So it asks:
"Hey DNS, where does *https://www.google.com* live?"

DNS checks its records. If your local cache doesn’t have it, the request climbs up the DNS hierarchy until someone authoritative replies with something like:

**142.251.179.xxx**  

Now we know exactly where to go. (hehe)

---

## 🔌 2. TCP/IP: "Let's establish a reliable connection"
With the IP in hand, the browser opens a **TCP connection**.   
This is the classic **three-way handshake**:    

1- **SYN** — "Hi."  
2- **SYN-ACK** — "Hi, got your hi."   
3- **ACK** — "Cool, we're synced."  

TCP is like a delivery service that won’t leave until you sign — every packet is tracked and accounted for.

---

## 🛡️ 3. Firewall: "Do you come in peace?" 
Your request passes through several **firewalls** along the way -> yours, your ISP’s, Google’s.

Firewalls check:

- Is this traffic allowed? (Port 443? ofcourse)  
- Is it suspicious? (Hopefully not..)

If everything looks good, your packets continue their journey.

---

## 🔐 4. HTTPS/SSL: "Prove you're actually Google.."
Before sending real data, your browser and Google perform a **TLS handshake**.

- Google presents its **SSL certificate**.  
- The browser verifies it (no impostors allowed hehe).  
- Both agree on encryption keys.

Now everything is encrypted -> nobody can spy on your search unless you literally show them your laptop (please don’t).

---

## ⚖️ 5. Load Balancer: "Pick a server, any server"  
Google doesn't rely on one machine. They run entire ecosystems of servers.

A **load balancer** decides:

- Which server is free  
- Which region is closest  
- Who can handle the request fastest  

Kinda like the traffic cop of the infinite Google highway.

---

## 🖥️ 6. Web Server: "Let me handle the HTTP stuff"  
After a backend server is chosen, the **web server** receives the request:
```bash
  GET / HTTP/1.1
  Host: www.google.com
```

Its job is simple:

- Accept the request  
- Interpret headers  
- Forward it to the correct internal service  

Basically the receptionist of the building.

---

## ⚙️ 7. Application Server: "Time to actually DO something"  
This is where the brains of Google Search kick in.

The application layer handles:

- Auto-suggestions  
- Ranking algorithms  
- ML-driven relevance  
- Ads (yes, always..)  

It figures out what you actually want and prepares your personalized results.

---

## 🗄️ 8. Database: "Fetching data... hold my coffee"  
Your query touches Google's **massive distributed databases**, which include:

- Web indexes  
- Caches  
- Knowledge graphs  
- ML models  

These aren’t tiny MySQL tables.. These are global, replicated, fault-tolerant data giants!

---

## 🎉 Finally: The Response  
The application server sends the results -> web server -> load balancer -> your browser.  
Your browser renders the DOM, CSS, and JavaScript, and suddenly:

**There it is.. The Google homepage**

A simple white screen hiding a world of complexity behind a single key press.

---

### ⭐ Final Thoughts  
Even a single Google search pulls together cryptography, distributed systems, networking, and a global infrastructure — all in milliseconds. If that isn’t internet magic, I don’t know what is, lol
