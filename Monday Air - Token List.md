# Monday Air - Token List

> รายการ token ทั้งหมดของ Monday Air สำหรับขึ้นงานด้วย Tailwind v4
> - ไฟล์ Figma: [Monday Air — Handoff](https://www.figma.com/design/aBawsR124C8iPAuBTio2De) (ดูตัวอย่างจริงใน page **Style Guide**)
> - ค่าทุกตัวตรงกับ Variables / Text Styles / Effect Styles ในไฟล์ Figma
> - วิธีอ่านตาราง: **ชื่อใน Figma → CSS variable ที่ต้องใส่ใน `@theme` → class Tailwind ที่ได้**

## กติกาก่อนเริ่ม
- เขียน `@theme` เองจากตารางนี้ ใช้ชื่อ CSS variable ตามคอลัมน์ "CSS variable" ทุกตัว แล้ว Tailwind จะสร้าง class ให้เอง เช่น `--color-primary-500` → `bg-primary-500`, `--radius-card` → `rounded-card`
- ใส่ `--color-*: initial;` เป็นบรรทัดแรกใน `@theme` เพื่อล้างสีเดิมของ Tailwind ทิ้ง จะได้ใช้ได้**เฉพาะสีในตารางนี้** (`bg-blue-500` จะใช้ไม่ได้)
- ห้ามใช้ hex และห้ามใช้ค่าที่ตั้งเองในวงเล็บ `[ ]` ใน class- ถ้าดึงข้อมูลจาก Figma ผ่าน MCP: Variable ทุกตัวตั้ง code syntax เป็น CSS variable ไว้แล้ว (เช่น `var(--color-primary-500)`) และช่องคำอธิบายของ Text Style คือ class Tailwind ที่ต้องใช้

## 1. Color

| Figma Variable | ค่า | CSS variable | ใช้ทำอะไร |
|---|---|---|---|
| `color/primary/50` | `#F6FDE3` | `--color-primary-50` | สำรอง ยังไม่ใช้ในหน้าจอ |
| `color/primary/100` | `#EAFBB8` | `--color-primary-100` | สำรอง ยังไม่ใช้ในหน้าจอ |
| `color/primary/500` | `#C6F432` | `--color-primary-500` | สีเน้นหลัก ปุ่ม ชิป |
| `color/primary/600` | `#B2DE1C` | `--color-primary-600` | ปุ่มตอน hover |
| `color/primary/700` | `#97BF0C` | `--color-primary-700` | ปุ่มตอนกด (pressed) |
| `color/neutral/0` | `#FFFFFF` | `--color-neutral-0` | พื้นการ์ด |
| `color/neutral/50` | `#EEEDE8` | `--color-neutral-50` | พื้นหน้า |
| `color/neutral/200` | `#D6D5CE` | `--color-neutral-200` | เส้นขอบ ปุ่ม disabled |
| `color/neutral/500` | `#66655F` | `--color-neutral-500` | ข้อความรอง |
| `color/neutral/900` | `#111111` | `--color-neutral-900` | ข้อความหลัก บล็อกดำ |
| `color/danger/50` | `#FEF2F2` | `--color-danger-50` | พื้นช่องกรอกที่ผิด |
| `color/danger/600` | `#DC2626` | `--color-danger-600` | ข้อความ error ชิป "ดีเลย์" |

**วิธีใช้เป็น class:** เติมชื่อสีหลัง `bg-` `text-` `border-` `outline-` เช่น `bg-primary-500` · `text-neutral-500` · `border-neutral-200`

> [!warning] กติกาสีเขียวมะนาว
> ห้ามใช้ `primary-500` เป็น**ตัวอักษรบนพื้นขาว** (contrast ต่ำมาก อ่านไม่ออก) ใช้ได้เป็น**พื้น**ที่มีตัวอักษรดำ หรือเป็นตัวอักษรบน**พื้นดำ**เท่านั้น

## 2. Font

| Figma Variable | ฟอนต์ | class | CSS variable |
|---|---|---|---|
| `font/display` | Outfit (ภาษาไทยใช้ IBM Plex Sans Thai แทน) | `font-display` | `--font-display` |
| `font/body` | IBM Plex Sans Thai | `font-body` | `--font-body` |

โหลดจาก Google Fonts ทั้งสองตัว

## 3. Text Styles

ชื่อ Text Style ใน Figma อ่านแบบนี้: **ฟอนต์ / ขนาด / น้ำหนัก-ระยะห่างตัวอักษร** เช่น `display/sm/semibold-widest` = `font-display text-sm font-semibold tracking-widest`

### ขนาดตัวอักษร (token)
| class | ขนาด / ความสูงบรรทัด | CSS variable |
|---|---|---|
| `text-sm` | 14 / 20px | `--text-sm` + `--text-sm--line-height` |
| `text-base` | 16 / 24px | `--text-base` + `--text-base--line-height` |
| `text-lg` | 20 / 28px | `--text-lg` + `--text-lg--line-height` |
| `text-xl` | 24 / 32px | `--text-xl` + `--text-xl--line-height` |
| `text-2xl` | 32 / 40px | `--text-2xl` + `--text-2xl--line-height` |
| `text-3xl` | 48 / 52px | `--text-3xl` + `--text-3xl--line-height` |
| `text-display` | ยืดตามจอ `clamp(4.5rem, 15vw, 12rem)` → 115.2px ที่จอ 768 · 192px ที่จอ 1280 · ความสูงบรรทัด 0.85 | `--text-display` + `--text-display--line-height` |

> [!note] ขนาดของ Monday Air ไม่ใช่ค่าเดิมของ Tailwind
> เช่น `text-2xl` ของ Tailwind ปกติคือ 24px แต่ของ Monday Air คือ 32px ให้ดูจากตารางนี้เสมอ

### Display (Outfit)
| Figma Text Style | class Tailwind |
|---|---|
| `display/sm/regular` | `font-display text-sm font-normal` |
| `display/sm/regular-widest` | `font-display text-sm font-normal tracking-widest` |
| `display/sm/semibold` | `font-display text-sm font-semibold` |
| `display/sm/semibold-widest` | `font-display text-sm font-semibold tracking-widest` |
| `display/sm/bold` | `font-display text-sm font-bold` |
| `display/sm/bold-widest` | `font-display text-sm font-bold tracking-widest` |
| `display/base/bold` | `font-display text-base font-bold` |
| `display/lg/regular` | `font-display text-lg font-normal` |
| `display/lg/bold` | `font-display text-lg font-bold` |
| `display/lg/bold-wide` | `font-display text-lg font-bold tracking-wide` |
| `display/lg/extrabold` | `font-display text-lg font-extrabold` |
| `display/xl/semibold` | `font-display text-xl font-semibold` |
| `display/xl/bold` | `font-display text-xl font-bold` |
| `display/2xl/bold` | `font-display text-2xl font-bold` |
| `display/2xl/extrabold-widest` | `font-display text-2xl font-extrabold tracking-widest` |
| `display/3xl/bold` | `font-display text-3xl font-bold` |
| `display/3xl/extrabold` | `font-display text-3xl font-extrabold` |
| `display/display-ipad/extrabold` · `display-desktop/extrabold` | `font-display text-display font-extrabold` |
| `display/display-ipad/extrabold-tight` · `display-desktop/extrabold-tight` | `font-display text-display font-extrabold tracking-tight` |

`display-ipad` กับ `display-desktop` ในโค้ดคือ class เดียวกัน (`text-display`) Figma แยกเป็นสองตัวเพราะยืดตามจอไม่ได้

### Body (IBM Plex Sans Thai)
| Figma Text Style | class Tailwind |
|---|---|
| `body/sm/regular` | `font-body text-sm font-normal` |
| `body/sm/medium` | `font-body text-sm font-medium` |
| `body/sm/semibold` | `font-body text-sm font-semibold` |
| `body/base/regular` | `font-body text-base font-normal` |
| `body/base/regular-input` | `font-body text-base font-normal` (ใช้ในช่องกรอก ความสูงบรรทัดตามค่าปกติของ browser) |
| `body/base/semibold` | `font-body text-base font-semibold` |
| `body/base/bold` | `font-body text-base font-bold` |
| `body/lg/regular` | `font-body text-lg font-normal` |
| `body/lg/semibold` | `font-body text-lg font-semibold` |
| `body/xl/bold` | `font-body text-xl font-bold` |
| `body/3xl/bold` | `font-body text-3xl font-bold` |

## 4. Spacing

ใช้ขั้นเดิมของ Tailwind (ขั้นละ 4px) ใน Figma ผูก padding และ gap ทุกจุดกับ Variable `spacing/*` แล้ว

| Figma Variable | ค่า | class |
|---|---|---|
| `spacing/1` | 4px | `p-1` `m-1` `gap-1` |
| `spacing/2` | 8px | `p-2` `m-2` `gap-2` |
| `spacing/3` | 12px | `p-3` `m-3` `gap-3` |
| `spacing/4` | 16px | `p-4` `m-4` `gap-4` |
| `spacing/5` | 20px | `p-5` `m-5` `gap-5` |
| `spacing/6` | 24px | `p-6` `m-6` `gap-6` |
| `spacing/8` | 32px | `p-8` `m-8` `gap-8` |
| `spacing/10` | 40px | `p-10` `m-10` `gap-10` |
| `spacing/12` | 48px | `p-12` `m-12` `gap-12` |
| `spacing/16` | 64px | `p-16` `m-16` `gap-16` |
| `spacing/20` | 80px | `p-20` `m-20` `gap-20` |
| `spacing/24` | 96px | `p-24` `m-24` `gap-24` |

ใช้ได้กับทุกทิศ เช่น `px-4` `py-2` `mt-6`

## 5. Radius

| Figma | ค่า | CSS variable | class | ใช้กับ |
|---|---|---|---|---|
| `radius/control` | 12px | `--radius-control` | `rounded-control` | ช่องกรอก การ์ดเลือกชั้นโดยสาร |
| `radius/card` | 24px | `--radius-card` | `rounded-card` | การ์ด |
| — | เต็มวง | (ค่าเดิมของ Tailwind) | `rounded-full` | ปุ่ม ชิป |

## 6. Shadow / Focus

| Figma | ค่า | CSS variable | class | ใช้กับ |
|---|---|---|---|---|
| Effect Style `shadow/card-hover` | `0 12px 32px` สี `#111111` 14% | `--shadow-card-hover` | `hover:shadow-card-hover` | การ์ดชั้นโดยสารตอน hover |
| — (ไม่มีใน Figma) | `0 1px 2px` สี `#111111` 6% | `--shadow-card` | `shadow-card` | สำรอง ยังไม่ใช้ในหน้าจอ |
| Effect Style `focus/ring` | ช่องว่าง 2px + เส้นดำ 2px | (ไม่ต้องสร้าง ใช้ class outline) | `focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-neutral-900` | วงโฟกัสบนพื้นสว่าง |

บนพื้นดำ วงโฟกัสใช้ `outline-primary-500` หรือ `outline-neutral-0` แทน `outline-neutral-900` (สีดำจะมองไม่เห็นบนพื้นดำ)

## 7. Layout

| Figma | ค่า | class | หมายเหตุ |
|---|---|---|---|
| `container/page` | 1200px | `max-w-page` | CSS variable `--container-page` · ความกว้างสูงสุดของเนื้อหา ใช้คู่กับ `mx-auto` |
| — | ระยะขอบซ้ายขวาของหน้า | `page-x` | custom utility (ดูข้อ 9) |
| Breakpoint | 640 / 768 / 1024px | `sm:` / `md:` / `lg:` | ค่าเดิมของ Tailwind · Figma มีหน้าจอ iPad 768 และ Desktop 1280 |

## 8. Animation (ยังไม่มีใน Figma ดูการเคลื่อนไหวจริงจากหน้าตัวอย่างที่เปิดให้ดู)

ตั้งชื่อเป็น `--animate-ชื่อ` ใน `@theme` แล้วจะได้ class `animate-ชื่อ` · "นุ่ม" ในตาราง = `cubic-bezier(0.2, 0.8, 0.2, 1)`

| class | ใช้ทำอะไร | เวลา |
|---|---|---|
| `animate-fly` | เครื่องบินเลื่อนบนเส้นทาง วนไม่หยุด | 6s ease-in-out |
| `animate-flip` | เวลาบนกระดาน Departures พลิก | 0.6s นุ่ม |
| `animate-rise` | เลื่อนขึ้นตอนโหลด | 0.6s นุ่ม |
| `animate-slide-l` · `animate-slide-r` | รหัสสนามบินเลื่อนเข้าจากซ้าย / ขวา | 0.7s นุ่ม |
| `animate-scan` | แถบสแกนบาร์โค้ด | 1.4s ease-in-out หน่วง 0.5s |
| `animate-takeoff` | เครื่องบินขึ้น | 1.4s ease-in |
| `animate-runway` | ไฟรันเวย์ / สายพานวิ่ง วนไม่หยุด | 0.4s linear |
| `animate-pop` | ข้อความเด้งขึ้น | 0.5s นุ่ม |
| `animate-stamp` | ตราประทับ BOARDED | 0.5s นุ่ม หน่วง 0.6s |
| `animate-progress` · `animate-progress-fill` | เครื่องบินและแถบความคืบหน้าระหว่างบิน | 6s linear |
| `animate-appear` | ค่อยๆ ปรากฏ | 0.6s ease-out |
| `animate-shake` | ช่องกรอกที่ผิดสั่น | 0.35s ease-in-out |

ใช้ผ่าน `motion-safe:` ทุกครั้ง เช่น `motion-safe:animate-rise` เครื่องที่ตั้งค่าลดการเคลื่อนไหวจะไม่เห็นแอนิเมชัน

## 9. Custom Utilities (ต้องสร้างเอง)

ของที่ Tailwind ไม่มีให้ สร้างด้วย `@utility` ครั้งเดียวแล้วใช้เหมือน class ปกติ ตารางนี้บอกว่าแต่ละตัวต้องได้หน้าตาแบบไหน

| class | ใช้ทำอะไร | หน้าตาที่ต้องได้ |
|---|---|---|
| `page-x` | ระยะขอบซ้ายขวาของหน้า | padding ซ้ายขวาอย่างน้อย 16px และไม่น้อยกว่าพื้นที่รอยบากจอ (`env(safe-area-inset-left/right)`) |
| `dots` | เส้นประของเส้นทางบิน | จุดกลมขนาด 3px ห่างกันทุก 12px เรียงแถวเดียวตรงกลางความสูง สีตามสีตัวอักษร (`currentColor`) |
| `barcode` | ลายบาร์โค้ดบนบัตร | แท่งสี `neutral-900` กว้าง 3 · 1 · 4 · 1px เว้น 2 · 3 · 2 · 3px วนซ้ำทุก 19px (ดูใน Figma หน้า 02) |
| `runway` | ไฟรันเวย์ / สายพาน | ขีดสี `primary-500` ยาว 16px เว้น 16px สูง 4px |
| `animate-delay-*` | หน่วงเวลาแอนิเมชัน | ตัวเลขเป็นมิลลิวินาที เช่น `animate-delay-120` = 120ms |
| `animate-stagger` | หน่วงเวลาไล่ลำดับ | หน่วง 200ms × ลำดับที่ (ตัวแปร `--i`) ใช้กับสายพานสัมภาระ |

## 10. อื่นๆ ที่ไม่ใช่ token
- **ไอคอนเครื่องบิน** เป็นตัวอักษร `✈` พิมพ์ลงใน HTML ได้เลย สีตาม `text-…` ใส่ `aria-hidden="true"` ถ้าเป็นแค่ของตกแต่ง
- **เส้นประเส้นทางบิน** ใน Figma คือ layer `Route Dots` (จุดกลม 3px ห่างกัน 12px สี `neutral-500`) เวลาเขียนโค้ดให้ใช้ class `dots` ที่สร้างเองตามข้อ 9 ไม่ต้องวาดเป็นรูป
