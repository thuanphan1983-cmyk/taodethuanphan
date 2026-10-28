# 🎓 Hệ Thống Tạo Đề Thi Thông Minh (Smart Exam Generator - GDPT 2018)

> Ứng dụng Web hiện đại hỗ trợ giáo viên THPT môn Toán, Lý, Hóa tạo đề kiểm tra chuẩn quy cách đề minh họa 2025 của Bộ Giáo dục & Đào tạo Việt Nam.

---

## 🌟 Tính Năng Nổi Bật

1. **Ma Trận Nhận Thức Cố Định GDPT 2018 (40 - 30 - 20 - 10):**
   - 40% Nhận biết (NB)
   - 30% Thông hiểu (TH)
   - 20% Vận dụng (VD)
   - 10% Vận dụng cao (VDC)
2. **Cấu Trúc 4 Phần Chuẩn Năm 2025:**
   - **Phần I:** Trắc nghiệm 4 lựa chọn (A, B, C, D)
   - **Phần II:** Trắc nghiệm Đúng/Sai (4 ý a, b, c, d)
   - **Phần III:** Trả lời ngắn (kết quả số)
   - **Phần IV:** Tự luận / Bài toán thực tế
3. **Hiển Thị & Xuất File Chuẩn Giáo Dục:**
   - Hiển thị công thức sắc nét qua **KaTeX**.
   - Xuất file `.docx` chuẩn cấu trúc **Office Math Markup Language (OMML)** - tương thích 100% với **MathType** và **Microsoft Word Equation Editor**.
   - Tự động bóc tách và nhúng hình vẽ minh họa, đồ thị hàm số, bảng biến thiên trực tiếp vào Word.
4. **Tạo Mã QR Đáp Án Chuẩn TNMaker:**
   - Tự động sinh chuỗi đáp án chuẩn cho ứng dụng chấm thi TNMaker.
5. **Chuyển Đổi PDF Sang Word (OCR Toán Học):**
   - Tích hợp Gemini Vision (`gemini-3.8-flash` / `gemini-2.5-flash`) tự động nhận diện đề thi scan, bóc tách đồ thị và xuất Word.
   - Tự động lưu trữ đề thi sau khi OCR vào **Kho Đề Thi**.

---

## 🚀 Hướng Dẫn Kết Nối GitHub & Vercel

### Bước 1: Khởi tạo và Đẩy Code lên GitHub

Mở PowerShell hoặc Terminal tại thư mục dự án và chạy các lệnh sau:

```bash
# 1. Khởi tạo Git repository (nếu chưa có)
git init -b main

# 2. Thêm tất cả tệp vào Git index
git add .

# 3. Tạo commit đầu tiên
git commit -m "feat: initial commit Smart Exam Generator GDPT 2018"

# 4. Tạo một repository mới trên GitHub (https://github.com/new), đặt tên ví dụ: smart-exam-generator

# 5. Liên kết tới repository GitHub của bạn (thay <USERNAME> và <REPO_NAME> tương ứng):
git remote add origin https://github.com/<USERNAME>/<REPO_NAME>.git

# 6. Đẩy code lên GitHub
git push -u origin main
```

---

### Bước 2: Kết Nối & Triển Khai Lên Vercel

1. Truy cập [Vercel Dashboard](https://vercel.com/new).
2. Đăng nhập bằng tài khoản **GitHub**.
3. Tại mục **Import Git Repository**, chọn repository `smart-exam-generator` bạn vừa tạo.
4. Vercel sẽ tự động phát hiện cấu hình chuẩn:
   - **Framework Preset:** `Vite`
   - **Root Directory:** `./`
   - **Build Command:** `npm run build`
   - **Output Directory:** `dist`
   - **Install Command:** `npm install`
5. Nhấn **Deploy**.
6. Dự án đã có sẵn tệp `vercel.json` định tuyến SPA (`rewrites`), đảm bảo truy cập tất cả các đường dẫn (`/login`, `/repository`, `/pdf-to-word`) mượt mà không bao giờ bị lỗi 404 khi tải lại trang!

---

## 🛠 Công Nghệ Sử Dụng

- **Frontend:** React 18, Vite 5, TypeScript 5, Tailwind CSS, Lucide Icons, Shadcn UI patterns
- **Math & Office:** KaTeX, docx (OMML MathRun), file-saver, pdfjs-dist
- **AI Core:** Google Gemini API (`gemini-2.5-flash`, `gemini-3.8-flash`, `gemini-3.1-pro-preview`)
- **Database & Auth:** Firebase Firestore / IndexedDB / LocalStorage, Google Sign-In
