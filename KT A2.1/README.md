# Portfolio CV - Vũ Lê Nhật Khôi

## 1. Tên dự án

**Portfolio CV cá nhân - Vũ Lê Nhật Khôi**

## 2. Mô tả

Website giới thiệu hồ sơ cá nhân dành cho vị trí Frontend Developer. Trang trình bày thông tin giới thiệu, kỹ năng, các dự án tiêu biểu và phương thức liên hệ. Giao diện được xây dựng theo hướng mobile-first, có thể xem trên điện thoại, máy tính bảng và máy tính để bàn.

Đây là website tĩnh, không có máy chủ ứng dụng, cơ sở dữ liệu hoặc bước biên dịch.

## 3. Chức năng

- Điều hướng nhanh đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Hiển thị ảnh đại diện, vai trò và nội dung giới thiệu.
- Trình bày danh sách kỹ năng và các dự án trong bố cục lưới responsive.
- Cung cấp liên kết email và GitHub để liên hệ.
- Hỗ trợ bố cục cho mobile, tablet và desktop; hỗ trợ điều hướng bằng bàn phím.

> Các liên kết "Xem chi tiết" của dự án và liên kết LinkedIn hiện là placeholder (`#`), cần cập nhật thành URL thực tế nếu sử dụng.

## 4. Công nghệ

- **HTML5:** cấu trúc ngữ nghĩa và nội dung trang.
- **CSS3:** giao diện, biến CSS, Flexbox, CSS Grid, media queries và responsive design.
- **Python (tùy chọn):** chạy máy chủ HTTP đơn giản để xem trang cục bộ.
- **Docker và Nginx (tùy chọn):** phục vụ trang tĩnh trong container.

Trang hiện không sử dụng framework JavaScript hoặc thư viện bên ngoài.

## 5. Yêu cầu môi trường

### Để xem trực tiếp

- Trình duyệt hiện đại như Chrome, Edge, Firefox hoặc Safari.
- Không cần cài Node.js, npm hay công cụ build.

### Để chạy máy chủ cục bộ

- Python 3 (khuyến nghị); trên Windows có thể dùng lệnh `py` nếu Python Launcher được cài đặt.
- Hoặc dùng Docker Desktop/Docker Engine nếu chọn cách chạy bằng container.

## 6. Cài đặt

1. Tải hoặc giải nén mã nguồn vào máy. Nếu dự án đã có sẵn trên máy, chuyển đến thư mục chứa `index.html`.
2. Giữ nguyên cấu trúc các tệp cần thiết:

```text
index.html
assets/
	css/
		styles.css
	img/
		avatar.jpg
```

3. Mở `index.html` trực tiếp bằng trình duyệt, hoặc làm theo hướng dẫn chạy máy chủ bên dưới.

## 7. Chạy thử trên Windows

### PowerShell

Mở PowerShell tại thư mục dự án, hoặc chuyển đến thư mục dự án:

```powershell
cd "C:\duong-dan\den\KT A2.1"
py -m http.server 8000
```

Nếu lệnh `py` không khả dụng nhưng Python đã được thêm vào `PATH`, dùng:

```powershell
python -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

## 8. Chạy thử trên macOS

Mở Terminal, chuyển đến thư mục dự án rồi khởi động máy chủ:

```bash
cd "/duong-dan/den/KT A2.1"
python3 -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

## 9. Chạy thử trên Linux

Mở Terminal, chuyển đến thư mục dự án rồi khởi động máy chủ:

```bash
cd "/duong-dan/den/KT A2.1"
python3 -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`. Nếu chưa có Python 3, hãy cài Python 3 bằng trình quản lý gói của bản phân phối Linux đang sử dụng.

## 10. Chạy thử bằng Docker

Cần cài Docker Desktop (Windows/macOS) hoặc Docker Engine (Linux), đồng thời bảo đảm Docker đang chạy. Các lệnh dưới đây mount thư mục dự án ở chế độ chỉ đọc vào Nginx; không cần tạo Dockerfile.

### Windows PowerShell

Chạy lệnh tại thư mục dự án:

```powershell
$projectPath = (Get-Location).Path
docker run --rm --name cv-portfolio -p 8080:80 --mount "type=bind,source=$projectPath,target=/usr/share/nginx/html,readonly" nginx:alpine
```

### macOS hoặc Linux

Chạy lệnh tại thư mục dự án:

```bash
docker run --rm --name cv-portfolio -p 8080:80 --mount "type=bind,source=$(pwd),target=/usr/share/nginx/html,readonly" nginx:alpine
```

Docker sẽ tải image Nginx nếu máy chưa có. Khi container khởi động, mở <http://localhost:8080>. Nhấn `Ctrl+C` trong terminal để dừng và xóa container.

Nếu cổng `8080` đang được sử dụng, đổi phần `-p 8080:80` thành một cổng khác, ví dụ `-p 8081:80`, rồi mở cổng tương ứng trên trình duyệt.

## 11. Cấu hình và kiểm tra

- Không cần tạo tệp cấu hình môi trường hoặc cài dependency.
- Máy chủ Python mặc định dùng cổng `8000`; Docker mặc định dùng cổng máy `8080`.
- Nếu cổng đang được sử dụng, thay số cổng trong lệnh chạy và truy cập đúng địa chỉ tương ứng.
- Kiểm tra trang bằng cách mở trang chủ, bấm các mục điều hướng, xác nhận ảnh đại diện và CSS tải thành công, rồi thử thay đổi kích thước cửa sổ hoặc xem trên thiết bị di động.
- Nếu ảnh đại diện không hiển thị, kiểm tra tệp `assets/img/avatar.jpg` và đường dẫn tương ứng trong `index.html`.

## 12. Thông tin liên hệ

- **Tên:** Vũ Lê Nhật Khôi
- **Email:** [vukhoi200008@gmail.com](mailto:vukhoi200008@gmail.com)
- **GitHub:** [vukhoi200008-gif](https://github.com/vukhoi200008-gif)
- **LinkedIn:** `linkedin.com/in/vulenhatkhoi` (cần cập nhật URL trong `index.html` trước khi sử dụng)
