# Version 8 — External Image Reliability

## เปลี่ยนแปลงหลัก
- อ่านลิงก์รูป 158 รายการใหม่จากไฟล์ Markdown ที่ผู้ใช้ให้มาโดยตรง
- ใช้ `https://lh5.googleusercontent.com/d/FILE_ID` เป็น Primary URL ตามข้อมูลต้นฉบับ
- เพิ่ม fallback อัตโนมัติ 2 ชั้นสำหรับ GitHub Pages:
  1. `https://lh3.googleusercontent.com/d/FILE_ID=s1600?authuser=0`
  2. `https://drive.google.com/thumbnail?id=FILE_ID&sz=w1600`
- เพิ่ม `referrerpolicy="no-referrer"` สำหรับรูปภายนอก
- ใช้ loader เดียวกันใน Chapter Cards, Hero Menu, Content Strips, System screenshots และ Photo Archive
- Viewer รูปใหญ่รองรับ fallback เดียวกัน

## หลังอัปขึ้น GitHub
แทนไฟล์ v7 ด้วย v8 แล้วรัน:

```bash
git add .
git commit -m "Fix portfolio image links v8"
git push
```

GitHub Pages จะอัปเดตจาก branch main โดยอัตโนมัติ
