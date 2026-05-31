# Lộ Trình Học Python Phase 1
## Python Cơ Bản · Tuần 1–7
14 chủ đề · 29 bài tập · từ biến đến thuật toán và OOP

---

## Tổng Quan Phase 1

> 4 tuần · 11 chủ đề cốt lõi · 1 bài tập lớn cuối phase

### Lịch học theo tuần

- **Tuần 1–2** — Variables, Types & Loops
- **Tuần 3–4** — Collections, Functions, Memory & Recursion
- **Tuần 5** — File I/O & Exceptions
- **Tuần 6–7** — OOP, Algorithms & CS Foundations

### Milestone cuối phase

- Xây dựng **Mini Library Manager CLI** — áp dụng toàn bộ kiến thức Phase 1

---

## Variables, Data Types & Operators

> Kiểu dữ liệu cơ bản · toán tử · input/output

### Kiến thức chính

- `int`, `float`, `str`, `bool` — 4 kiểu dữ liệu cơ bản
- Python là **dynamically typed** — không cần khai báo kiểu trước
- `type()` để kiểm tra kiểu; `int()`, `float()`, `str()` để ép kiểu
- Toán tử số học: `+`, `-`, `*`, `/`, `//`, `%`, `**`
- Toán tử so sánh: `==`, `!=`, `>`, `<`, `>=`, `<=` → trả về `bool`
- Toán tử logic: `and`, `or`, `not`
- f-string: `f"{name}, {age} tuổi"` — cách format chuỗi hiện đại nhất

### Bài tập thực hành

- 📝 Tính BMI từ input
- 📝 Chuyển đổi nhiệt độ (Celsius → Fahrenheit & Kelvin)
- 📝 Đổi giây sang giờ:phút:giây
- 📝 Tính giảm giá
- 📝 Phân tích chuỗi tên

---

## Conditionals & Loops

> if/elif/else · for/while · break/continue · range()

### Kiến thức chính

- Python dùng **thụt lề (indentation)** thay vì `{}` — sai indent = lỗi ngay
- `if / elif / else` — rẽ nhánh điều kiện
- Ternary: `"PASS" if score >= 60 else "FAIL"` — viết gọn 1 dòng
- `for item in items:` — lặp qua từng phần tử
- `range(1, 6)` — sinh dãy số; `enumerate()` — lấy cả index và giá trị
- `while` + `break` / `continue` — vòng lặp có điều kiện dừng linh hoạt

### Bài tập thực hành

- 📝 In bảng cửu chương
- 📝 Kiểm tra số chẵn/lẻ trong list
- 📝 FizzBuzz
- 📝 Tìm số lớn nhất không dùng `max()`
- 📝 In tam giác sao căn phải

---

## List, Dictionary, Tuple, Set

> Cấu trúc dữ liệu · indexing · methods · comprehension

### So sánh 4 loại collection

| Loại | Thứ tự | Thay đổi được | Trùng lặp | Dùng khi nào |
|------|--------|---------------|-----------|--------------|
| `list` | ✅ | ✅ | ✅ | Danh sách thứ tự quan trọng |
| `dict` | ✅ | ✅ | key ❌ | Key-value, tra cứu nhanh |
| `tuple` | ✅ | ❌ | ✅ | Dữ liệu cố định, config |
| `set` | ❌ | ✅ | ❌ | Loại trùng, kiểm tra tồn tại |

### Kiến thức chính

- Index âm: `lst[-1]` → phần tử cuối; Slice: `lst[1:3]`
- `append()`, `insert()`, `remove()` — thao tác list cơ bản
- `dict.get(key, default)` — lấy giá trị có giá trị mặc định nếu key không tồn tại
- List comprehension: `[x for x in lst if condition]`

### Bài tập thực hành

- 📝 Quản lý danh sách sản phẩm
- 📝 Group sản phẩm theo category
- 📝 Đảo ngược list không dùng `reverse()`
- 📝 Tìm phần tử chung 2 list dùng `set`
- 📝 Dict comprehension lọc sản phẩm theo giá

---

## Functions

> def · return · default params · *args · **kwargs · lambda

### Kiến thức chính

- `def func(param):` — định nghĩa hàm; `return` trả về giá trị
- Default parameter: `def create(name, status="PENDING")`
- `*args` — nhận nhiều positional arguments (tuple bên trong hàm)
- `**kwargs` — nhận nhiều keyword arguments (dict bên trong hàm)
- Lambda: `sorted(lst, key=lambda x: x["price"])`
- Hàm giúp **tái sử dụng code** và tách logic thành đơn vị nhỏ có thể test

### Bài tập thực hành

- 📝 Hàm validate email
- 📝 Hàm tính điểm trung bình với `*args`
- 📝 Hàm `*args` — tính tổng và tích
- 📝 Hàm `**kwargs` tạo thẻ sản phẩm
- 📝 Lambda + sorted sắp xếp linh hoạt theo nhiều tiêu chí

---

## Memory & References

> id() · is vs == · Mutable vs Immutable · pass by reference · copy

### Kiến thức chính

- Biến không chứa giá trị — biến chứa **reference** đến object trên heap
- `id()` trả về địa chỉ bộ nhớ; `is` so sánh identity; `==` so sánh giá trị
- **Mutable**: `list`, `dict`, `set` — thay đổi in-place, ảnh hưởng tất cả reference
- **Immutable**: `int`, `float`, `str`, `tuple` — mỗi thay đổi tạo object mới
- `lst.copy()` → shallow copy; `copy.deepcopy()` → deep copy độc lập hoàn toàn
- Không dùng mutable default argument: `def f(x=[])` — bug khó phát hiện

### Bài tập thực hành

- 📝 Thí nghiệm `is` vs `==` và integer caching
- 📝 Hàm không sửa list gốc (`remove_duplicates`)
- 📝 Bẫy mutable default argument
- 📝 Shallow copy vs deep copy với nested list

---

## Scope & Lifetime

> LEGB rule · Local · Global · Enclosing · global keyword · Namespace

### Kiến thức chính

- Python tìm biến theo **LEGB**: Local → Enclosing → Global → Built-in
- Biến **local**: sống từ khi hàm chạy đến khi hàm `return`
- Biến **global**: sống cả đời chương trình
- Đọc global bên trong hàm: OK (không cần khai báo)
- Ghi global bên trong hàm: phải khai báo `global count`
- Hạn chế dùng `global` — khiến code khó test và debug
- `nonlocal` dùng cho closure (enclosing scope)

### Bài tập thực hành

- 📝 Truy vết LEGB qua 3 tầng hàm lồng nhau
- 📝 Refactor bỏ `global` — dùng class `Counter`
- 📝 Counter bằng closure (`nonlocal`)
- 📝 Hàm tạo ra hàm — `make_adder(n)`

---

## Recursion — Đệ quy

> Base case · Recursive case · Call stack · Factorial · Fibonacci

### Kiến thức chính

- Recursion = hàm tự gọi chính nó
- **Base case**: điều kiện dừng — bắt buộc phải có, thiếu → `RecursionError`
- **Recursive case**: gọi lại hàm với input nhỏ hơn
- Ứng dụng tự nhiên: cây thư mục lồng nhau, cấu trúc đệ quy
- `fib(40)` thuần đệ quy = 300 triệu lần gọi — dùng memoization thay thế
- Python giới hạn default recursion depth = 1000

### Bài tập thực hành

- 📝 Tổng các số trong list lồng nhau (`deep_sum`)
- 📝 Đảo ngược chuỗi bằng đệ quy
- 📝 Fibonacci với dict cache (memoization)
- 📝 GCD bằng thuật toán Euclid

---

## File I/O · CSV · JSON

> open() · read/write · with · csv module · json module

### Kiến thức chính

- Ba chế độ mở file: `'r'` (đọc), `'w'` (ghi đè), `'a'` (ghi thêm)
- Luôn dùng `with open(...) as f:` — tự đóng file kể cả khi có exception
- Mỗi dòng file dạng `"Alice-42\n"` → `rstrip().split('-')` để parse
- `json.dump(data, f, indent=2, ensure_ascii=False)` — ghi JSON có indent
- `json.load(f)` — đọc JSON trả về dict/list Python
- `encoding="utf-8"` để đọc đúng tiếng Việt

### Bài tập thực hành

- 📝 Đọc và in bảng xếp hạng từ `top.txt`
- 📝 Cập nhật bảng xếp hạng (sort + giữ top 5)
- 📝 Thống kê `top.txt` — điểm cao nhất, thấp nhất, trung bình

---

## Exceptions & Error Handling

> try/except/finally · raise · custom exceptions

### Kiến thức chính

- **Exception** = lỗi runtime — nếu không xử lý, chương trình dừng ngay
- `try` → `except` → `finally` — cấu trúc bắt lỗi đầy đủ
- `finally` luôn chạy dù có lỗi hay không — dùng để cleanup resource
- `raise DataError("message")` — ném lỗi thủ công khi phát hiện dữ liệu sai
- Custom exception: `class ValidationError(Exception): pass`
- Bắt lỗi cụ thể (`FileNotFoundError`), không dùng `except:` trống

### Các lỗi thường gặp

- `FileNotFoundError` · `JSONDecodeError` · `ZeroDivisionError` · `KeyError`

### Bài tập thực hành

- 📝 Xử lý lỗi đọc file (`load_config`)
- 📝 Custom `ValidationError`
- 📝 Hàm chia an toàn (`safe_divide`)
- 📝 Đọc `top.txt` an toàn với fallback
- 📝 Custom `ScoreError` hierarchy (subclass)

---

## 4 Tính Chất OOP

> Class · Object · Encapsulation · Inheritance · Polymorphism · Abstraction

### 4 tính chất cốt lõi

| Tính chất | Ý nghĩa | Keyword Python |
|-----------|---------|----------------|
| **Encapsulation** | Đóng gói data + method, kiểm soát truy cập | `_attr`, `__attr`, `@property` |
| **Inheritance** | Class con kế thừa attribute + method từ class cha | `class B(A):`, `super()` |
| **Polymorphism** | Cùng tên method, hành vi khác nhau theo từng class | Method overriding, duck typing |
| **Abstraction** | Interface bắt buộc, ẩn chi tiết implement | `ABC`, `@abstractmethod` |

### Kiến thức chính

- Class = bản thiết kế; Object = thực thể cụ thể tạo từ bản thiết kế
- `__init__(self, ...)` — constructor; `self` là tham chiếu đến object hiện tại
- `__str__` → `print(obj)`; `__repr__` → debug-friendly representation
- `public` / `_protected` / `__private` — 3 mức truy cập

### Bài tập thực hành

- 📝 Xây dựng Animal hierarchy (Dog, Cat, Bird)
- 📝 BankAccount với Encapsulation (`@property`, `_balance`)
- 📝 Abstract Shape system (Circle, Rectangle, Triangle)

---

## Algorithms & Problem Solving

> Linear Search · Binary Search · Bubble Sort · Insertion Sort · Big O

### Kiến thức chính

- **Problem Decomposition** — chia vấn đề thành bước nhỏ trước khi code
- **Linear Search** O(n) — duyệt từng phần tử, dùng cho mọi list
- **Binary Search** O(log n) — list phải sắp xếp trước, rất nhanh với dữ liệu lớn
- **Bubble Sort** O(n²) — đổi chỗ cặp liền kề, dễ hiểu nhất
- **Insertion Sort** O(n²) — tốt hơn Bubble Sort khi mảng gần như đã sắp xếp
- Hiểu thuật toán để: đọc code người khác, phỏng vấn kỹ thuật, tối ưu hóa

### Bài tập thực hành

- 📝 So sánh linear vs binary search — đếm số bước trên 1.000 phần tử
- 📝 Sắp xếp sản phẩm theo giá dùng `insertion_sort`

---

## Milestone — Mini Library Manager CLI

> Bài Tập Lớn · Phase 1 · Áp dụng toàn bộ kiến thức

### Yêu cầu chức năng

- Đọc file CSV chứa danh sách sách (dùng `csv.DictReader`)
- Class `Book` (OOP + Encapsulation) và class `Library` (composition)
- Tìm kiếm sách theo tên (linear search) và theo năm (binary search)
- Sắp xếp sách theo giá hoặc năm xuất bản, in danh sách format đẹp
- Ghi báo cáo thống kê ra JSON (tổng sách, giá TB, sách đắt nhất)
- Xử lý lỗi khi file không tồn tại (`FileNotFoundError`, `DataError`)

### Kiến thức áp dụng

- Variables · Collections · Functions · File I/O · Exceptions · OOP · Algorithms
