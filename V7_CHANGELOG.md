# Version 7 — Mobile Gesture Choreography

## เป้าหมาย
แก้ปัญหา Mobile ที่ตัวละครผายมือไปด้านข้าง แต่ข้อความ/เมนูถูกย้ายไปอยู่ด้านล่างจน gesture ไม่สัมพันธ์กับ UI

## สิ่งที่แก้
- Desktop คง layout และ motion เดิม
- Hero บนมือถือ: ชื่อ WACHIRA UTHAWANG ปรากฏใกล้ปลายมือด้านขวา
- เพิ่ม connector line + anchor dot เพื่อเชื่อม gesture กับข้อความ
- ขยายช่วงเวลาที่ชื่อค้างก่อนเลื่อนออก
- เมนู 5 บทบนมือถือเลื่อนเข้ากึ่งกลางจอหลังตัวละครเริ่มเดินออก แทนการเป็น Bottom Sheet
- เมนู 5 บทยังคงปัดซ้าย/ขวาได้
- Video 3 บนมือถือ: DIGITAL SYSTEMS ปรากฏใกล้ฝ่ามือด้านซ้าย
- ลด white wash บน mobile motion scene เพื่อให้ตัวละครและ anchor เด่นขึ้น
- Closing ไม่มี gesture ชี้ จึงคง card ด้านล่างเพื่อการอ่านที่ชัดเจน

## แนวคิด Layout
Motion scene บน Mobile ใช้ 2 stage:
1. Gesture Anchor — UI ปรากฏในทิศทางที่มือชี้
2. Expand / Center — เมื่อ gesture จบ UI เคลื่อนเข้าสู่ตำแหน่งสำหรับการอ่านและ interaction

## Preview URLs
- `index.html?preview=intro-name`
- `index.html?preview=intro-menu`
- `index.html?preview=return`
- `index.html?preview=closing`
