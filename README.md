# Money Flow: Sổ Thu Chi

Ứng dụng quản lý thu chi cá nhân dạng PWA, chạy offline và cài được lên iPhone.

## Tính năng
- Quản lý nhiều ví, ghi thu, chi và chuyển ví
- Số dư đầu tháng tự động chuyển từ tháng trước
- Xem số dư dự kiến 3 tháng tới, chỉ tính từ dữ liệu đã nhập: giao dịch sắp tới, giao dịch định kỳ và nợ (không tự ước tính)
- Đổi icon cho từng danh mục thu chi và từng ví (bộ icon có sẵn hoặc tự nhập)
- Chọn tháng nhanh bằng thanh cuộn ngang
- Thẻ tổng quan: số dư, đầu tháng, thu, chi, chuyển; chạm vào Thu, Chi hoặc Chuyển để xem chi tiết theo danh mục và theo ngày
- Danh sách giao dịch nhóm theo ngày, hiển thị tổng chi của từng ngày
- Giao dịch định kỳ, ngân sách, theo dõi nợ
- Mục tiêu tiết kiệm: chọn ví để góp (trừ tiền khỏi ví) hoặc rút (cộng lại vào ví), có lịch sử từng lần góp
- Biểu đồ thu chi và diễn biến số dư
- Biểu đồ phân tích chi tiêu: tỷ trọng theo danh mục, chi từng ngày, chi theo thứ trong tuần, so với tháng trước, 5 khoản chi lớn nhất
- Sao lưu, khôi phục và xuất CSV

## Nội dung gói
`index.html` (ứng dụng), `sw.js` (chạy offline), `manifest.webmanifest`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`

## Cài đặt

### Cách 1: Cài qua Safari (không cần Mac)
1. Đưa toàn bộ file trong thư mục lên một dịch vụ host tĩnh có HTTPS (Netlify Drop, GitHub Pages hoặc Cloudflare Pages).
2. Mở đường dẫn bằng **Safari** trên iPhone.
3. Chọn **Chia sẻ** > **Thêm vào Màn hình chính**.

### Cách 2: Đóng gói app iOS (cần Mac và Xcode)
```
mkdir sothuchi && cd sothuchi
npm init -y
npm i @capacitor/core @capacitor/cli @capacitor/ios
npx cap init "Money Flow" com.tenban.sothuchi --web-dir=www
mkdir www   # chép toàn bộ file của gói vào www
npx cap add ios
npx cap sync
npx cap open ios
```
- Apple ID miễn phí: app hết hạn sau 7 ngày, cần cài lại.
- Phát hành TestFlight hoặc App Store: cần tài khoản Apple Developer (99 USD/năm).
- Biểu tượng app: thay `icon-512.png` trong Xcode (Assets > AppIcon).

## Dữ liệu
- Dữ liệu lưu cục bộ trên thiết bị, không có tài khoản hay đồng bộ giữa các máy.
- Safari và app trên Màn hình chính lưu dữ liệu tách biệt, nên chọn một cách và dùng cố định.
- Sao lưu định kỳ tại **Sao Lưu** > **Xuất File**; khôi phục bằng **Nhập File**.

## Cập nhật
Khi thay đổi `index.html`, tăng tên cache trong `sw.js` (hiện là `sothuchi-v11`) để thiết bị tải bản mới.
