# Wachira Interactive Portfolio v12 — Stable Responsive UI

## V12

- แยก stylesheet หลักไปที่ `styles.css`
- รวม responsive rules เป็น Desktop / Tablet / Phone
- แก้หัวข้อภาษาไทยและอังกฤษล้นกรอบหรือตัดบรรทัดผิดตำแหน่ง
- ปรับฉากเปิด เมนู Portfolio, cards, gallery และ viewer ให้รองรับจอ 360–1440px
- เพิ่ม focus styles, dialog semantics, focus trap และคืน focus หลังปิด modal
- ลดการใช้ `!important` จาก 313 จุด เหลือเฉพาะกฎ reduced-motion

รายละเอียดเพิ่มเติมอยู่ใน `V12_CHANGELOG.md`

## Local Gallery

## จุดเปลี่ยนหลัก
v10 ใช้รูปจากเครื่อง/Repository เป็นแหล่งหลัก แทนการ hotlink จาก Google Drive

### ตำแหน่งรูป
- `assets/gallery/Pic/` — รูปทั่วไป/กิจกรรม 134 ไฟล์
- `assets/gallery/certificate/` — เกียรติบัตร 24 ไฟล์

**ใช้ชื่อไฟล์ตาม CSV เดิมทุกตัว ห้ามเปลี่ยนชื่อ**

ตัวอย่าง:
- `assets/gallery/Pic/047-computer-lab-teaching-01.jpg`
- `assets/gallery/certificate/003_Digital_Teacher_Course_2025_Technology (Small).png`

## การทำงาน
1. เว็บโหลด Local Gallery ก่อน
2. ถ้าไฟล์ Local ยังไม่มี จะ fallback ไป Google URL เดิมอัตโนมัติ
3. Card / Slider / Viewer / Photo Archive ใช้ registry เดียวกันทั้งหมด

## หลังวางรูป
ควรมี:
- Pic = 134 ไฟล์
- certificate = 24 ไฟล์
- รวม = 158 ไฟล์

จากนั้น:
```powershell
git add -A
git commit -m "Add local gallery images v10"
git push
```


## V11
Adaptive Desktop / Tablet / Phone layout and frame-engine performance profiles. See `V11_CHANGELOG.md`.
