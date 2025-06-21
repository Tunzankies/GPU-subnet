# Hướng dẫn sử dụng tool GPUv3

## 1. Giới thiệu
Đây là tool hỗ trợ đăng ký, đăng nhập, làm nhiệm vụ và liên kết tài khoản cho dự án GPUv3. Tool hỗ trợ chạy đa luồng, kiểm tra proxy, tự động hóa các tác vụ liên quan đến tài khoản và ví.

## 2. Cấu hình file `config.json`
- `refCode`: Danh sách mã ref (có thể nhiều mã cho nhiều tài khoản)
- `checkProxy`: Bật/tắt kiểm tra proxy trước khi chạy (`true`/`false`)
- `protocol`: Loại proxy sử dụng (`http` hoặc `socks`)
- `numberThread`: Số luồng chạy song song
- `numberRef`: Số lượng ref mỗi lần chạy
- `waitTime`: Thời gian chờ giữa các lần chạy (giây)
- `newData`: Làm mới file data.json khi chạy (`true` sẽ xóa toàn bộ tài khoản cũ)
- `social`: Bật/tắt làm nhiệm vụ X (nên cân nhắc khi bật)
- `draw`: Bật/tắt tự động mở hòm

## 3. Chuẩn bị các file dữ liệu
- `proxy.txt`: Mỗi dòng 1 proxy, định dạng `ip:port:user:pass`
- `accounts.txt`: Mỗi dòng 1 privateKey tài khoản
- `X.txt`: Mỗi dòng 1 `auth_token` của tài khoản X
- `problems.txt`: Mỗi dòng là 1 vấn đề cho câu hỏi "Describe the biggest challenge..." (nên dùng ChatGPT để tạo)
- `solutions.txt`: Mỗi dòng là 1 giải pháp cho câu hỏi "Design your solution..." (nên dùng ChatGPT để tạo)

## 4. Cách chạy tool
### Trên Windows
Chạy file `gpu.exe` sau khi đã chỉnh config.

### Trên Linux
Chạy lệnh `./gpu` sau khi đã chỉnh config.

## 5. Các chế độ hoạt động
### 1. Đăng ký tài khoản
- Tạo tài khoản mới, xuất ra file `accounts-<dd-MM-yyyy>.txt` và `accounts-<dd-MM-yyyy>.xlsx`

### 2. Đăng nhập
- Sử dụng tài khoản trong `accounts.txt` để đăng nhập, xuất ra file `data.json`

### 3. Làm nhiệm vụ
- Sử dụng tài khoản trong `data.json` để làm nhiệm vụ
- Xuất dữ liệu ra các file: `dApp.json`, `dApp.xlsx`, `solWallet.json`, `solWallet.xlsx`

### 4. Liên kết X
- Sử dụng tài khoản trong `data.json` để liên kết X (cần có `auth_token`)
- Xuất ra file `X.json`, `bindData.xlsx`

## 6. Lưu ý
- Đảm bảo đã chỉnh sửa đúng các file cấu hình và dữ liệu trước khi chạy.
- Các file xuất ra sẽ có định dạng ngày tháng năm hiện tại (`dd-MM-yyyy`).
- Khi bật chế độ làm nhiệm vụ X, hãy tự chịu trách nhiệm nếu bị kiểm tra sybill.

---
Mọi thắc mắc vui lòng liên hệ admin hoặc tham khảo thêm tài liệu đi kèm. 