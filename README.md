# [Thực hành] Tạo menu dọc (Vertical Dropdown Menu)

## 📌 Giới thiệu & Mục tiêu
Bài thực hành kỹ thuật tạo **trình đơn dọc thả xuống (Vertical Dropdown Menu)** đa cấp hoàn toàn bằng **HTML & CSS thuần**:
- Hiểu và ứng dụng thành thạo mối quan hệ định vị `position: relative` (phần tử cha) và `position: absolute` (danh sách con).
- Ẩn/hiện nội dung động không cần JavaScript thông qua bộ chọn `visibility: hidden` và pseudo-class `:hover`.
- Chuẩn hóa reset CSS (`margin`, `padding`, `box-sizing`) để menu hiển thị nhất quán trên mọi trình duyệt.

---

## 🛠️ Nguyên lý hoạt động của CSS Menu dọc

1. **Vùng chứa chính (`#menu`)**:
   - Sử dụng thẻ `div` với `id="menu"` bọc các danh sách không có thứ tự lồng nhau (`<ul>`, `<li>`).
2. **Định dạng phần tử trong danh sách (`li`)**:
   - `list-style: none;`: Loại bỏ dấu chấm bullet mặc định của danh sách.
   - `position: relative;`: Đặt làm mốc tọa độ tương đối cho các menu con bên trong.
   - `width: 180px;` & `height: 38px;`: Cố định kích thước cho mỗi mục menu.
   - `padding: 0 16px;`: Tạo khoảng cách lề trong hai bên cho văn bản.
   - `background-color: #1a1a1a;`: Màu nền đen theo yêu cầu bài thực hành.
   - `line-height: 38px;`: Căn giữa chữ theo chiều dọc.
   - `cursor: pointer;`: Chuyển con trỏ chuột sang hình bàn tay khi tương tác.
3. **Định dạng liên kết (`a`)**:
   - `text-decoration: none;`: Bỏ gạch chân mặc định của thẻ liên kết.
   - `color: #ffffff;`: Đổi màu chữ sang trắng tương phản trên nền tối.
4. **Hiệu ứng Hover (`li:hover`)**:
   - `background-color: #007bff;`: Đổi màu nền sang màu xanh nổi bật khi di chuột qua.
5. **Định dạng menu con (`ul ul`)**:
   - `position: absolute;`: Cố định vị trí menu con so với menu cha tương ứng.
   - `top: 0;`: Căn đỉnh ngang bằng với mục cha.
   - `left: 180px;`: Đặt menu con xuất hiện ngay sát cạnh phải của mục cha.
   - `visibility: hidden;`: Ẩn menu con ở trạng thái mặc định.
6. **Kích hoạt hiển thị (`li:hover > ul`)**:
   - `visibility: visible;`: Cho phép menu con xuất hiện ngay khi rê chuột vào mục cha tương ứng.

---

## 📂 Cấu trúc thư mục dự án

```
vertical-dropdown-menu/
├── index.html          # Trang HTML chứa cấu trúc menu dọc đa cấp (cấp 1, 2, 3)
├── style.css           # Mã nguồn CSS định dạng và điều khiển hiển thị dropdown
├── .gitignore          # Cấu hình bỏ qua file rác hệ thống
└── README.md           # Tài liệu hướng dẫn và giải thích kỹ thuật
```

---

## 🚀 Hướng dẫn mở và kiểm tra giao diện

1. Clone kho lưu trữ về máy:
   ```bash
   git clone https://github.com/dtc245200862-dot/vertical-dropdown-menu.git
   ```
2. Mở file `index.html` trực tiếp bằng trình duyệt Chrome, Edge hoặc Firefox.
3. Di chuột vào mục **"Khóa học"** để thấy menu cấp 2 trượt sang phải, tiếp tục di chuột vào **"Cơ sở dữ liệu"** để thấy menu cấp 3 xuất hiện trơn tru.
