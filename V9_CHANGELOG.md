# V9 — GitHub Pages Performance Fix

## ปัญหาที่แก้
- GitHub Pages ตอบ 503 บาง frame เมื่อ Canvas Frame Engine ยิง request พร้อมกันจำนวนมาก
- Hero / frame sequence อาจสะดุดหรือแสดงเฟรมใกล้เคียงแทนเมื่อ resource โหลดไม่ทัน

## การปรับ Frame Engine
- จำกัด concurrent image requests: Desktop 4 / Mobile 3
- ลด preload window: Desktop ±4 / Mobile ±5
- preload เน้นทิศทาง Scroll ก่อน
- ตัด preload ซ้ำออกจาก animation loop
- update เฉพาะ scene ที่อยู่ใกล้ viewport
- retry frame ที่โหลดพลาดสูงสุด 2 ครั้ง (220ms / 700ms)
- ลด frame cache เพื่อควบคุม memory
- คง Canvas + WebP frame motion และ UI choreography เดิม

## การใช้งาน
แทนไฟล์ v8 ด้วย v9 แล้ว commit/push ตามปกติ
