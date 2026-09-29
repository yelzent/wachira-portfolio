# Wachira Portfolio v13 — Performance Rebuild Patch

แพตช์นี้ทำจาก v12.1 โดยแก้เฉพาะระบบ Motion/Frame Engine และชุดเฟรม ไม่แตะเนื้อหา Gallery, Portfolio, styles.css หรือ sheet-images.js

## ไฟล์ที่ต้องนำไปวาง

คัดลอกไฟล์/โฟลเดอร์จาก ZIP ไปทับ/เพิ่มในโฟลเดอร์ WebPort:

- `index.html` → ทับ `WebPort/index.html`
- `data/frame-manifest-v13.js` → เพิ่มใน `WebPort/data/`
- `assets/frames-v13/` → เพิ่มทั้งโฟลเดอร์ใน `WebPort/assets/`

ไม่ต้องลบ `assets/frames/` เดิมในรอบทดสอบแรก เพื่อให้ rollback ได้ง่าย

## ชุดเฟรมใหม่

| Device | Intro | Return | Closing | Resolution | Approx size |
|---|---:|---:|---:|---|---:|
| Phone | 150 | 68 | 72 | 720×405 | 2.2 MB |
| Tablet | 187 | 86 | 90 | 960×540 | 4.0 MB |
| Desktop | 224 | 103 | 108 | 1280×720 | 6.2 MB |

เดิมทุกอุปกรณ์ใช้ Intro 299 + Return 137 + Closing 144 = 580 frames ต่อชุด

## Engine v13

- ใช้ asset คนละชุดจริงตาม Phone / Tablet / Desktop
- โหลด compressed WebP ของชุดอุปกรณ์นั้นก่อนเข้าเว็บ
- decode เฉพาะเฟรมใกล้ตำแหน่งปัจจุบัน
- ใช้ `createImageBitmap()` เมื่อ browser รองรับ
- rolling decoded cache จำกัด RAM
- ปิด ImageBitmap (`close()`) เมื่อถูก evict
- ถ้า target frame decode พร้อมแล้ว จะ scrub ไปเฟรมนั้นทันที
- ถ้ายังไม่พร้อม ใช้ Fast Follow + nearest decoded frame ชั่วคราว
- ลด Canvas DPR และ image smoothing cost
- ป้องกัน resize จาก mobile browser address bar แบบเดิม

## Git

```powershell
cd C:\Users\Muenfun\Desktop\WebPort
git add -A
git commit -m "Test v13 performance rebuild"
git push
```

## วิธีทดสอบ

1. เปิดเว็บและปล่อย Loader ถึง 100%
2. Scroll Hero ช้า ๆ 1 รอบ
3. Scroll Hero เร็ว ๆ 1 รอบ
4. กลับขึ้นด้านบนแล้วทดสอบรอบสอง
5. ทดสอบ Return และ Closing
6. ทดสอบทั้ง Phone / Tablet / Desktop

ถ้า v13 ลื่นกว่าชัดเจน ค่อยลบ `assets/frames/` เก่าเพื่อลดขนาด repository ใน commit ถัดไป
