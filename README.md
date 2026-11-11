# Git Reference — คู่มือคำสั่ง Git & การทำงานเป็นทีม

เว็บไซต์ Cheatsheet สรุปคำสั่ง Git และแนวทางการทำงานร่วมกันผ่าน 1 Repository (Branch + Pull Request workflow) ออกแบบด้วยธีมสีอบอุ่นถนอมสายตา รองรับทุกขนาดหน้าจอ

## ฟีเจอร์

- **คลังคำสั่ง Git 21 คำสั่ง** แบ่งเป็น 4 หมวด
  - โฟลว์พื้นฐาน (`init`, `clone`, `status`, `add`, `commit`, `fetch`)
  - ทำงานร่วมกัน & Branch (`branch`, `checkout -b`, `switch`, `pull`, `push`, `stash`)
  - แก้ Merge Conflict (`merge`, `merge --abort`)
  - ย้อนเวอร์ชัน & Undo (`log`, `restore`, `amend`, `reset`, `revert`)
- **ค้นหาคำสั่ง** แบบทันที รองรับทั้งชื่อคำสั่ง คำอธิบาย และแท็กภาษาไทย
- **กรองตามหมวดหมู่** ผ่านปุ่ม Filter Chips
- **คัดลอกคำสั่งได้ในคลิกเดียว** พร้อม Toast แจ้งเตือน
- **Workflow 4 ขั้นตอน** สำหรับทำงานร่วมกันในทีม (Pull → Branch → Push → Pull Request)
- **ตัวอย่างการอ่าน Merge Conflict** พร้อมไฮไลต์ `<<<<<<<`, `=======`, `>>>>>>>` แบบ Visualizer
- **Responsive Design** รองรับตั้งแต่มือถือจนถึงจอใหญ่ พร้อมปุ่มค้นหาแบบ Mobile
- **ดีไซน์ถนอมสายตา** ธีมสี Cream/Terracotta พร้อม Animated Background Blobs

## เทคโนโลยีที่ใช้

- HTML / CSS / JavaScript (Vanilla — ไม่ต้อง Build)
- [Tailwind CSS](https://tailwindcss.com/) (ผ่าน CDN)
- [Lucide Icons](https://lucide.dev/)
- Google Fonts: [Kanit](https://fonts.google.com/specimen/Kanit) & [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)

## วิธีใช้งาน

เป็นเว็บเพจเดียว (Single Page) ไม่ต้องติดตั้งอะไรเพิ่ม:

1. Clone โปรเจกต์
   ```bash
   git clone https://github.com/ChanodomOngkulna/TestGithubCM.git
   ```
2. เปิดไฟล์ `index.html` ในเบราว์เซอร์ หรือรัน Local Server เช่น
   ```bash
   npx serve .
   # หรือ
   python3 -m http.server 8000
   ```
3. หากเปิดผ่าน GitHub Pages สามารถเข้าถึงได้จากหน้า Settings → Pages ของ Repository

> หมายเหตุ: ฟีเจอร์คัดลอกคำสั่ง (Clipboard API) ต้องเปิดผ่าน `https://` หรือ `localhost` เท่านั้น หากเปิดไฟล์ตรง ๆ ระบบจะใช้วิธี Fallback แทน

## โครงสร้างโปรเจกต์

```
testgithub/
├── index.html   # ไฟล์หลัก (HTML + CSS + JavaScript ทั้งหมด)
└── README.md
```

## โครงสร้างโค้ดใน index.html

- `gitCommands` — อาร์เรย์ข้อมูลคำสั่งทั้งหมด (หมวดหมู่, คำสั่ง, คำอธิบาย, แท็กสำหรับค้นหา) เพิ่มคำสั่งใหม่ได้โดยแก้ไขส่วนนี้
- `renderCards()` — ฟังก์ชันสร้างการ์ดคำสั่ง พร้อมตรรกะกรองตามหมวดหมู่และคำค้นหา
- `copyToClipboard()` / `showToast()` — ระบบคัดลอกคำสั่งและแจ้งเตือน
- Event Listeners — จัดการปุ่มค้นหาบนมือถือ, ช่องค้นหา และปุ่มกรองหมวดหมู่

## การมีส่วนร่วม (Contributing)

ยึดหลักการเดียวกับคู่มือในเว็บ: **ไม่ Push งานเข้า `main` โดยตรง**

1. `git pull origin main`
2. `git checkout -b feature/name`
3. Commit และ `git push -u origin feature/name`
4. เปิด Pull Request ให้ทีมรีวิวก่อน Merge

## License

© Git Command Reference & Teamwork Guide
