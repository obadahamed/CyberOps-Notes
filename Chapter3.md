# **SUBJECT AND OBJECT DEFINITION**
[[SUBJECT AND OBJECT DEFINITION]]

| المفهوم | التعريف | أمثلة | ملاحظات |
|--------|----------|--------|----------|
| Subject | كيان نشط يطلب الوصول لمورد | مستخدم، متصفح، تطبيق، خدمة | يتصرف بالنيابة عن Principal |
| Object | كيان سلبي يحتوي على المعلومة | ملف، DB، API، خدمة | دوره يعتمد على من يطلب الوصول |
| Access Control | آلية تمنح أو تمنع أو تلغي الوصول | RBAC, ACL, Permissions | يعتمد على صلاحيات الـ Subject تجاه الـ Object |

---
# **Access Control Fundamentals**
[[Access Control Fundamentals]]

| المرحلة | التعريف | أمثلة | ملاحظات |
|--------|---------|--------|----------|
| Identification | تقديم الهوية | Username, ID, Passport | يجب أن تكون فريدة وغير وصفية |
| Authentication | إثبات الهوية | Password, Token, Fingerprint | ثلاث طرق: معرفة، ملكية، خصائص |
| Authorization | تحديد الصلاحيات | Read/Write/Execute | يعتمد على السياسات وNeed to Know |
| Accounting | تسجيل النشاط | Audit Logs | مهم للتحقيقات الأمنية |

# **Access Control Process**
[[Access Control Process]]

| المرحلة | التعريف | أمثلة | ملاحظات |
|--------|---------|--------|----------|
| Asset Classification | تحديد أهمية الأصل | Top Secret, Private | يحدد مستوى الحماية |
| Asset Marking | وضع علامات على الأصل | Watermark, Labels | يجب أن تكون واضحة ومتسقة |
| Access Control Policy | تحديد من يصل وكيف | Data at rest/motion/use | يعتمد على التصنيف |
| Data Disposal | التخلص الآمن من البيانات | Clearing, Purging, Destroying | يمنع استرجاع البيانات |

# **INFORMATION SECURITY ROLES AND RESPONSIBILITIES**
[[INFORMATION SECURITY ROLES ANDRESPONSIBILITIES]]

| الدور | المسؤوليات | أمثلة |
|-------|-------------|--------|
| Executives / Senior Management | المسؤولية النهائية، الموافقة على السياسات | CEO, CIO |
| Data Owner | تصنيف البيانات، تحديد الصلاحيات، مراجعة الوصول | مدير HR |
| Data Custodian | تنفيذ المهام اليومية، ضمان التوفر، تطبيق السياسات | DBA |
| System Owner | حماية الأنظمة، التعاون مع مالك البيانات | IT Manager |
| Security Administrator | منح الصلاحيات، مراقبة الوصول، حفظ السجلات | Access Admin |
| End User | استخدام البيانات والالتزام بالسياسات | موظف HR |
| Security Officer | تصميم وإدارة سياسات الأمن | CISO |
| InfoSec Professional | كتابة المعايير، تقديم الاستشارات | Security Engineer |
| Auditor | التحقق من الالتزام، تقديم تقارير مستقلة | Internal Auditor |


# **Access Control Types**
[[Access Control Types]]

| النوع | التعريف | أمثلة | الهدف |
|-------|----------|--------|--------|
| Administrative | سياسات وإجراءات تدير الوصول | تصنيف المعلومات، تدريب، تدقيق | تنظيم وإدارة الأمن |
| Physical | حماية الحدود المادية | حراس، كاميرات، بوابات | حماية المبنى والأصول |
| Technical | ضوابط تقنية تنفذ السياسات | Firewall, IDS, Encryption | حماية رقمية |
| Preventive | منع الحوادث | Passwords, ACLs | منع الهجوم |
| Deterrent | ردع المهاجم | لافتات تحذير | تخويف المهاجم |
| Detective | كشف الهجمات | Logs, SIEM | اكتشاف الهجوم |
| Corrective | معالجة المشكلة أثناء الهجوم | عزل جهاز | تقليل الضرر |
| Recovery | استعادة الوضع الطبيعي | Backup, DRP | العودة للوضع الطبيعي |
| Compensating | بديل مؤقت | حارس بدل قارئ بطاقة | تقليل المخاطر |

# **Access Control Models**
[[Access Control Models]]

| النموذج | كيف يُتخذ القرار      | المزايا                 | العيوب                      | أمثلة             |
| ------- | --------------------- | ----------------------- | --------------------------- | ----------------- |
| DAC     | المالك يحدد الصلاحيات | مرن وسهل                | ضعف التحكم، Privilege Creep | NTFS, Linux chmod |
| MAC     | النظام يفرض السياسة   | أمان عالي               | غير مرن، صعب الإدارة        | SELinux, Military |
| RBAC    | حسب الدور الوظيفي     | قابلية توسع، إدارة سهلة | Role Explosion              | Active Directory  |
| ABAC    | حسب Attributes        | مرونة عالية             | تعقيد كبير                  | XACML, Cloud IAM  |

# **Access Control Mechanisms**
[[Access Control Mechanisms]]

| الآلية | الفكرة الأساسية | يعتمد على | مثال |
|--------|------------------|-----------|--------|
| ACL | قائمة صلاحيات مرتبطة بالـ Object | Object | NTFS ACLs |
| Capability Table | قائمة صلاحيات مرتبطة بالـ Subject | Subject | User Capability List |
| ACM | مصفوفة تربط Subjects بـ Objects | كلاهما | جدول صلاحيات شامل |
| Restricted Interface | تقييد الخيارات عبر الواجهة | Role/Identity | قوائم المسؤول/الضيف |
| Content-Dependent | القرار يعتمد على محتوى البيانات | Data Content | Database Views |
| Context-Dependent | القرار يعتمد على السياق | Session/Time/Location | Stateful Firewall |


# **Identity and Access Control Implementation**

[[Identity and Access Control Implementation]]

| التقنية | الوظيفة | البروتوكولات/الطبقات | ملاحظات |
|---------|----------|------------------------|----------|
| RADIUS | AAA | UDP 1812/1813 | كلمة المرور فقط مشفرة |
| TACACS+ | AAA | TCP 49 | تشفير كامل، Granular |
| Diameter | AAA متقدم | TCP/SCTP + TLS | Peer-to-peer |
| Port Security | تقييد MAC | Layer 2 | MAC Move Detection |
| 802.1X | مصادقة منفذ | EAP, EAPoL, RADIUS | 4 مراحل |
| Network ACL | فلترة شبكة | L2/L3/L4 | Stateless |
| dACL | ACL ديناميكي | ISE | Per-user |
| SGACL | ACL حسب الدور | TrustSec | يعتمد على SGT |
| VLAN | تقسيم الشبكة | Layer 2 | Private VLANs |
| DMZ | عزل الخدمات | Firewall | Web/Partner Zones |
| TrustSec | Access Control متقدم | SGT + MACSec | Ingress/Egress Enforcement |
| IDS | كشف الهجمات | Promiscuous | Alerts |
| IPS | منع الهجمات | Inline | Blocks |


