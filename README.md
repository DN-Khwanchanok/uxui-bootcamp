# Monday Air — Handoff Pack

การบ้าน Tailwind 101: ขึ้นหน้าเว็บ Monday Air ด้วย Tailwind v4 จากไฟล์ design ที่ทีม Design ส่งให้

## ในแพ็กนี้มีอะไร

| ของ | ใช้ทำอะไร |
|---|---|
| ไฟล์ Figma [Monday Air — Handoff](https://www.figma.com/design/aBawsR124C8iPAuBTio2De) | หน้าจอทั้งหมด, component, สถานะของฟอร์ม และ Style Guide |
| `Monday Air - Token List.md` | token ทั้งหมด พร้อมชื่อ CSS variable สำหรับเขียน `@theme` และ class Tailwind ที่ได้ |

## เริ่มยังไง

1. เปิดไฟล์ Figma แล้วอ่าน page **Read Me** ก่อน
2. ดู page **Style Guide** ให้เห็นภาพรวมของสี ตัวอักษร ระยะห่าง มุมโค้ง และเงา
3. กด ▶ **Present** ที่ page **Desktop 1280** (flow "Monday Air — Desktop") เพื่อดูว่ากดปุ่มไหนแล้วไปหน้าไหน
4. เขียน `@theme` และ `@utility` จาก `Monday Air - Token List.md`
5. ขึ้นหน้าเว็บตามหน้าจอใน Figma ทั้ง Desktop 1280 และ iPad 768
6. ดูสถานะ hover / focus / error / disabled ใน page **Form States**
7. ตรวจงานตัวเองด้วย Handoff Checklist ด้านล่างก่อนส่ง

ถ้าดึงข้อมูลจาก Figma ผ่าน MCP ได้: Variable ทุกตัวตั้งชื่อ CSS variable ไว้แล้ว (เช่น `var(--color-primary-500)`) และช่องคำอธิบายของ Text Style คือ class Tailwind ที่ต้องใช้

## ต้องทำแค่ไหน

| ระดับ | หน้า / งาน |
|---|---|
| **ต้องทำ** | 01 หน้าแรก + 02 หน้าบัตรขึ้นเครื่อง · ฟอร์มมีสถานะ hover / focus / error · Desktop + iPad · ไม่ต้องใช้ JavaScript |
| **โบนัสระดับ 1** | 04 หน้าถึงออฟฟิศ (ฟอร์มให้คะแนน + สายพานสัมภาระ) |
| **โบนัสระดับ 2** | 03 หน้ากำลังบิน + 05 เช็กอินเที่ยวกลับ + 02R / 03R + 06 ถึงเตียง · แอนิเมชัน · แสดงชื่อจริงบนบัตร |

- ทำแต่ละหน้าเป็นไฟล์ HTML แยกกัน ใช้ลิงก์ธรรมดาเชื่อมหน้า และฟอร์มเช็กอินส่งไปหน้าบัตรด้วย `<form action="boarding-pass.html">`
- วันส่งงานและวิธีส่ง: ตามที่ mentor แจ้ง

## ขอบเขตของโค้ดเวอร์ชันนี้

- ใช้ HTML และ Tailwind v4 โดยไม่มี JavaScript ทำงานในหน้าเว็บ
- การ์ดเลือกชั้นโดยสารใช้ `<label for="…">` เชื่อมกับ radio ในฟอร์ม
- ฟอร์มใช้ `required`, `type="email"`, `pattern` และ CSS `:user-invalid` ตรวจข้อมูล โดยจังหวะที่เริ่มแสดง error ขึ้นอยู่กับเบราว์เซอร์ จึงอาจต่างจากเว็บตัวอย่างที่ควบคุมด้วย JavaScript
- หน้าบัตรใช้ข้อมูลตัวอย่างคงที่ การแสดงข้อมูลที่กรอกจริงและการเก็บข้อมูลเมื่อย้อนกลับเป็นส่วนที่ยังไม่ได้ทำ
- กรอบ CHECKED IN และตรา BOARDED เป็นส่วนแสดงผลของหน้าบัตร ไม่ได้ยืนยันการจองกับระบบภายนอก

## Handoff Checklist (ใช้ตรวจงาน)

- [ ] สี มุมโค้ง เงา ฟอนต์ มาจาก token ทั้งหมด
- [ ] ไม่มี hex และไม่มี `[ค่าที่ตั้งเอง]` ใน class
- [ ] Responsive ตาม Desktop / iPad ในไฟล์ Figma
- [ ] ปุ่มและช่องกรอกมี hover / focus ที่มองเห็นชัด (ดู page Form States)
- [ ] ช่องกรอกทุกช่องมี `<label>` และข้อความ error ผูกกับช่อง (`aria-describedby`)
- [ ] บรรทัดแรกของทุกไฟล์เป็น `<!doctype html>`
- [ ] ใช้ semantic tag: `header` · `nav` · `main` · `footer`
- [ ] โค้ดจัด indent อ่านง่าย
