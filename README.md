# 🐍 Lộ Trình Học Python Căn Bản

> **Từ biến đến game thực chiến** — 13 tuần · 33 chủ đề · 75 bài tập · 3 milestones

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://python.org)
[![Pygame](https://img.shields.io/badge/Pygame-2.x-orange.svg)](https://pygame.org)

---

## 📋 Tổng Quan

Lộ trình học Python **3 tháng (13 tuần)** từ nền tảng đến dự án thực chiến:

| Phase | Nội dung | Tuần | Topics | Bài tập |
|-------|----------|------|--------|---------|
| **Phase 1** | Python Căn Bản | T1 – T7 | 14 | 29 |
| **Phase 2** | Git & GitHub | T8 – T9 | 6 | 10 |
| **Phase 3** | Project Flappy Bird | T10 – T13 | 13 | 36 |

---

## 📚 Lộ Trình Chi Tiết

### Phase 1 · Python Căn Bản (Tuần 1–7)

| Tuần | Chủ đề | Nội dung chính |
|------|--------|----------------|
| 1–2 | Variables, Types & Loops | Data types, operators, if/elif/else, for/while, virtualenv |
| 3–4 | Collections, Functions, Memory & Recursion | List/Dict/Tuple/Set, functions, scope, memory model, đệ quy |
| 5 | File I/O & Exceptions | CSV/JSON, try/except, custom exceptions |
| 6–7 | OOP, Algorithms & CS Foundations | 4 tính chất OOP, search/sort, Big O notation, execution model |

**Milestone 1**: Mini Library Manager CLI — đọc/ghi CSV, OOP, tìm kiếm, sắp xếp

---

### Phase 2 · Git & GitHub (Tuần 8–9)

| Tuần | Chủ đề | Nội dung chính |
|------|--------|----------------|
| 8 | Git cơ bản | init, add, commit, log, branch, merge, .gitignore |
| 9 | GitHub | Remote, push, pull, clone, pull request |

**Milestone 2**: Đẩy project Phase 1 lên GitHub với history rõ ràng

---

### Phase 3 · Project Thực Chiến — Flappy Bird (Tuần 10–13)

| Tuần | Chủ đề | Nội dung chính |
|------|--------|----------------|
| 10 | Pygame & Game Loop | pygame.init, display, Clock, FPS, event loop |
| 11 | Bird & Chuyển động | Surface/Rect, image/transform, gravity, animation, USEREVENT |
| 12 | Pipe, Va chạm & Âm thanh | Floor tiling, Pipe random, colliderect, mixer.Sound |
| 13 | Menu & Hoàn thiện | Font/draw, Button/Input, State machine, File I/O ranking |

**Milestone 3**: Game Flappy Bird hoàn chỉnh — 16 bước từ cửa sổ trống đến game có bảng xếp hạng

---

## 🚀 Bắt Đầu Học

### 1. Mở lộ trình

```bash
# Double-click index.html
# hoặc mở bằng Live Server trong VS Code
```

Giao diện web tự động tải nội dung từng phase, có:
- Theo dõi tiến độ theo từng bài tập (checkbox)
- Ghi chú cá nhân lưu tự động vào localStorage
- Search toàn bộ nội dung
- Dark/Light mode

### 2. Cài đặt môi trường Python

```bash
# Tạo virtualenv
python -m venv .venv

# Kích hoạt (Windows PowerShell)
.venv\Scripts\Activate.ps1

# Kích hoạt (macOS/Linux)
source .venv/bin/activate

# Cài dependencies
pip install -r requirements.txt
```

### 3. Cài Pygame (cho Phase 3)

```bash
pip install pygame

# Kiểm tra cài đặt
python -m pygame --version
```

---

## 📁 Cấu Trúc Project

```
lession-python/
├── index.html          # Giao diện chính — mở file này để học
├── styles.css          # Styling (dark/light theme)
├── script.js           # Logic: progress tracking, search, notes
│
├── phase1.html         # Python Căn Bản (14 topics)
├── phase2.html         # Git & GitHub (6 topics)
├── phase3.html         # Flappy Bird Project (13 topics)
│
├── requirements.txt    # Python dependencies
├── pytest.ini          # Cấu hình pytest (cho Phase 1 bài tập)
├── conftest.py         # pytest fixtures
├── example_test.py     # File test mẫu
├── demo.py             # Script demo
│
└── README.md           # File này
```

---

## 🎯 Hướng Dẫn Sử Dụng

### Cách học theo từng topic

1. Đọc **lý thuyết** và đọc kỹ code examples
2. Tự gõ lại code (không copy-paste) vào IDE
3. Làm **bài tập thực hành** — mỗi bài có mô tả rõ
4. **Check vào checkbox** khi hoàn thành từng bài
5. Dùng **📝 Ghi chú** để note lại điều chưa hiểu
6. Hoàn thành **milestone** cuối mỗi phase trước khi qua phase tiếp

### Tips học hiệu quả

| | Gợi ý |
|--|-------|
| ⏰ **Thời gian** | 8–12 giờ/tuần (1–2 giờ/ngày) |
| 🎯 **Thứ tự** | Học tuần tự, không bỏ qua |
| 💻 **Thực hành** | Code nhiều hơn đọc — tỷ lệ 70/30 |
| 🔄 **Ôn tập** | Review bài cũ 10 phút trước mỗi buổi học |
| 🐛 **Debug** | Đọc kỹ error message trước khi Google |

---

## ⚙️ Yêu Cầu Hệ Thống

| | Yêu cầu |
|--|---------|
| **Python** | 3.10+ |
| **Pygame** | 2.x (Phase 3) |
| **Browser** | Chrome/Firefox/Edge (để mở index.html) |
| **OS** | Windows 10+, macOS 12+, Ubuntu 20.04+ |
| **RAM** | 4GB+ |

---

## 📊 Nội Dung Phase 1 Chi Tiết

<details>
<summary>Xem 14 chủ đề Phase 1</summary>

1. Variables, Data Types & Operators
2. Conditionals & Loops
3. Virtualenv, Type Hints & Code Quality
4. List, Dictionary, Tuple, Set
5. Functions (*args, **kwargs, default params)
6. Memory & References (id, is vs ==, mutable/immutable)
7. Scope & Lifetime (LEGB rule, global, namespace)
8. Recursion (base case, call stack, factorial, fibonacci)
9. File I/O — CSV & JSON
10. Exceptions & Error Handling (try/except/finally, custom exceptions)
11. 4 Tính chất OOP (Encapsulation, Inheritance, Polymorphism, Abstraction)
12. Algorithms & Problem Solving (Linear/Binary Search, Bubble/Insertion Sort)
13. Complexity Analysis — Big O (O(1), O(n), O(log n), O(n²))
14. Program Execution Model (Bytecode, Stack/Heap, Garbage Collection)

</details>

---

## 📊 Nội Dung Phase 3 Chi Tiết

<details>
<summary>Xem 13 chủ đề Phase 3 + 16 bước milestone</summary>

**Topics:**
1. Tổng quan dự án Flappy Bird (7 class, kiến trúc)
2. Pygame là gì? (SDL, modules, cài đặt)
3. Cửa sổ game & Game Loop (display, Clock, FPS, event)
4. Surface & Rect (blit, get_rect, colliderect)
5. pygame.image & pygame.transform (load, scale, flip)
6. Bird — Trọng lực, Nhảy & Animation (USEREVENT, set_timer)
7. Floor — Sàn cuộn vô hạn (tiling, reset)
8. Pipe — Cột chướng ngại vật (randrange, recycling)
9. Va chạm & Tính điểm (colliderect, boundary check)
10. pygame.mixer — Âm thanh (Sound, play, pause)
11. pygame.font & pygame.draw (render text, Button, Input)
12. Game State & Animation Game Over (state machine, slide-in)
13. Bảng xếp hạng & File I/O (Top 5, đọc/ghi file)

**Milestone — 16 bước build từ đầu:**
Bước 1 → Screen class → Bước 8 → Pipe → Bước 12 → Game Over animation → Bước 16 → Control class hoàn chỉnh

</details>

---

_Made with Python 🐍_
