# V10 CHANGELOG

- เปลี่ยน Primary image source เป็น Local Gallery
- ใช้ชื่อไฟล์จาก `Port2026 - PicLink(2).csv` ตรง 158/158 รายการ
- Local paths:
  - `assets/gallery/Pic/<File Name>`
  - `assets/gallery/certificate/<File Name>`
- เก็บ Google URLs เดิมเป็น fallback 3 ชั้น
- Viewer รูปใหญ่รองรับ fallback เช่นเดียวกับ Card/Slider
- เพิ่ม `.gitkeep` เพื่อให้ Git เก็บโฟลเดอร์ gallery แม้ยังไม่มีรูป
- คัดลอก CSV ล่าสุดไว้ที่ `data/Port2026-PicLink.csv`
