# การส่งงานผ่าน GitHub Pull Request

## คำแนะนำสำหรับนักศึกษา

### ขั้นตอนที่ 1: Fork Repository
1. ไปที่ GitHub repository ของการทดลอง
2. คลิกปุ่ม "Fork" ที่มุมขวาบน
3. เลือกบัญชี GitHub ของตนเองเป็นปลายทาง

### ขั้นตอนที่ 2: Clone และตั้งค่า
```bash
# Clone repository ที่ fork มา
git clone https://github.com/YOUR_USERNAME/lab-04-esp32-docker-qemu.git
cd lab-04-esp32-docker-qemu

# ตั้งค่า upstream (repository หลัก)
git remote add upstream https://github.com/SPECIAL-TOPICS-COMPUTER-THURSDAY/lab-04-esp32-docker-qemu.git

# ตรวจสอบ remote
git remote -v
```

### ขั้นตอนที่ 3: สร้าง Branch สำหรับงาน
```bash
# สร้าง branch ใหม่
git checkout -b submission/studentID-name

# ตัวอย่าง
git checkout -b submission/65123456-john-doe
```

### ขั้นตอนที่ 4: เตรียมไฟล์งาน
```bash
# สร้างโฟลเดอร์ส่วนตัว
mkdir submissions/65123456-john-doe
cd submissions/65123456-john-doe

# คัดลอกโครงสร้างจาก example
cp -r ../example-submission/* .

# แก้ไขไฟล์ให้ตรงกับงานของตนเอง
```

### ขั้นตอนที่ 5: เพิ่มไฟล์งาน
ใส่ไฟล์ดังนี้ในโฟลเดอร์ `submissions/studentID-name/`:

1. **README.md** - สรุปการทำงาน
2. **report.pdf** - รายงานการทดลอง
3. **screenshots/** - รูปภาพหน้าจอ
4. **code/** - โค้ดโปรแกรม
5. **video_demo.mp4** - วิดีโอสาธิต

### ขั้นตอนที่ 6: Commit และ Push
```bash
# เพิ่มไฟล์ทั้งหมด
git add .

# Commit
git commit -m "Add lab submission for 65123456 - John Doe

- Complete Docker environment setup
- Working ESP32 hello world program
- QEMU simulation successful
- GDB debugging demonstrated
- Complete documentation and video demo"

# Push ไปยัง repository ของตนเอง
git push origin submission/65123456-john-doe
```

### ขั้นตอนที่ 7: สร้าง Pull Request
1. ไปที่ GitHub repository ของตนเอง
2. จะเห็นแจ้งเตือน "Compare & pull request"
3. คลิกปุ่มนี้
4. เลือก base repository เป็น repository หลัก
5. เลือก base branch เป็น `main`
6. เลือก compare branch เป็น `submission/studentID-name`

### ขั้นตอนที่ 8: เขียน Pull Request
**Title:** `Lab Submission - [StudentID] [Name]`

**Description:** ใช้ template ที่กำหนด (จะขึ้นอัตโนมัติ)

### ตัวอย่าง Pull Request Title:
```
Lab Submission - 65123456 John Doe
```

## กฎและข้อกำหนด

### 📋 เกณฑ์การตรวจ
- **ความสมบูรณ์** (40%): ไฟล์ครบตามที่กำหนด
- **ความถูกต้อง** (30%): โค้ดทำงานได้และผลลัพธ์ถูกต้อง
- **คุณภาพรายงาน** (20%): รายงานละเอียดและมีคุณภาพ
- **การส่งตรงเวลา** (10%): ส่งภายในกำหนด

### ⚠️ ข้อควรระวัง
1. **ห้ามแก้ไขไฟล์นอกโฟลเดอร์ของตนเอง**
2. **ใช้ชื่อ branch ตามรูปแบบที่กำหนด**
3. **ไม่ส่งไฟล์ที่มีขนาดใหญ่เกินไป** (video < 100MB)
4. **ตรวจสอบให้แน่ใจว่า Pull Request target ถูกต้อง**

### 🕐 กำหนดเวลา
- **Deadline:** [วันที่กำหนดส่ง] 23:59 น.
- **Late Submission:** หักคะแนน 10% ต่อวัน
- **Maximum Late:** 7 วัน (หลังจากนั้นไม่รับงาน)

### 📞 การขอความช่วยเหลือ
หากมีปัญหา:
1. ตรวจสอบ documentation ก่อน
2. ถามในกลุ่ม/ฟอรัม
3. ติดต่ออาจารย์หรือ TA

## คำสั่งที่มีประโยชน์

### Git Commands
```bash
# ดูสถานะปัจจุบัน
git status

# ดู log การ commit
git log --oneline

# ดู remote repositories
git remote -v

# ดู branch ทั้งหมด
git branch -a

# Switch branch
git checkout branch-name

# Pull อัปเดตจาก upstream
git pull upstream main
```

### ตรวจสอบก่อนส่ง
```bash
# ตรวจสอบขนาดไฟล์
find submissions/studentID-name -type f -exec ls -lh {} \;

# ตรวจสอบโครงสร้าง
tree submissions/studentID-name

# ตรวจสอบว่า Docker ยังทำงานได้
docker-compose build
docker-compose up -d
```
