# Portfolio cá nhân - Đinh Bá Thi

## 1. Giới thiệu dự án

Đây là website portfolio cá nhân giới thiệu Đinh Bá Thi, các kỹ năng, dự án tiêu biểu và thông tin liên hệ. Giao diện được xây dựng theo hướng đơn giản, có thể sử dụng trên điện thoại, máy tính bảng và máy tính.

## 2. Chức năng

- Hiển thị phần giới thiệu và ảnh đại diện.
- Điều hướng nhanh đến các mục Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Trình bày danh sách kỹ năng và các dự án tiêu biểu.
- Cung cấp liên kết mạng xã hội và email liên hệ.
- Bố cục responsive, hỗ trợ nhiều kích thước màn hình.

## 3. Công nghệ sử dụng

- HTML5: cấu trúc và nội dung trang.
- CSS3: giao diện, Flexbox, CSS Grid và responsive design.
- Nginx (tùy chọn): phục vụ website trong Docker.

Dự án hiện là website tĩnh, không có backend, cơ sở dữ liệu, thư viện ngoài hoặc bước biên dịch.

## 4. Yêu cầu môi trường

Để mở trực tiếp website:

- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.
- Git (tùy chọn, nếu muốn tải dự án bằng lệnh `git clone`).

Để chạy máy chủ web cục bộ:

- Python 3.

Để chạy bằng Docker:

- Docker Desktop trên Windows hoặc macOS, hoặc Docker Engine trên Linux.
- Kết nối Internet lần đầu để tải image `nginx:alpine`.

## 5. Cài đặt

### Tải mã nguồn

Có thể tải dự án dưới dạng ZIP và giải nén, hoặc dùng Git:

```bash
git clone <URL-repository>
cd <thu-muc-vua-clone>
```

Thay `<URL-repository>` bằng địa chỉ repository thực tế và `<thu-muc-vua-clone>` bằng tên thư mục Git tạo ra. Nếu đã có thư mục dự án trên máy, mở terminal tại thư mục chứa `index.html`.

### Cài đặt theo hệ điều hành

Không cần cài thêm package để chạy website. Nếu muốn dùng máy chủ Python, cài Python 3 từ trang chủ Python hoặc dùng trình quản lý gói của hệ điều hành. Docker là tùy chọn riêng, xem mục 9, “Chạy bằng Docker”.

- **Windows:** cài Python 3 từ python.org và chọn tùy chọn thêm Python vào `PATH`; hoặc cài Docker Desktop nếu dùng Docker.
- **macOS:** cài Python 3 bằng bộ cài từ python.org hoặc Homebrew (`brew install python`); cài Docker Desktop nếu dùng Docker.
- **Linux:** cài Python 3 bằng trình quản lý gói của bản phân phối, ví dụ Ubuntu/Debian: `sudo apt install python3`; cài Docker Engine nếu dùng Docker.

## 6. Cấu hình

Website không yêu cầu file cấu hình, biến môi trường hay thông tin bí mật.

- Nội dung, tiêu đề, liên kết và thông tin liên hệ có thể chỉnh trong `index.html`.
- Màu sắc, khoảng cách và bố cục có thể chỉnh trong `assets/css/styles.css`.
- Ảnh đại diện hiện được tham chiếu bằng `anh ban than.jpg` ở thư mục gốc. Ảnh dự án nằm trong `assets/img/`; nếu đổi tên hoặc di chuyển ảnh, hãy cập nhật đường dẫn tương ứng trong HTML.
- Khi triển khai công khai, hãy thay các liên kết dự án đang để `#` bằng địa chỉ thực tế.

## 7. Chạy thử nhanh

### Mở trực tiếp

Mở file `index.html` bằng trình duyệt. Cách này phù hợp để xem nhanh giao diện.

### Chạy máy chủ cục bộ

Mở terminal tại thư mục dự án, tức thư mục có `index.html`, rồi chạy lệnh theo hệ điều hành:

**Windows PowerShell:**

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có, thử `python -m http.server 8000`.

**macOS:**

```bash
python3 -m http.server 8000
```

**Linux:**

```bash
python3 -m http.server 8000
```

Mở trình duyệt tại [http://localhost:8000](http://localhost:8000). Dừng máy chủ bằng `Ctrl+C` trong terminal.

## 8. Cấu trúc thư mục

```text
.
├── index.html
├── anh ban than.jpg
├── assets/
│   ├── css/
│   │   └── styles.css
│   └── img/
│       ├── anh thanh xuan.jpg
│       ├── anh tt.jpg
│       ├── anh xe.jpg
│       └── goc hoc tap.jpg
└── README.md
```

## 9. Chạy bằng Docker

Docker sẽ chạy Nginx và phục vụ nội dung thư mục dự án tại cổng `8080`. Thực hiện lệnh tại thư mục chứa `index.html`.

**Windows PowerShell (Docker Desktop):**

```powershell
docker run --rm --name portfolio-thi -p 8080:80 --mount "type=bind,source=$($PWD.Path),target=/usr/share/nginx/html,readonly" nginx:alpine
```

**macOS hoặc Linux:**

```bash
docker run --rm --name portfolio-thi -p 8080:80 --mount "type=bind,source=$(pwd),target=/usr/share/nginx/html,readonly" nginx:alpine
```

Mở [http://localhost:8080](http://localhost:8080) để kiểm tra. Nhấn `Ctrl+C` trong terminal để dừng và xóa container. Nếu cổng `8080` đang được sử dụng, đổi phần `8080:80` thành một cổng trống khác, chẳng hạn `8081:80`, rồi mở cổng tương ứng trên trình duyệt.

## 10. Thông tin liên hệ

- **Tác giả:** Đinh Bá Thi
- **Email:** [bathidinh0411@gmail.com](mailto:bathidinh0411@gmail.com)
- **Facebook:** [facebook/Đinh Bá Thi](https://web.facebook.com/do.dinh.585559)
- **TikTok:** [@b.thi_________2008](https://www.tiktok.com/@b.thi_________2008)
