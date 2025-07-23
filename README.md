# Lab 04: ESP32 Docker QEMU Development Environment

## ภาพรวมของโปรเจ็กต์

โปรเจ็กต์นี้เป็นการสร้างสภาพแวดล้อมการพัฒนาโปรแกรม ESP32 โดยใช้ Docker และการจำลองการทำงานด้วย QEMU เพื่อให้นักศึกษาสามารถพัฒนาและทดสอบโปรแกรม ESP32 ได้โดยไม่ต้องมีฮาร์ดแวร์จริง

## เป้าหมายการเรียนรู้

- เข้าใจการใช้ Docker ในการสร้างสภาพแวดล้อมการพัฒนา
- เรียนรู้การพัฒนาโปรแกรม ESP32 ด้วย ESP-IDF
- ฝึกการใช้ QEMU สำหรับการจำลอง embedded system
- เข้าใจกระบวนการ build, debug และ testing

## โครงสร้างไฟล์

```
lab-04-esp32-docker-qemu/
├── LAB_WORKSHEET.md      # ใบงานการทดลองหลัก
├── QUICK_START.md        # คำแนะนำการเริ่มต้นอย่างรวดเร็ว
├── Dockerfile            # Docker image configuration
├── docker-compose.yml    # Docker services configuration  
├── Makefile             # Build automation
├── esp32-helper.sh      # Helper scripts
├── run_qemu.sh          # QEMU execution script
└── examples/            # ตัวอย่างโค้ด
    └── hello_world_main.c
```

## การเริ่มต้นใช้งาน

### ข้อกำหนดระบบ
- Docker Desktop
- RAM อย่างน้อย 4GB
- พื้นที่ดิสก์ว่าง 5GB
- Internet connection

### ขั้นตอนเริ่มต้น
1. **อ่านใบงานการทดลอง**: `LAB_WORKSHEET.md`
2. **ทำตามคำแนะนำเริ่มต้น**: `QUICK_START.md`
3. **ติดตั้ง Docker Desktop** จาก https://www.docker.com/products/docker-desktop

### คำสั่งพื้นฐาน

```bash
# Build Docker environment
docker-compose build

# เริ่มต้น development environment
docker-compose up -d

# เข้าสู่ container
docker-compose exec esp32-dev bash

# หยุดการทำงาน
docker-compose down
```

## เครื่องมือที่ใช้

- **ESP-IDF v5.1**: Framework สำหรับพัฒนา ESP32
- **QEMU**: Emulator สำหรับจำลอง ESP32
- **GDB**: Debugger สำหรับ embedded development
- **Docker**: Containerization platform

## การส่งงาน

นักศึกษาต้องส่งงานผ่าน **GitHub Pull Request** เท่านั้น

### ขั้นตอนการส่งงาน:
1. **Fork** repository นี้ไปยังบัญชี GitHub ของตนเอง
2. **Clone** และสร้าง branch ใหม่: `submission/studentID-name`
3. **เพิ่มงาน** ในโฟลเดอร์ `submissions/studentID-name/`
4. **สร้าง Pull Request** กลับมายัง repository หลัก

## เอกสารประกอบ

### 📚 เอกสารหลัก
- **[LAB_WORKSHEET.md](LAB_WORKSHEET.md)** - ใบงานการทดลองหลัก (20 ขั้นตอน)
- **[QUICK_START.md](QUICK_START.md)** - คำแนะนำการเริ่มต้นอย่างรวดเร็ว

### 🔧 เอกสารเทคนิค
- **[DOCKER_COMMANDS_GUIDE.md](DOCKER_COMMANDS_GUIDE.md)** - คำแนะนำ Docker commands โดยละเอียด
- **[GRADING_RUBRIC.md](GRADING_RUBRIC.md)** - เกณฑ์การให้คะแนน

### 📝 การส่งงาน
- **[SUBMISSION_GUIDE.md](SUBMISSION_GUIDE.md)** - คำแนะนำการส่งงานผ่าน Pull Request
- **[.github/pull_request_template.md](.github/pull_request_template.md)** - แบบฟอร์ม Pull Request

### กำหนดส่ง:
- **Deadline:** [วันที่กำหนดส่ง] 23:59 น.
- **Late Submission:** หักคะแนน 10% ต่อวัน
- **ไม่รับงานหลังเกิน 7 วัน**

## License

This project is for educational purposes only.

## ผู้สร้าง

Special Topics Computer Thursday - Engineering Education
## การใช้ Docker สำหรับพัฒนา ESP32 และจำลองด้วย QEMU