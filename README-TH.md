# Capri Android Edition — v0.3.0 Quick Toggle

โปรเจกต์ Android สำหรับพัฒนา Capri ให้เป็นตัวละครลอยหน้าจอ พร้อมปุ่มควบคุมในแอปและ Quick Settings Tile

## สร้าง APK ผ่าน GitHub Actions

1. อัปโหลดไฟล์และโฟลเดอร์ทั้งหมดในโปรเจกต์นี้ไปยัง root ของ GitHub repository (อย่าอัปโหลด ZIP ซ้อนเป็นไฟล์เดียว)
2. เปิดแท็บ **Actions** ใน repository และเลือก **Build Capri Android APK**
3. กด **Run workflow** หรือรอให้ workflow ทำงานหลัง push ไฟล์
4. เมื่อสถานะเป็นสีเขียว เปิดรายการ workflow run แล้วดาวน์โหลด artifact ชื่อ `Capri-Android-debug-apk`
5. แตก ZIP artifact เพื่อรับ `app-debug.apk`

## คุณสมบัติในซอร์สรุ่นนี้
- แอป Android Kotlin และ floating overlay service
- ปุ่มเปิด/ปิด Capri ภายในแอป
- Quick Settings Tile สำหรับเปิด/ปิด Capri (ผู้ใช้ต้องเพิ่มไทล์เอง)
- การแจ้งเตือนขณะทำงานพร้อม action ปิด Capri
- WebView renderer ใช้ WebGL พร้อมภาพต้นฉบับและ fallback
- ขอสิทธิ์แสดงทับแอปอื่นผ่าน Android Settings โดยผู้ใช้เป็นผู้อนุญาตเอง

## ข้อจำกัดและสถานะการทดสอบ
- Workflow นี้สร้าง **debug APK** ไม่ใช่ release APK ที่ลงนามสำหรับเผยแพร่
- ต้องตรวจสอบการทำงานจริงบนอุปกรณ์ Android หลังติดตั้ง
- ฟีเจอร์ Capri desktop ทั้งหมด, state machine/acting เต็มรูปแบบ และ FX integration ยังไม่ครบ
- อย่าใส่ API key หรือรหัสผ่านลงใน GitHub repository

## เครื่องมือ build
- JDK 17
- Gradle 8.9
- Android Gradle Plugin 8.7.3
- Android compile SDK 35
