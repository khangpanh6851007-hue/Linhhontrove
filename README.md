# Tùng Phạt Chúng Sinh 9.0

Ứng dụng web HTML/CSS/JavaScript thuần, giao diện tiếng Việt. Bản hiện tại chạy trực tiếp trên trình duyệt và lưu dữ liệu demo bằng `localStorage`.

## Tính năng

- Tổng quan điểm phước đức, cấp tu luyện và tiến độ.
- Hệ thống 10.000 cấp tu luyện.
- 1.000 danh hiệu và 1.000 thần khí.
- Ghi sổ thiên phạt, hoàn tác và nhật ký.
- Bang hội, chiến tranh mô phỏng, chợ demo, thành viên, bảng xếp hạng và chat cục bộ.
- Sao lưu/khôi phục dữ liệu JSON.
- Khu vực quản trị demo: đăng nhập bằng PIN và thay đổi PIN có xác nhận.

## Chạy trên máy

1. Đặt `index.html` ở thư mục gốc của repository.
2. Mở `index.html` bằng trình duyệt hiện đại.

Không cần cài Node.js hoặc chạy lệnh build.

## Đưa website lên GitHub Pages

1. Tạo repository trên GitHub.
2. Đặt file HTML phiên bản mới đã sửa PIN thành `index.html` ở thư mục gốc repository.
   - Nếu đang dùng file `index_fixed_pin.html`, hãy đổi tên file đó thành `index.html`.
3. Thêm workflow tại `.github/workflows/deploy.yml` (file này đã có trong gói).
4. Push các thay đổi lên nhánh `main`.
5. Vào **Settings → Pages** và chọn **GitHub Actions** làm Build and deployment source.
6. Mở tab **Actions** để theo dõi workflow `Deploy static site to GitHub Pages`.
7. Khi workflow thành công, địa chỉ website sẽ hiển thị trong phần **Settings → Pages**.

Các lần push tiếp theo lên `main` sẽ tự động triển khai lại website. Có thể chạy thủ công bằng **Actions → Deploy static site to GitHub Pages → Run workflow**.

## Cấu trúc

```text
.
├── index.html
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml
```

## Lưu ý quan trọng về dữ liệu và bảo mật

- Đây là ứng dụng frontend demo. Dữ liệu `localStorage` chỉ nằm trên trình duyệt/thiết bị hiện tại; không tự đồng bộ giữa người dùng hoặc thiết bị.
- Chat, bảng xếp hạng, bang hội, chợ và chiến tranh hiện là mô phỏng cục bộ, chưa phải dịch vụ liên server.
- PIN quản trị hiện được lưu ở phía trình duyệt. Không dùng cơ chế này để bảo vệ dữ liệu hoặc chức năng nhạy cảm trên website công khai.
- Không đưa mật khẩu, khóa API, thông tin cá nhân nhạy cảm hoặc bí mật vào mã nguồn công khai.
- Muốn có tài khoản thật, phân quyền an toàn, đồng bộ dữ liệu và tính năng realtime, cần bổ sung backend cùng cơ chế xác thực phía máy chủ.

## Giấy phép

Chưa chỉ định giấy phép. Nếu muốn cho phép người khác sử dụng hoặc chỉnh sửa mã nguồn, hãy thêm tệp `LICENSE` phù hợp.
