# SC3 Mobile E-Commerce

โปรเจกต์แอปพลิเคชันเว็บสำหรับการซื้อขายโทรศัพท์มือถือ (Mobile E-Commerce) โดยแบ่งระบบการทำงานออกเป็นส่วนของผู้ซื้อ (Buyer) และผู้ขาย (Seller) พัฒนาด้วย Vue.js สำหรับ Frontend และ Spring Boot สำหรับ Backend พร้อมระบบฐานข้อมูล MySQL และใช้งาน Docker สำหรับการ Deploy

## ฟีเจอร์หลัก (Features)

### ระบบผู้ใช้งาน (Authentication & Profile)
* **ลงทะเบียนและเข้าสู่ระบบ:** รองรับการสมัครสมาชิกแยกตามประเภทผู้ใช้งาน (Buyer และ Seller) และเข้าสู่ระบบผ่านระบบรักษาความปลอดภัยแบบ JWT (JSON Web Token)
* **การจัดการรหัสผ่าน:** มีระบบยืนยันอีเมล (Email Verification) และการขอรีเซ็ตรหัสผ่าน (Forgot/Reset Password)
* **จัดการโปรไฟล์:** ผู้ใช้สามารถดูและแก้ไขข้อมูลส่วนตัว รวมถึงอัปโหลดเอกสารที่เกี่ยวข้อง (เช่น รูปบัตรประชาชนสำหรับ Seller)

### ระบบจัดการสินค้าและแบรนด์ (Product & Brand Management)
* **จัดการแบรนด์สินค้า:** ผู้ขายสามารถเพิ่ม แก้ไข และลบข้อมูลแบรนด์โทรศัพท์ได้
* **จัดการรายการสินค้า:** ผู้ขายสามารถเพิ่มข้อมูลโทรศัพท์มือถือ ระบุรายละเอียด ราคา จำนวนสเปก และอัปโหลดรูปภาพสินค้าได้สูงสุดตามที่ระบบกำหนด
* **การแสดงผลสินค้า:** ผู้ซื้อสามารถเรียกดูรายการสินค้าแบบแกลเลอรี ค้นหา กรองสินค้าตามแบรนด์ เรียงลำดับ (Sort) และแบ่งหน้า (Pagination) ได้

### ระบบการสั่งซื้อ (Order Management)
* **ตะกร้าสินค้า (Cart):** ผู้ซื้อสามารถเลือกโทรศัพท์ลงตะกร้าและจัดการรายการสั่งซื้อ
* **ระบบคำสั่งซื้อ (Place Order):** ทำรายการสั่งซื้อสินค้าจากระบบ
* **ประวัติคำสั่งซื้อ:** ผู้ซื้อสามารถดูประวัติการสั่งซื้อของตนเองได้ และผู้ขายสามารถดูรายการคำสั่งซื้อที่มีลูกค้าสั่งสินค้าของตนได้

## เทคโนโลยีที่ใช้งาน (Tech Stack)

**Frontend:**
* Vue.js 3
* Vite
* Cypress (สำหรับการทำ End-to-End Testing)

**Backend:**
* Java (Spring Boot 3)
* Spring Security & JWT สำหรับระบบ Authentication
* Spring Data JPA
* Java Mail Sender (สำหรับส่งอีเมลยืนยันตัวตน)

**Database & Infrastructure:**
* MySQL 8+
* Docker & Docker Compose
* Nginx (Reverse Proxy / Web Server)
* GitHub Actions (CI/CD Pipeline)

## โครงสร้างโปรเจกต์ (Project Structure)

* `/Integrated_project_SC3_frontend/` - ซอร์สโค้ดฝั่ง Frontend (Vue.js) รวมถึงไฟล์คอนฟิก Nginx และ Test Script (Cypress)
* `/Integrated_project_SC3_backend/` - ซอร์สโค้ดฝั่ง Backend (Spring Boot) จัดการ API, ไฟล์อัปโหลด และ Business Logic
* `/Integrated_project_SC3_database/` - ไฟล์สคริปต์ SQL และ CSV สำหรับการสร้างโครงสร้างฐานข้อมูลเริ่มต้น (Seed data)
* `docker-compose.yml` - ไฟล์สำหรับรันคอนเทนเนอร์ของระบบทั้งหมด (Frontend, Backend, Database)

## การติดตั้งและการรันโปรเจกต์ (Installation & Setup)

**ข้อกำหนดเบื้องต้น:** ต้องติดตั้ง Docker และ Docker Compose บนเครื่องเซิร์ฟเวอร์หรือเครื่องที่ใช้รันโปรเจกต์

1. Clone Repository
```bash
git clone <repository_url>
cd integrated-project-sc3
