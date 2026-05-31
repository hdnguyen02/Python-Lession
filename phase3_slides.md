# Lộ Trình Học Python Phase 3

**Project Thực Chiến · Tuần 10–13 · 13 chủ đề · 36 bài tập**

---

## Tổng Quan Phase 3

> 4 tuần xây dựng game Flappy Bird hoàn chỉnh từ 0 — đồ họa, vật lý, âm thanh, UI, lưu dữ liệu

### Nội dung
- 4 tuần: Tuần 10–13
- 13 chủ đề từ Pygame cơ bản đến game hoàn chỉnh
- 36 bài tập thực hành, build từng phần rồi ghép lại

### Kết quả sau Phase
- Game Flappy Bird chạy 60 FPS với animation, âm thanh, bảng xếp hạng
- Hiểu OOP, vật lý, xử lý sự kiện, file I/O qua thực chiến
- Có sản phẩm thật để đưa vào portfolio

---

## Giới Thiệu Project — Flappy Bird

> Game đủ đơn giản để hoàn thành trong 1 tháng, đủ phức tạp để học mọi thứ quan trọng

### Tính năng game hoàn chỉnh
- Cửa sổ 500×700px, chạy ổn định 60 FPS
- Bird: animation 17 frame, trọng lực, nhảy bằng click/Space
- Pipe: 3 cặp cột ngẫu nhiên di chuyển và tái tạo liên tục
- Floor: sàn cuộn vô hạn bằng kỹ thuật tiling
- Va chạm chính xác, tính điểm khi vượt cột
- Nhạc nền + 4 SFX, nút bật/tắt âm thanh
- Nhập tên người chơi, bảng xếp hạng Top 5 lưu ra file

### Kiến trúc — 7 class chính
- `Control` — bộ điều khiển trung tâm, state machine
- `Screen` — quản lý cửa sổ pygame
- `Bird`, `Pipe`, `Floor` — các đối tượng game
- `Achievement` — điểm số và bảng xếp hạng
- `Utilitie` — helper tĩnh: load ảnh, font, Button, Input

### Bài tập thực hành
- 📝 Clone project và chạy thử
- 📝 Vẽ sơ đồ class bằng tay

---

## Pygame là gì?

> Thư viện Python bọc SDL — cho phép vẽ đồ họa, phát âm thanh, đọc input từ bàn phím/chuột

### Kiến thức chính
- **Pygame** xây trên **SDL** (C library) — cross-platform trên Windows, Mac, Linux
- Pygame không phải game engine — bạn tự xây game loop, physics, collision
- Đây là lý do học Pygame: hiểu từng thứ hoạt động thế nào
- Cài đặt: `pip install pygame`, kiểm tra: `python -m pygame --version`
- Module quan trọng: `display`, `event`, `image`, `transform`, `time`, `mixer`, `font`, `draw`

### Bài tập thực hành
- 📝 Cài pygame và kiểm tra version

---

## Cửa Sổ Game & Game Loop

> pygame.init · display.set_mode · Clock · FPS · event.get · QUIT

### Kiến thức chính
- Mọi game Pygame: **khởi tạo → tạo cửa sổ → game loop** lặp 60 lần/giây
- Mỗi vòng loop làm 3 việc: xử lý sự kiện → cập nhật trạng thái → vẽ lại
- `clock.tick(60)` — gọi đầu mỗi vòng loop để giới hạn 60 FPS
- `pygame.event.get()` — lấy danh sách sự kiện đang chờ xử lý
- `pygame.QUIT` — sự kiện người dùng bấm X cửa sổ
- Trong project: `Screen` class bọc cửa sổ, `Control` class bọc game loop

### Bài tập thực hành
- 📝 Tạo cửa sổ 500×700 màu xanh trời
- 📝 Tạo Screen class

---

## Surface & Rect — Nền Tảng Đồ Họa

> Surface = tấm canvas chứa pixel · Rect = vị trí + kích thước · blit = vẽ lên màn hình

### Kiến thức chính
- **Surface**: mọi ảnh, text, hình vẽ đều là Surface
- **Rect**: hình chữ nhật xác định vị trí — `topleft`, `center`, `midleft`
- `window.blit(surface, rect)` — vẽ surface lên cửa sổ tại vị trí rect
- Di chuyển object = thay đổi `rect.x`/`rect.y`/`rect.centery`
- `rect.colliderect(other)` — kiểm tra va chạm giữa 2 rect, trả về True/False
- Thuộc tính hữu ích: `top`, `bottom`, `left`, `right`, `center`, `centerx`, `centery`

### Bài tập thực hành
- 📝 Load và hiển thị ảnh background

---

## pygame.image & pygame.transform

> image.load · transform.scale · transform.flip — load ảnh đúng cách, tránh lag

### Kiến thức chính
- `image.load(path)` — load ảnh từ file, trả về Surface
- `transform.scale(surface, (w, h))` — resize ảnh về kích thước cố định
- `transform.flip(surface, x_bool, y_bool)` — lật ảnh ngang/dọc
- `flip(s, False, True)` = lật ngược dọc → dùng để tạo cột trên từ cột dưới
- **Quan trọng**: load ảnh trong `__init__` hoặc class variable — KHÔNG gọi trong game loop
- Dùng `staticmethod` cho helper tĩnh: `surfaceSize(path, size)` và `surfaceScale(path, scale)`

### Bài tập thực hành
- 📝 Tạo Utilitie class với 2 method

---

## Bird — Trọng Lực, Nhảy & Animation

> GRAVITY · movement · handleJump · USEREVENT · set_timer · 17 frame

### Kiến thức chính
- Vật lý đơn giản: mỗi frame `movement += GRAVITY(0.25)`, `rect.centery += movement`
- Nhảy: `handleJump()` đặt `movement = -SPEED(-5)` → bird bật lên rồi rơi lại
- Bird X cố định = 140, chỉ di chuyển theo trục Y
- **Animation**: load 17 frame vào list, dùng `USEREVENT + 5` và `set_timer(event, 16ms)`
- Mỗi khi nhận timer event, chuyển sang frame tiếp theo theo vòng tròn `% 17`
- Input: `MOUSEBUTTONDOWN` hoặc `KEYDOWN + K_SPACE` → gọi `handleJump()`

### Bài tập thực hành
- 📝 Bird rơi bởi trọng lực
- 📝 Bird nhảy khi click chuột hoặc Space
- 📝 Animation 17 frame

---

## Floor — Sàn Cuộn Vô Hạn

> Tiling 3 bản · cuộn theo SPEED · reset khi ra ngoài màn hình

### Kiến thức chính
- Kỹ thuật **tiling**: vẽ 3 bản sàn nối tiếp nhau tại `x`, `x+width`, `x+width*2`
- Mỗi frame: `x -= SPEED(2)` → sàn dịch sang trái
- Khi `x <= -floor_width`: reset `x = 0` — tạo hiệu ứng cuộn vô hạn
- Sàn chỉ di chuyển khi `isPlay = True`, dừng khi game over
- `bottomleft` anchor đảm bảo sàn luôn dính đáy màn hình

### Bài tập thực hành
- 📝 Tạo Floor cuộn vô hạn

---

## Pipe — Cột Chướng Ngại Vật

> randrange · tạo top/bottom pair · BLANK gap · di chuyển · tái tạo

### Kiến thức chính
- Mỗi cặp cột: 1 cột dưới (`bottom`) + 1 cột trên (`top` = lật ngược), hở `BLANK = 160px`
- `randrange()` tạo vị trí Y ngẫu nhiên cho cặp cột mỗi lần sinh
- Quản lý danh sách **3 cặp cột**: di chuyển trái `SPEED = 2px/frame`
- Khi cặp đầu ra ngoài (`x < -WIDTH`): `pop(0)` xóa đi, `append()` thêm cặp mới ở cuối
- Cờ `"pass": False` đánh dấu cặp cột đã được tính điểm chưa

### Bài tập thực hành
- 📝 Tạo 3 cặp cột và di chuyển

---

## Va Chạm & Tính Điểm

> colliderect · boundary check · score khi vượt cột

### Kiến thức chính
- Va chạm sàn/mép trên: kiểm tra `rect.y <= 0` hoặc `rect.y >= screen.height - floor.height`
- Va chạm cột: `bird.rect.colliderect(pipe["top"])` hoặc `colliderect(pipe["bottom"])`
- Khi `isCollision()` trả `True` → đặt `isPlay = False` → dừng mọi di chuyển
- Tính điểm: khi `pipe["bottom"].right < bird.x` và `pipe["pass"] == False`
- Đánh dấu `pass = True` ngay sau khi tính điểm để không đếm hai lần
- Hiển thị điểm bằng `pygame.font.Font` render lên góc trên màn hình

### Bài tập thực hành
- 📝 Va chạm và game over
- 📝 Tính điểm và hiển thị

---

## pygame.mixer — Âm Thanh

> mixer.Sound · play · loops · pause · unpause · 5 file âm thanh

### Kiến thức chính
- `mixer.Sound(path)` — load file âm thanh (.mp3), trả về Sound object
- `sound.play(loops=0)` — phát 1 lần; `loops=-1` — phát vô hạn (nhạc nền)
- `mixer.pause()` — tạm dừng TẤT CẢ channel đang chạy
- `mixer.unpause()` — tiếp tục từ chỗ dừng
- 5 âm thanh: nhạc nền, SFX nhảy, va chạm, thua, cộng điểm
- Nút mute: toggle giữa `pause()` và `unpause()` bằng flag `isSound`

### Bài tập thực hành
- 📝 Tích hợp 5 file âm thanh

---

## pygame.font & pygame.draw — Text và UI

> font.Font · render · Button class · Input class · draw.line

### Kiến thức chính
- `font.Font(path, size)` — load font .ttf với kích thước chỉ định
- `font.render(text, True, color)` — render text thành Surface (True = antialias)
- `event.unicode` — lấy ký tự Unicode của phím được nhấn (dùng cho nhập text)
- **Button class**: `checkClick(pos)` kiểm tra tọa độ chuột có trong vùng rect không
- **Input class**: xử lý `KEYDOWN`, dùng cursor `_`, hỗ trợ Backspace
- `draw.line(surface, color, start, end, width)` — vẽ đường kẻ dưới ô input

### Bài tập thực hành
- 📝 Tạo Button và Input class

---

## Game State & Animation Game Over

> State machine · isPlay flag · slide-in animation · min/max clamp

### Kiến thức chính
- Game có 3 trạng thái: **Start → Playing → Game Over**
- 3 method riêng: `startGame()`, `handlGame()`, `finishGame()` — mỗi cái 1 vòng loop riêng
- `isPlay = False` → dừng bird rơi và cột di chuyển, bắt đầu `finishGame()`
- **Animation slide-in**: biến y bắt đầu ngoài màn hình, mỗi frame tăng/giảm cố định
- Dùng `min()`/`max()` để **clamp** tại vị trí đích — không cần thư viện animation
- Click Replay → `resetGame()` → `handlGame()` — vòng game mới bắt đầu

### Bài tập thực hành
- 📝 Implement 3 màn hình: Start, Play, Game Over
- 📝 Animation slide-in cho màn hình Game Over

---

## Bảng Xếp Hạng & File I/O

> open · readlines · sort · writelines · Top 5 logic

### Kiến thức chính
- File `top.txt`: mỗi dòng lưu `tên-điểm`, ví dụ `Alice-42`
- Đọc khi khởi động: `open('top.txt', 'r')` + `split('-')` để parse tên và điểm
- Cập nhật sau game over: chỉ ghi nếu điểm mới > điểm thứ 5
- `list.sort(key=lambda u: u["core"], reverse=True)` rồi `pop()` giữ đúng 5 người
- Ghi lại: `open('top.txt', 'w')` + `writelines([...])` + `close()`
- Hiển thị Top 5 với ảnh huy chương, nút Back về màn hình Start

### Bài tập thực hành
- 📝 Implement Achievement class đầy đủ
- 📝 Màn hình Ranking với bảng xếp hạng

---

## Milestone Phase 3 — Hoàn Thiện Game Flappy Bird

> Build lại từ đầu theo 16 bước — không copy, hiểu rồi tự gõ lại từng dòng

### Lộ trình 16 bước
- **Bước 1:** Tạo `Screen` class — cửa sổ 500×700, game loop, thoát bằng QUIT
- **Bước 2:** Load và vẽ background — `image.load`, scale, blit mỗi frame
- **Bước 3:** Tạo `Utilitie` class — `surfaceSize`, `surfaceScale`, `surfaceFont`
- **Bước 4:** `Floor` class — tiling 3 bản, cuộn liên tục, dừng khi `isPlay=False`
- **Bước 5:** `Bird` class — load 17 frame, hiển thị tại vị trí cố định
- **Bước 6:** Bird animation — USEREVENT + set_timer(16ms), vòng qua 17 frame
- **Bước 7:** Bird physics — GRAVITY=0.25, nhảy bằng click/Space (movement=-5)
- **Bước 8:** `Pipe` class — 3 cặp cột ngẫu nhiên, di chuyển, tái tạo khi ra ngoài
- **Bước 9:** Va chạm — `colliderect` + boundary check → `isPlay=False`
- **Bước 10:** Âm thanh — nhạc nền loops=-1, SFX nhảy/va chạm/thua/điểm
- **Bước 11:** `Achievement` — tính điểm khi vượt cột, hiển thị lên màn hình
- **Bước 12:** `Button` + `Input` class — checkClick, nhập tên, cursor, Backspace
- **Bước 13:** Màn hình Start — background, title, input tên, nút Start/Ranking/Mute
- **Bước 14:** Màn hình Game Over — animation slide-in bảng điểm, nút Replay/Home
- **Bước 15:** File I/O — đọc/ghi `top.txt`, cập nhật Top 5, màn hình Ranking
- **Bước 16:** `Control` class — kết nối tất cả, 3 vòng loop state machine, reset game
