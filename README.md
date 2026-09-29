# Smart Home Service Co., Ltd. - Official Verification Website

เว็บไซต์ทางการสำหรับยืนยันตัวตนองค์กร (Organization Verification) บน **Google Play Console**
สำหรับ **Smart Home Service Co., Ltd. (บริษัท สมาร์ท โฮม เซอร์วิส จำกัด)**

---

## 📁 โครงสร้างไฟล์ (File Structure)

```text
smart-home-service-web/
├── index.html            # หน้าหลัก: แสดงข้อมูลนิติบุคคล, โปรไฟล์บริษัท, แอปพลิเคชัน, ข้อมูลติดต่อ
├── privacy-policy.html   # Privacy Policy ที่สอดคล้องกับ Google Play Policy & PDPA
├── terms-of-service.html # Terms of Service (ข้อกำหนดการใช้งาน)
├── delete-account.html   # Account & Data Deletion URL (ข้อบังคับใหม่ของ Google Play)
├── support.html          # หน้า Help Desk / Customer Support
└── README.md             # คู่มือการแก้ไขข้อมูลและวิธี Deploy
```

---

## 📝 จุดที่ต้องใส่ข้อมูลจริงก่อนส่งตรวจ (Placeholders Checklist)

ค้นหาและแทนที่ข้อความในวงเล็บก้ามปู `[...]` ในไฟล์ HTML ทั้งหมด:

1. **D-U-N-S Number**: เลข 9 หลักจาก Dun & Bradstreet ที่ใช้สมัคร Google Play Console (เช่น `[XXXXXXXXX]`)
2. **Tax ID / DBD Reg No.**: เลขทะเบียนนิติบุคคล 13 หลักของกรมพัฒนาธุรกิจการค้า (เช่น `01055XXXXXXXX`)
3. **Registered Address**: ที่อยู่จดทะเบียนภาษาไทยและอังกฤษ (ต้องตรงกับข้อมูลในระบบ D&B และ ภ.พ.20)
4. **Domain & Email**:
   - `yourdomain.com` ➔ โดเมนจริงของคุณ (เช่น `smarthomeservice.co.th`)
   - `contact@yourdomain.com` ➔ อีเมลติดต่อทั่วไป
   - `support@yourdomain.com` ➔ อีเมลซัพพอร์ต (ต้องรับส่งเมลได้จริง Google จะส่งรหัสยืนยัน)
5. **App Package Name**:
   - เปลี่ยนชื่อแพ็กเกจ เช่น `com.smarthome.service.connect` ให้ตรงกับแอปจริงที่จะปล่อย

---

## 🚀 ทดสอบเปิดดูในเครื่อง (Local Preview)

รันคำสั่งเปิด Local Web Server:

```bash
cd smart-home-service-web
python3 -m http.server 8080
```

เปิด Browser ไปที่: [http://localhost:8080](http://localhost:8080)

---

## 🌐 ตัวเลือกการ Deploy ขึ้นออนไลน์ (ใช้งานฟรีและรองรับ HTTPS)

Google Play Console บังคับว่าเว็บไซต์ต้องเป็น **HTTPS**:

### วิธีที่ 1: Cloudflare Pages (แนะนำ - ฟรีและเร็วที่สุด)
1. นำโฟลเดอร์นี้อัปขึ้น GitHub Repo
2. ต่อกับ [Cloudflare Pages](https://pages.cloudflare.com/) ➔ Deploy
3. ผูก Custom Domain ของบริษัทได้ฟรี พร้อม SSL อัตโนมัติ

### วิธีที่ 2: GitHub Pages
1. Push ขึ้น GitHub Repo
2. ไปที่ Settings > Pages > เลือก Source เป็น `main` branch / root
3. ตั้งค่า Custom Domain

### วิธีที่ 3: Vercel / Netlify
- ลากโฟลเดอร์ `smart-home-service-web` วางบนแดชบอร์ด Vercel หรือ Netlify เพื่อรับลิงก์ใช้งานทันที

---

## 🛡️ Checklist การกรอกข้อมูลบน Google Play Console

| ช่องที่ Google Play Console ถาม | ค่าที่ต้องนำไปกรอก |
|---|---|
| **Developer name** | Smart Home Service Co., Ltd. |
| **Legal name** | Smart Home Service Co., Ltd. |
| **D-U-N-S number** | เลข 9 หลักที่ตรงกับเว็บไซต์ |
| **Official website** | `https://www.yourdomain.com` |
| **Contact email address** | `contact@yourdomain.com` (ควรใช้อีเมลโดเมนเดียวกับเว็บ) |
| **Privacy policy URL** | `https://www.yourdomain.com/privacy-policy.html` |
| **App support email** | `support@yourdomain.com` |
| **App support website** | `https://www.yourdomain.com/support.html` |
| **Account deletion URL** | `https://www.yourdomain.com/delete-account.html` |
