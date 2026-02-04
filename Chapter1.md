**“Please Do Not Throw Sausage Pizza Away”**

|الحرف|الطبقة|
|---|---|
|P|Physical|
|D|Data Link|
|N|Network|
|T|Transport|
|S|Session|
|P|Presentation|
|A|Application|

---
📌 إشارات كهربا / ضوء / موجات.
# threats
[[Threats Risks Vulnerabilities]]
## Vulnerabilities
## 🧠 1️⃣ Injection & Code Injection Vulnerabilities

|النوع|الفكرة الأساسية|الخطر|
|---|---|---|
|SQL Injection|إدخال أوامر SQL عبر input|تسريب / تعديل / حذف بيانات|
|HTML Injection|إدخال HTML في الصفحة|تغيير محتوى الصفحة / تمهيد لـ XSS|
|Command Injection|تمرير أوامر نظام عبر التطبيق|تنفيذ أوامر OS|
|Dynamic Code Eval|تشغيل كود ديناميكي غير آمن|تنفيذ كود|
|Object Injection|التلاعب بالكائنات|تحكم بالتنفيذ|
|Remote File Inclusion|تحميل ملفات خارجية|تنفيذ كود|
|Format String|التحكم بصيغة الطباعة|تسريب ذاكرة|
|Shell Injection|أوامر شِل عبر input|تحكم بالنظام|

---

## 🗄️ 2️⃣ SQL Injection (SQLi)

|البند|الشرح|
|---|---|
|التعريف|إدخال SQL داخل input أو URL|
|التأثير|قراءة / تعديل / حذف DB|
|مثال|`Santos' OR 1=1;--`|
|أماكن شائعة|Login – Search – E-commerce|

### أنواع SQLi

|النوع|كيف يتم|
|---|---|
|In-band|نفس القناة (النتيجة تظهر بالصفحة)|
|Out-of-band|قناة ثانية (email / request خارجي)|
|Blind|استنتاج عبر السلوك (True/False / Time)|

---

## 🌐 3️⃣ HTML Injection

|البند|الشرح|
|---|---|
|التعريف|إدخال HTML داخل التطبيق|
|النتيجة|تغيير الصفحة / سرقة cookies|
|العلاقة|ممكن تتطور لـ XSS|

---

## 💻 4️⃣ Command Injection

| البند   | الشرح                        |
| ------- | ---------------------------- |
| التعريف | تمرير أوامر نظام عبر التطبيق |
| الفرق   | ليس Buffer Overflow          |
| السبب   | عدم التحقق من input          |
| النتيجة | تنفيذ أوامر OS               |

---

## 🔐 5️⃣ Authentication-Based Vulnerabilities

|النوع|
|---|
|Credential Brute Force|
|Session Hijacking|
|Redirecting|
|Default Credentials|
|Weak Credentials|
|Kerberos Exploits|

---

## 🔑 6️⃣ Brute Force & Password Cracking

|النوع|الشرح|
|---|---|
|Online|محاولات مباشرة (سهل الكشف)|
|Offline|كسر hashes (أخطر)|

|عامل ضعف|التأثير|
|---|---|
|كلمات مرور ضعيفة|اختراق سريع|
|خوارزميات ضعيفة (MD5, RC4)|كسر سهل|
|بدون Salt|Rainbow Tables|

|حماية|
|---|
|MFA|
|Throttling|
|Logging & Auditing|

---

## 🕵️ 7️⃣ Session Hijacking

|الطريقة|الشرح|
|---|---|
|Token Prediction|توقع session ID|
|Session Sniffing|اعتراض traffic|
|MITM|بين العميل والسيرفر|
|MITB|المتصفح نفسه مخترق|

⚠️ Session IDs غير المفلترة → SQLi / Stored XSS

---

## 🔓 8️⃣ Default Credentials

|المشكلة|الشرح|
|---|---|
|كلمات افتراضية|routers / switches / firewalls|
|المصدر|documentation / مواقع|
|أدوات|Shodan|
|الحل|تغيير + تقييد الوصول|

---

## 🧱 9️⃣ IDOR (Insecure Direct Object Reference)

|البند|الشرح|
|---|---|
|السبب|عدم التحقق من الصلاحيات|
|الطريقة|تغيير ID بالـ URL|
|مثال|`customerID=1245 → 1246`|
|الخطر|الوصول لبيانات غير مسموحة|

|الحماية|
|---|
|Authorization checks|
|Indirect references|
|Input validation|

---

## 🧪 🔟 Cross-Site Scripting (XSS)

|النوع|كيف يصير|
|---|---|
|Reflected|الرابط يعكس الكود|
|Stored|الكود محفوظ بالـ DB|
|DOM-based|بالكلاينت فقط|

|أماكن شائعة|
|---|
|Search|
|Headers|
|Input fields|
|Error messages|
|Hidden fields|

|التأثير|
|---|
|سرقة Cookies|
|Session Hijack|
|Redirect|
|Account compromise|

---

## 🔄 1️⃣1️⃣ CSRF

|البند|الشرح|
|---|---|
|الفكرة|استغلال ثقة الموقع بالمستخدم|
|الشرط|المستخدم مسجل دخول|
|الطريقة|طلب HTTP خبيث|
|الاسم|Session Riding|

---

## 🍪 1️⃣2️⃣ Cookie Manipulation (Stored DOM)

|البند|الشرح|
|---|---|
|السبب|input مخزن بالـ DOM|
|الطريقة|JavaScript يغير cookie|
|الخطر|حسب دور cookie|

---

## ⏱️ 1️⃣3️⃣ Race Conditions (TOCTOU)

|البند|الشرح|
|---|---|
|الفكرة|فرق توقيت check / use|
|الصعوبة|عالية جدًا|
|مثال|ACL قبل التحديث|
|الاسم|TOCTOU|

---

## 🔌 1️⃣4️⃣ Unprotected APIs

|النوع|الوصف|
|---|---|
|SOAP|XML – قديم – strict|
|REST|JSON – Swagger|
|GraphQL|Query Language|

|خطورة|
|---|
|توثيق = خريطة هجوم|
|صعب المراقبة|
|معقد|

|توثيق|
|---|
|Swagger / OpenAPI|
|WSDL|
|WADL|

---

## 🧨 1️⃣5️⃣ Buffer Overflow & ret2libc

|البند|الشرح|
|---|---|
|Buffer Overflow|فيضان stack|
|ret2libc|استخدام system() بدل كود|
|NX Bit|يمنع shellcode|
|ليش ما يمنع ret2libc؟|كود موجود|

|الحماية|
|---|
|Stack Canary|
|ASCII Armoring|
|ASLR (قوي 64-bit)|

---

## 🧠 خلاصة ذهبية (تحطها Note لحالها):

> **كل الثغرات تدور حول ثلاث أشياء:**  
> Input غير مفلتر  
> ثقة زائدة  
> منطق سيء

---

# Cisco ACL – Simple Notes

## ما هي ACL؟
- قائمة بتقرر:
  - مين بيمر
  - ومين بيتمنع

## ما هي ACE؟
- سطر واحد داخل ACL

---

## أهم قاعدة
- ACL تنفحص **من فوق لتحت**
- أول سطر يطابق → خلص القرار

---

## إضافة سطر جديد
- أي ACE جديدة → تنضاف **آخر القائمة**

---

## Implicit Deny
- آخر ACL دائمًا فيه:
  - deny any
- إذا ما انطبق ولا سطر → Drop

---

## Security Levels (ASA)
- Inside = 100
- Outside = 0

### السلوك الافتراضي
- Inside → Outside ✅ مسموح
- Outside → Inside ❌ ممنوع

---

## لما نحط ACL
- من Inside → Outside:
  - نلغي السماح الافتراضي
- من Outside → Inside:
  - لازم السماح يكون واضح

---

## وين نحط ACL؟
- لازم تنربط بواجهة
- بدون ربط = ما بتشتغل

---

## أنواع الترافيك
### TCP / UDP
- ذكي (Stateful)
- الرد مسموح تلقائيًا

### ICMP
- غبي شوي 😅
- بدو سماح بالاتجاهين
- إلا إذا فعلنا ICMP inspection

---

## شغلات لازم تتذكرها
- الترتيب أهم شي
- deny مخفي موجود دائمًا
- ACL بدون interface = بلا قيمة
# Cisco ASA – Types of ACLs (Very Simple)

## ليش في أكتر من نوع ACL؟
- لأن مو كل الترافيك متل بعض
- في IP
- في Non-IP
- في VPN
- في Web

---

## 1️⃣ Standard ACL
- تفحص:
  - IP واحد فقط (بسيطة جدًا)
- الاستخدام:
  - VPN
  - Routing (OSPF / BGP)
- ❌ ما بتفلتر ترافيك على الواجهة
- ✅ فقط Routed Mode

👉 نادرًا نستخدمها للأمن الحقيقي

---

## 2️⃣ Extended ACL (الأهم 🔥)
- تفحص:
  - Source IP
  - Destination IP
  - Protocol (TCP / UDP / ICMP)
  - Ports
- الاستخدام:
  - فلترة الترافيك
  - NAT
  - VPN
- ✅ Routed Mode
- ✅ Transparent Mode

👉 90% من الشغل عليها

---

## 3️⃣ IPv6 ACL
- نفس Extended ACL
- بس لـ IPv6
- لا فلسفة زيادة

---

## 4️⃣ EtherType ACL
- تشتغل على:
  - Layer 2
- تفرق بين:
  - IP
  - Non-IP (مثل IPX)
- تستخدم Ethernet Type
- ✅ فقط Transparent Mode

⚠️ implicit deny موجود  
⚠️ implicit deny **ما يمنع IP**
إلا إذا حطيت deny صريح

---

## 5️⃣ Webtype ACL
- خاصة بـ:
  - SSL VPN
- إذا في ACL:
  - وما صار match → DROP
- إذا ما في ACL:
  - الترافيك مسموح

---

## قاعدة ذهبية 🧠
- كل ACL فيها:
  - implicit deny
- ACL بدون Interface:
  - ولا شي 😴

---

## Firewall Types (مختصر جدًا)
### Packet Filtering Firewall
- يشوف:
  - IP
  - Port
- ❌ ما يفهم التطبيق
- ❌ ينضحك عليه بـ spoofing
- ❌ صعب مع التطبيقات الحديثة

### Stateful Firewall
- يفهم:
  - Connection
  - TCP flags
- أذكى ✔️

### Next-Gen Firewall
- يفهم:
  - Application
  - User
  - Context
- مستوى احترافي 🔥

---

## كيف أحفظها؟
- Standard → بسيطة
- Extended → الأساس
- EtherType → Layer 2
- Webtype → VPN
## Firewalls & ACLs – Super Simple

|النوع|وين؟|شو يفلتر؟|ملاحظة ذهبية|
|---|---|---|---|
|Standard ACL|L3|Destination IP|مو للفِلترة|
|Extended ACL|L3/L4|IP + Ports|الأكثر استخدامًا|
|IPv6 ACL|L3|IPv6 فقط|واضح|
|EtherType ACL|L2|IP / Non-IP|Transparent mode|
|Webtype ACL|VPN|SSL VPN|implicit deny|


# Firewalls
[[FIREWALLS]]

| العنصر | الشرح المختصر | ملاحظات أمنية |
|------|---------------|---------------|
| Firewall | جهاز/برنامج يتحكم بحركة المرور بين الشبكات | خط الدفاع الأول |
| وظيفة Firewall | Allow / Deny traffic حسب rules | لا يكتشف الهجمات المعقدة |
| Packet Filtering FW | يفحص L3/L4 (IP, Port, Protocol) | سريع – أمانه محدود |
| Stateful Firewall | يتتبع حالة الجلسات (Sessions) | أكثر استخدامًا عمليًا |
| Application Firewall | يفحص L7 (HTTP, FTP, SMTP) | يفهم محتوى التطبيق |
| NGFW | Firewall + IPS + App Control | مثل Cisco Firepower |
| Network-based FW | يحمي شبكة كاملة | يوضع عند البوابة |
| Host-based FW | يحمي جهاز واحد | Windows Firewall |
| Ingress Filtering | فلترة traffic الداخل | منع هجمات خارجية |
| Egress Filtering | فلترة traffic الخارج | منع data exfiltration |
| Default Policy | Deny All | best practice |
| Rule Order | ترتيب القواعد مهم جدًا | أول Rule ينطبق يُنفّذ |
| Logging | تسجيل الأحداث | مهم للتحقيق (Forensics) |
| DMZ | شبكة معزولة للخدمات العامة | تقلل خطر الاختراق |

# INTRUSION DETECTION SYSTEMSAND INTRUSION PREVENTIONSYSTEMS
[[Intrusion Detection Systems (IDS)  Intrusion Prevention Systems (IPS)]]

| النوع | الشرح | طريقة العمل / التحليل | مثال | مميزات | عيوب |
|-------|-------|----------------------|------|--------|------|
| IDS (Intrusion Detection System) | يكشف محاولات الهجوم على الشبكة أو الأجهزة، مثل الوصول غير المصرح به أو DDoS أو الفيروسات | مراقبة promiscuous mode، إرسال تنبيه عند اكتشاف تهديد | جهاز IDS يراقب حزمة خبيثة تصل إلى 10.10.20.0/24 ويبلغ النظام المراقب | كشف الهجمات قبل حصولها | لا يمنع الهجمات مباشرة، الحزمة الضارة تصل للهدف |
| IPS (Intrusion Prevention System) | يكشف ويمنع الهجمات عن طريق إسقاط الحزم الخبيثة | يمكن تفعيل inline mode بعد مرحلة المراقبة | IPS يوقف حزمة خبيثة أثناء مرورها على الشبكة ويبلغ النظام | يمنع الهجمات مباشرة، حماية متقدمة | استهلاك عالي للموارد، يحتاج مراقبة دقيقة |
| NIPS (Network-based IPS) | IPS شبكي تقليدي | تحليل حركة الشبكة عبر الأجهزة | Cisco IPS 4200، Catalyst 6500 IPS module | حماية الشبكة بالكامل | أجهزة قديمة وصلت EoL |
| NGIPS (Next-Generation IPS) | IPS متطور للأداء العالي، يدعم الشبكات الافتراضية | تحليل الحركة، التوافق مع تطبيقات حديثة | Cisco Firepower IPS | حماية متكاملة، يدعم الافتراضية | يحتاج تعلم للتعامل مع كل الميزات |
| HIPS (Host-based IPS) | IPS مخصص للجهاز نفسه | مراقبة الحزم والعمليات على الجهاز | HIPS على سيرفر ويندوز | حماية الجهاز الفردي | محدود بالنطاق، لا يغطي الشبكة كاملة |
| Pattern Matching | البحث عن تسلسل بايت محدد في الحزم | يستخدم Signatures للكشف | TCP packet على port 1234 و payload = ff11ff22 | بسيط وسريع، يربط مباشرة بالهجوم | false positives/negatives عالية |
| Stateful Pattern Matching | تحسين Pattern Matching بأخذ ترتيب الحزم بعين الاعتبار | تتبع TCP stream للحزم غير المشفرة | كشف هجمات TCP عبر أكثر من حزمة | يدعم جميع البروتوكولات غير المشفرة | استهلاك موارد أعلى |
| Protocol Analysis | تحليل البروتوكولات والتأكد من الالتزام بالقواعد | فحص الحقول والأوامر في البروتوكول | فحص SMTP commands مثل HELO, MAIL | يقلل false positives | يعتمد على تعريف واضح للبروتوكول |
| Heuristic Analysis | استخدام تحليل إحصائي وسلوك الشبكة | يعتمد على الخوارزميات لتحديد الشذوذ | كشف scanning ports عبر host معين | يكتشف هجمات غير معروفة | يحتاج ضبط دقيق لتقليل false positives |
| Anomaly-Based Analysis | مقارنة السلوك الحالي مع "السلوك الطبيعي" | تحديد الانحرافات عن السلوك المتوقع | كشف DDoS أو zero-day | يكتشف هجمات جديدة | تعريف السلوك الطبيعي صعب، false positives محتمل |
| Global Threat Correlation | استخدام بيانات من Cisco Talos لتقييم سمعة IP | تصفية حركة الشبكة حسب سمعة IP | IPS يمنع حركة من IP ذو سمعة سيئة | توقع سلوك IP مستقبلي | يعتمد على تحديث البيانات الخارجية |
| Firepower Management Center (FMC) | منصة إدارة مركزية لكل أجهزة IPS وFTD | إدارة سياسات مركزية وتحليلات وتقارير | ضبط سياسة DDoS لجميع NGIPS وFTD | إدارة مركزية، تقارير وتحليلات متقدمة | يحتاج تدريب للتعامل مع كل الميزات |


# ADVANCED MALWARE PROTECTION
[[Cisco ADVANCED MALWARE Protection(AMP)]]
---

## 🦠 Malware Types (Quick Reference)

|Malware Type|Description (Short)|
|---|---|
|Virus|Infects files/systems, corrupts or steals data|
|Worm|Self-replicates over network without user action|
|Mailer Worm|Spreads itself via email automatically|
|Logic Bomb|Malicious code triggered by specific condition|
|Trojan Horse|Disguised as legit software, steals or destroys data|
|Backdoor|Allows remote attacker access/control|
|Exploit|Uses a specific vulnerability|
|Downloader|Downloads additional malware|
|Spammer|Sends spam to scam users|
|Keylogger|Records keystrokes (passwords, CC, PINs)|
|Rootkit|Gains root/admin-level control|
|Ransomware|Encrypts data and demands payment|

---

## 🛡️ Antivirus Examples

|Type|Products|
|---|---|
|Commercial|Avast, AVG, Bitdefender, Kaspersky, McAfee, Sophos, Norton|
|Open Source|ClamAV|
|Community-Based|Immunet|

---

## 🔐 Personal Firewall vs HIPS vs AMP for Endpoints

|Feature|Personal Firewall|HIPS|AMP for Endpoints|
|---|---|---|---|
|Layer Control|L3 / L4|L3–L7|L3–L7|
|Malware Protection|❌|✅|✅✅|
|Behavioral Analysis|❌|Limited|Advanced|
|Retrospective Analysis|❌|❌|✅|
|Threat Intelligence|❌|❌|Cisco Talos|
|Modern Attacks|❌|⚠️|✅|

---

## 💻 AMP for Endpoints — Summary

|Feature|Description|
|---|---|
|Scope|Endpoint protection|
|OS Support|Windows, macOS, Linux, Android|
|Detection|Beyond point-in-time|
|Retrospective Security|Detects past-allowed malware|
|File Trajectory|Tracks file behavior over time|
|Device Trajectory|Tracks device activity|
|Threat Intel|Cisco Talos|
|Supported Files|EXE, PDF, ZIP, ELF, MACHO, JAVA, SWF|

---

## 🌐 AMP for Networks — Summary

|Feature|Description|
|---|---|
|Scope|Network-based protection|
|Deployment|Firepower, ASA w/ FirePOWER, NGIPS|
|Inspection Mode|Inline (in-flight)|
|Detection|Continuous + retrospective|
|File Trajectory|Tracks file spread in network|
|File Capture|Stores files for analysis|
|Hashing|SHA-256|
|Cloud Usage|Hash only (file optional via Threat Grid)|

---

## 🔄 AMP for Networks Detection Flow

|Step|Action|
|---|---|
|1|File passes appliance|
|2|SHA-256 hash created|
|3|Check local cache|
|4|Query FMC if unknown|
|5|FMC queries cloud|
|6|Block / Allow / Retrospective alert|

---

## 🧠 AMP Components Overview

| Component                | Role                        |
| ------------------------ | --------------------------- |
| AMP for Endpoints        | Remediates infected hosts   |
| AMP for Networks         | Detects & blocks in transit |
| AMP for Content Security | Email/Web inspection        |
| FMC                      | Central management          |
| Threat Grid              | Advanced sandbox analysis   |

# WEB SECURITY APPLIANCE

[[Web Security Appliance (WSA)]]

|Feature / Topic|Explanation (Simple)|Example|Summary (EN)|
|---|---|---|---|
|**Web Security Appliance (WSA)**|جهاز يحمي الشبكة من تهديدات الويب، بما فيها المواقع الشرعية المصابة. يستخدم معلومات سحابية لتحليل الملفات قبل، أثناء، وبعد الهجوم.|موظف يفتح موقع إخباري يحتوي على إعلان مصاب، WSA يوقف الهجوم قبل وصوله للجهاز.|WSA protects networks from web-based threats using cloud intelligence and attack lifecycle analysis.|
|**Attack Continuum**|حماية الشبكة قبل وأثناء وبعد الهجوم باستخدام معلومات Cisco Talos وملفات السمعة وSandboxing.|اكتشاف فيروس قبل الدخول للشبكة، أو فحص ملف مشتبه به في Sandbox بعد الهجوم.|Lifecycle-based protection using prevention, detection, and retrospective analysis.|
|**Explicit Proxy Deployment**|العميل يعرف أن الطلب يمر عبر WSA.|المتصفح مهيأ لإرسال كل طلب HTTP للـ WSA مباشرة.|Clients explicitly route traffic through WSA.|
|**Transparent Proxy Deployment (WCCP)**|العميل لا يعرف أن الطلب يعاد توجيهه، يستخدم البروتوكول WCCP.|الراوتر يعيد توجيه HTTP تلقائياً للـ WSA بدون تعديل على المتصفح.|Transparent traffic redirection using WCCP protocol.|
|**WCCP Registration**|WSA يرسل كل 10 ثواني “Here I am”، السيرفر يرد “I see you”، بعد 30 ثانية بدون رد يعتبر العميل Inactive.|شبكة كبيرة فيها عدة WSAs، الراوتر يراقب كل الأجهزة ويعرف أي WSA توقف عن العمل.|WCCP enables WSA registration and monitoring for large-scale deployments.|
|**Real-time Antimalware Adaptive Scanning**|اختيار ديناميكي لمحرك مكافحة الفيروسات بناءً على سمعة URL ونوع المحتوى وفعالية الفحص.|فحص صورة أو JavaScript أو Adobe Flash يحتوي على malware بطريقة متقدمة.|Dynamically selects the most effective antimalware engine to increase detection.|
|**Layer 4 Traffic Monitor**|يراقب حركة الشبكة ويمنع البرمجيات الخبيثة، يحدث قائمة IPs ضارة تلقائياً.|حظر نطاق جديد يستخدمه spyware أو malware.|Monitors Layer 4 traffic to detect and block spyware.|
|**Third-Party DLP Integration**|إعادة توجيه حركة الإنترنت لأجهزة DLP لفحص المحتوى ومنع تسريب البيانات.|منع رفع ملفات سرية على Dropbox أو Google Drive.|Integrates with DLP to inspect web traffic and prevent data exfiltration.|
|**File Reputation**|تقييم سمعة الملفات باستخدام معلومات Cisco Talos كل 3–5 دقائق.|ملف جديد يرفع على الشبكة، يتم التحقق من سمعته قبل السماح له بالوصول.|Continuously evaluates file reputation using threat intelligence.|
|**File Sandboxing**|تشغيل الملفات المشبوهة في بيئة آمنة لتحليل سلوكها، مع استخدام AI لتحديد مستوى التهديد.|ملف exe جديد يختبر في Sandbox لمعرفة إذا كان malware.|Executes suspicious files in a sandbox to determine threat level.|
|**File Retrospection**|إعادة فحص الملفات السابقة للكشف عن تهديدات لم تُكتشف سابقاً.|ملف تم السماح له سابقاً يكتشف لاحقاً أنه malware، يتم إرسال تنبيه.|Re-examines previously allowed files for late-detected threats.|
|**Application Visibility and Control**|مراقبة أو حظر التطبيقات حسب سياسة الشركة.|السماح Facebook لكن حظر الألعاب المصغرة داخل الموقع.|Controls and monitors web applications based on corporate policy.|

# Cisco AsyncOS supports numerous features that help mitigate email-based threats. The following are examples of the features supported by the Cisco ESA:
[[Email Security Appliance (ESA)]]

| Feature              | What it Does (Simple)                                | Key Benefit                          |
| -------------------- | ---------------------------------------------------- | ------------------------------------ |
| Access Control       | Controls who can send emails based on IP or domain   | Blocks unwanted senders early        |
| Antispam             | Filters spam using reputation and Talos intelligence | Reduces spam and phishing            |
| Network Antivirus    | Scans email attachments at the gateway               | Stops malware before delivery        |
| AMP                  | Detects, analyzes, and tracks malware over time      | Retrospective malware detection      |
| DLP                  | Prevents sensitive data from leaving via email       | Stops data exfiltration              |
| Email Encryption     | Encrypts outbound emails                             | Ensures confidentiality & compliance |
| Email Authentication | Verifies sender identity (SPF, DKIM, etc.)           | Prevents spoofing & impersonation    |
| Outbreak Filters     | Blocks new and emerging email threats                | Zero-day email attack protection     |


# Identity Services Engine (ISE)
[[Identity Services Engine (ISE)]]

# SECURITY CLOUD-BASED SOLUTIONS

[[SECURITY CLOUD-BASED SOLUTIONS]]

### ALL

| الخدمة               | الوظيفة الأساسية                  | مثال عملي                 | ملاحظة              |
| -------------------- | --------------------------------- | ------------------------- | ------------------- |
| Cloud Email Security | حماية البريد من phishing وmalware | منع إيميل تصيّد قبل وصوله | Email gateway سحابي |
| AMP Threat Grid      | تحليل malware                     | فحص ملف مشبوه             | Sandboxing          |
| Threat Awareness     | Threat intelligence               | رؤية عامة للتهديدات       | تحليل سياقي         |
| Umbrella             | DNS security                      | منع موقع خبيث قبل الاتصال | ممتاز للـ remote    |
| Stealthwatch Cloud   | Network monitoring                | كشف حركة مشبوهة           | Behavioral analysis |
| CloudLock            | CASB                              | حماية Google Drive        | SaaS security       |

---
### Cloud Email Security

| الخدمة                | الوظيفة               | مثال                     | ملاحظة            |
| --------------------- | --------------------- | ------------------------ | ----------------- |
| Cloud Email Security  | حماية الإيميل سحابيًا | منع phishing             | High Availability |
| Hybrid Email Security | Cloud + On-Prem       | بيانات حساسة تبقى محليًا | Compliance        |

---
 ### Cisco AMP Threat Grid

|الخدمة|الوظيفة|مثال|ملاحظة|
|---|---|---|---|
|AMP Threat Grid|Malware Analysis|تحليل ملف مشبوه|IOC + Threat Score|
|Glovebox|Manual interaction|تشغيل malware بأمان|ضد evasive malware|


---

### Umbrella (OpenDNS) 

| الخدمة      | الوظيفة      | مثال         | ملاحظة           |
| ----------- | ------------ | ------------ | ---------------- |
| Umbrella    | DNS Security | منع phishing | يعمل بأي مكان    |
| Investigate | Threat Intel | تحليل دومين  | API + Prediction |



---

### Stealthwatch Cloud 

|الخدمة|الوظيفة|مثال|ملاحظة|
|---|---|---|---|
|Stealthwatch Cloud|Network Monitoring|كشف حركة مشبوهة|AWS/GCP/Azure|


---


### CloudLock

|الخدمة|الوظيفة|مثال|ملاحظة|
|---|---|---|---|
|CloudLock|CASB + DLP|منع تسريب بيانات|ML + UEBA|
|Apps Firewall|App Control|حظر cloud app خبيث|Shadow IT|

---





# CISCO NETFLOW
[[CISCO NETFLOW]]
## جدول Obsidian

|العنصر|الشرح|ملاحظة|
|---|---|---|
|NetFlow|Network Telemetry|Visibility كاملة|
|Flow|اتصال أحادي الاتجاه|Unidirectional|
|5-Tuple|تعريف الاتصال|IPs + Ports + Protocol|
|Security Use|كشف هجمات|DoS / C2 / Anomaly|
|Export|UDP|2055 شائع|
|IPFIX|Standard Flow|UDP 4739|
|NetFlow v9|أساس IPFIX|Template-based|


# DATA LOSS PREVENTION(DLP)
[[DATA LOSS PREVENTION(DLP)]]
## 🛡️ Data Loss Prevention (DLP)

| 🧩 Category | 📌 Description |
|------------|---------------|
| 🎯 Purpose | Prevent sensitive data from leaving the organization without authorization |
| 📤 Data in Motion | Email traffic, web uploads, file transfers |
| 💾 Data at Rest | Stored data in SaaS, IaaS, PaaS platforms |
| 🖥️ Data in Use | Copy, paste, print, screen capture, uploads |
| 🔍 Inspection Type | Deep content inspection (content, metadata, size) |
| 🚨 Main Threats | Insider threats, human error, data exfiltration |
| 🧠 Detection Methods | Pattern matching, policies, context awareness |
| ☁️ Cloud DLP | API-based inspection and retroactive monitoring |
| 🤖 Automation | Encryption, quarantine, alerting, user notification |
| 🧰 Cisco Solutions | ESA, WSA, Cloud Email Security, CloudLock |
| 📊 Visibility | Full visibility of inbound and outbound data flows |
| 🧪 Use Cases | Compliance, incident response, forensic analysis |

---

# Defense in Depth
🛡️ Defense in Depth Strategy
[[Defense in Depth (الدفاع متعدد الطبقات)]]

| 🔐 Layer        | 🧩 Description        | 🛠️ Examples                  |
| --------------- | --------------------- | ----------------------------- |
| 🧑 Human        | Policies & awareness  | Training, procedures          |
| 🏢 Physical     | Protect facilities    | Cameras, badge readers        |
| 🌐 Network      | Secure infrastructure | CoPP, routing auth, hardening |
| 💻 Host         | Secure endpoints      | AV, AMP, EDR                  |
| 🧪 Application  | Secure apps           | XSS, CSRF, SQLi protection    |
| 📦 Data         | Protect information   | Encryption at rest/in transit |
| 👁️ Visibility  | See everything        | NetFlow, logs, telemetry      |
| 📐 Architecture | Smart design          | Segmentation, SDN             |
| ⚙️ Policy       | Business glue         | RBAC, least privilege         |
# CIA Triad (Confidentiality – Integrity – Availability)
[[CIA Triad (Confidentiality – Integrity – Availability)]]


| 🔐 Principle | 🧠 Definition | 💥 Attacks | 🛡️ Controls |
|-------------|-------------|-----------|------------|
| Confidentiality | Prevent unauthorized access | Data breach, sniffing | Encryption, ACL, Auth |
| Integrity | Prevent unauthorized changes | Config tampering, MITM | Hashing, signatures |
| Availability | Ensure system uptime | DoS, ransomware | Redundancy, LB |


# RISK & RISK ANALYSIS
[[RISK & RISK ANALYSIS]]
 🔥 Risk & Risk Analysis

| Concept | Description |
|------|------------|
| Risk | Likelihood × Impact |
| Inherent Risk | Risk before controls |
| Residual Risk | Risk after controls |
| ISO 27001 | ISMS & risk-based planning |
| ISO 27005 | Cybersecurity risk management |
| FFIEC | Risk & maturity assessment |
| CVSS | Vulnerability severity scoring |
| Risk Treatment | Mitigate, Accept, Avoid, Transfer |

## 🔥 Risk & Risk Analysis

| Concept | Description |
|------|------------|
| Risk | Likelihood × Impact |
| Inherent Risk | Risk before controls |
| Residual Risk | Risk after controls |
| ISO 27001 | ISMS & risk-based planning |
| ISO 27005 | Cybersecurity risk management |
| FFIEC | Risk & maturity assessment |
| CVSS | Vulnerability severity scoring |
| Risk Treatment | Mitigate, Accept, Avoid, Transfer |
# PII & PHI (Personally Identifiable Information / Protected Health Information)
 🧾 PII vs PHI
[[PII & PHI (Personally Identifiable Information  Protected Health Information)]]

| Category | PII | PHI |
|--------|-----|-----|
| Definition | Identifies a person | Health data linked to person |
| Law | Privacy regulations | HIPAA |
| Examples | Name, ID, Credit Card | Medical records, diagnosis |
| Sensitivity | High | Very High |
| Breach Impact | Legal + Financial | Severe legal penalties |

# Security Operations Center (SOC)
Security Operations Center (SOC)
[[Security Operations Center (SOC)]]

| Aspect | Description |
|------|-------------|
| Purpose | Detect, analyze, respond to threats |
| Scope | Network, endpoints, cloud, apps |
| Core Tools | SIEM, SOAR |
| Key Roles | SOC Analyst, CSIRT |
| Key Goals | Visibility, fast detection, response |
| Challenges | Skills, tools, automation |
| Success Factors | Planning, governance, support |
# PLAYBOOKS, RUNBOOKS, AND RUNBOOK AUTOMATION
[[PLAYBOOKS, RUNBOOKS, AND RUNBOOK AUTOMATION]]
### 📊 جدول مرتب وجميل لـ Obsidian

|العنصر|التعريف|مثال واقعي|الفائدة|
|---|---|---|---|
|**Runbook**|خطوات تشغيلية تفصيلية|معالجة Malware|توحيد التنفيذ|
|**Playbook**|سيناريو استجابة شامل|Incident Response Plan|تنظيم القرار|
|**RBA**|أتمتة الـ Runbook|عزل جهاز تلقائيًا|سرعة + دقة|

---

### 📈 Metrics لقياس الفعالية (مهمة جدًا)

| Metric           | شو تقيس         |
| ---------------- | --------------- |
| MTTR             | سرعة الإصلاح    |
| MTBF             | استقرار الأنظمة |
| Time to Discover | سرعة الاكتشاف   |
| Time to Contain  | سرعة الاحتواء   |
| Automation Level | نضج العمليات    |

# DIGITAL FORENSICS
[[DIGITAL FORENSICS]]


|العنصر|ليش مهم|
|---|---|
|طريقة الجمع|تثبت عدم التلاعب|
|وقت الجمع|ربط زمني للحادثة|
|النقل|منع التبديل أو الضياع|
|التخزين|حماية الدليل|
|الوصول|تحديد المسؤولية|


---


 
