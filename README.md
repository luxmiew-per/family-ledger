# Family Ledger — Website Export

รีโพซิทอรีนี้เป็นไฟล์ **frontend ที่ดึงจากเว็บไซต์ที่เผยแพร่สาธารณะ** เมื่อวันที่ 22 สิงหาคม 2026 จาก [geminifam-vfelwki5.manus.space](https://geminifam-vfelwki5.manus.space/)

## วิธีเปิดใช้งาน

สามารถเปิด `index.html` ผ่าน static hosting ได้ เช่น GitHub Pages, Netlify หรือบริการ static hosting อื่น ๆ โดยคงโฟลเดอร์ `public/assets/` ไว้ตามเดิม หากเปิดด้วยไฟล์ `file://` โดยตรง เบราว์เซอร์บางรุ่นอาจจำกัดการโหลด module หรือทรัพยากรบางรายการ ควรใช้ static server แทน

ตัวอย่างการรันในเครื่อง:

```bash
python3 -m http.server 8080
```

จากนั้นเปิด `http://localhost:8080/`

## ขอบเขตของการย้ายข้อมูล

ไฟล์ที่รวมไว้คือ HTML ที่เผยแพร่จริง, JavaScript bundle และ CSS ที่เว็บไซต์อ้างอิงโดยตรง ไฟล์เหล่านี้เป็น **ไฟล์ build/minified** ไม่ใช่ซอร์สโค้ดต้นฉบับที่ใช้พัฒนาแอป

เว็บไซต์มีส่วนติดต่อกับระบบ backend/API และหน้าเข้าสู่ระบบผู้ดูแล ดังนั้นข้อมูลฐานข้อมูล บัญชีผู้ใช้ รหัสผ่าน คีย์ลับ environment variables ระบบ authentication และ backend ที่อยู่ฝั่งเซิร์ฟเวอร์ **ไม่สามารถดึงออกจาก URL สาธารณะได้** และไม่ได้ถูกนำมาใส่ในรีโพซิทอรีนี้

หากต้องการย้ายโปรเจกต์ให้แก้ไขต่อได้ครบทั้ง frontend และ backend จำเป็นต้องมีไฟล์โปรเจกต์ต้นฉบับหรือสิทธิ์เข้าถึงโปรเจกต์ต้นทางโดยตรง

## ไฟล์หลัก

| ไฟล์ | รายละเอียด |
|---|---|
| `index.html` | หน้า HTML ที่เผยแพร่จริง |
| `public/assets/index-CIBQB7Ba.js` | JavaScript production bundle |
| `public/assets/index-DnL4pkPa.css` | CSS production bundle |
| `headers.txt` | HTTP headers ที่บันทึกระหว่างการดึงไฟล์ |

## ความปลอดภัย

ไม่ควร commit credentials, access tokens, cookies, ฐานข้อมูล หรือไฟล์ `.env` ลงในรีโพซิทอรี หากได้รับซอร์สต้นฉบับเพิ่มเติม ควรตรวจสอบ secret และสร้าง credentials ใหม่ก่อนเผยแพร่หรือแชร์รีโพซิทอรี
