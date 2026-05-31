# Lộ Trình Học Python Phase 2

**Git & GitHub · Tuần 8–9 · 6 chủ đề · 10 bài tập**

---

## Tổng Quan Phase 2

> 2 tuần thực chiến với Git & GitHub — từ cài đặt đến workflow chuyên nghiệp

### Nội dung
- 2 tuần: Tuần 8 (Git) và Tuần 9 (GitHub)
- 6 chủ đề từ cơ bản đến thực chiến
- 10 bài tập thực hành có kiểm chứng

### Milestone cuối Phase
- Tạo repo GitHub, push toàn bộ bài tập Python lên mạng
- Xem lịch sử commit trực tiếp trên trang GitHub
- Clone repo về máy mới và xác nhận code đầy đủ

---

## Git là gì?

> Git = "chụp ảnh" code theo thời gian — quay lại bất kỳ bản nào khi cần

### Kiến thức chính
- **Git** lưu từng "bản chụp" (snapshot) của code theo thời gian
- **Git ≠ GitHub** — Git chạy trên máy tính, GitHub là kho lưu trên mạng
- Cài đặt tại `git-scm.com`, kiểm tra bằng `git --version`
- Cấu hình một lần duy nhất: `git config --global user.name` và `user.email`
- Git ghi tên/email vào mỗi commit để biết ai đã làm gì

### Bài tập thực hành
- 📝 Cài Git và kiểm tra phiên bản
- 📝 Cấu hình tên và email

---

## Các Lệnh Git Cơ Bản

> init · status · add · commit · log — quy trình lưu code hàng ngày

### Kiến thức chính
- **3 khu vực**: Working folder → Staging area → Repository
- `git init` — khởi tạo Git trong thư mục dự án (1 lần/dự án)
- `git status` — xem file nào đang thay đổi
- `git add .` — đưa tất cả thay đổi vào staging
- `git commit -m "message"` — lưu snapshot với mô tả rõ ràng
- `git log --oneline` — xem lịch sử commit ngắn gọn

### Bài tập thực hành
- 📝 Tạo repo đầu tiên
- 📝 Thực hiện 3 commit liên tiếp

---

## File .gitignore

> Bảo Git "đừng quan tâm đến file này" — bảo vệ mật khẩu và dọn rác

### Kiến thức chính
- `.gitignore` liệt kê các file/thư mục Git sẽ bỏ qua hoàn toàn
- Đặt ở thư mục gốc dự án, cùng chỗ với thư mục `.git`
- Bỏ qua `__pycache__/` và `*.pyc` — file tự sinh của Python
- **Quan trọng**: file `.env` chứa mật khẩu — đừng bao giờ commit
- Sau khi tạo `.gitignore`, `git status` sẽ không còn hiển thị các file đó

### Bài tập thực hành
- 📝 Tạo file .gitignore cho Python

---

## Tạo Tài Khoản GitHub & Repository

> GitHub = Google Drive dành cho code — lưu, chia sẻ, theo dõi lịch sử

### Kiến thức chính
- Đăng ký tại `github.com` — chọn username dễ nhớ
- **Repository** (repo) = kho chứa một dự án, mỗi dự án một repo riêng
- Tạo repo mới: click `+` → New repository → đặt tên → Create
- Chọn **Public** (công khai) hoặc **Private** (riêng tư)
- Không tick "Add a README" nếu máy đã có code sẵn

### Bài tập thực hành
- 📝 Đăng ký tài khoản GitHub
- 📝 Tạo repo đầu tiên trên GitHub

---

## Đẩy Code Lên GitHub (push)

> Nối thư mục máy tính với repo GitHub rồi đẩy code lên — chỉ 3 lệnh lần đầu

### Kiến thức chính
- `git branch -M main` — đổi tên nhánh chính theo chuẩn GitHub
- `git remote add origin <URL>` — nối thư mục với repo trên GitHub
- `git push -u origin main` — đẩy code lên lần đầu
- Từ lần 2 trở đi: chỉ cần `git add .` → `git commit` → `git push`
- Nếu bị hỏi mật khẩu nhiều lần: dùng **Personal Access Token** thay mật khẩu

### Bài tập thực hành
- 📝 Đẩy bài tập Python lên GitHub
- 📝 Thêm file mới và push lại

---

## Tải Code Về Máy (clone & pull)

> Chuyển máy tính? clone về trong 1 lệnh — cập nhật code mới? dùng pull

### Kiến thức chính
- `git clone <URL>` — tải toàn bộ repo (code + lịch sử) về máy mới
- `git pull` — cập nhật code mới nhất từ GitHub về máy đang dùng
- **Thói quen tốt**: `git pull` trước khi làm việc, `git push` sau khi xong
- Clone tạo ra thư mục mới chứa đầy đủ mọi thứ — không cần cài lại Git config

### Bài tập thực hành
- 📝 Clone repo về một thư mục khác

---

## Milestone Phase 2 — Đưa Bài Tập Python Lên GitHub

> Hoàn thành toàn bộ quy trình Git & GitHub trong một dự án thật

### Checklist hoàn thành
- Tạo thư mục `bai-tap-python`, chạy `git init` và `git config`
- Tạo file `.gitignore` bỏ qua `__pycache__/`
- Commit ít nhất **3 lần** với message có ý nghĩa
- Tạo repo trên GitHub và push code lên thành công
- Vào trang GitHub, xem lịch sử commit hiển thị đúng 3+ lần
- Clone repo về thư mục khác và xác nhận code đầy đủ
