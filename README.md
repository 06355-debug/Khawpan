# Trash to Treasure — วิธี deploy

โครงสร้าง
- public/index.html   หน้าเว็บนักเรียน
- public/admin.html   หน้าตรวจ/ตัดคูปองสำหรับครู (/admin.html)
- netlify/functions/api.mjs   หลังบ้าน (สมัคร/ล็อกอิน/สแกน/แลกรางวัล)
- package.json, netlify.toml

ตั้งค่า Netlify → Site settings → Environment variables
- GEMINI_API_KEY   (จำเป็น) คีย์จาก Google AI Studio
- ADMIN_KEY        (จำเป็นถ้าจะใช้ admin.html) รหัสลับของครู ตั้งยาวๆ
- DAILY_TOKEN_LIMIT  (ไม่บังคับ, ค่าเริ่มต้น 20) โทเคนสูงสุดต่อคนต่อวัน
- SCAN_COOLDOWN_MS   (ไม่บังคับ, ค่าเริ่มต้น 8000) เว้นระยะระหว่างสแกน
- GEMINI_MODEL       (ไม่บังคับ, ค่าเริ่มต้น gemini-2.5-flash)

Deploy: เชื่อม GitHub repo กับ Netlify (แนะนำ) หรือใช้ `netlify deploy --prod`
ดู error จริงได้ที่ Netlify → Logs → Functions → api
