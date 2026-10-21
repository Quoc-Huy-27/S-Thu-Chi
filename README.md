# Sổ Thu Chi Của Bạn – gói cài lên iPhone

Gói này gồm: index.html (app), manifest.webmanifest, sw.js (chạy khi mất mạng), 3 file logo con heo.

## Cách 1 (dễ nhất): cài như app qua Safari, không cần Mac
1. Đưa **cả 6 file** (giải nén zip) lên một nơi lưu trữ web miễn phí, đặt chung một thư mục:
   - Netlify Drop: vào https://app.netlify.com/drop, kéo thả thư mục vào, nhận link dạng https://ten-ngau-nhien.netlify.app
   - hoặc GitHub Pages / Cloudflare Pages.
2. Trên iPhone mở link bằng **Safari** > nút Chia sẻ > **Thêm vào Màn hình chính**.
3. Mở từ biểu tượng con heo trên Màn hình chính: app chạy toàn màn hình, dùng được cả khi mất mạng.

## Cách 2: đóng gói thành app iOS thật (cần máy Mac + Xcode)
```
mkdir sothuchi && cd sothuchi
npm init -y
npm i @capacitor/core @capacitor/cli @capacitor/ios
npx cap init "Sổ Thu Chi" com.tenban.sothuchi --web-dir=www
mkdir www        # chép 6 file của gói này vào thư mục www
npx cap add ios
npx cap sync
npx cap open ios # mở Xcode, chọn iPhone của bạn rồi bấm Run
```
- Chạy trên iPhone của chính bạn: dùng Apple ID miễn phí, app hết hạn sau 7 ngày và phải cài lại.
- Đưa lên App Store hoặc TestFlight: cần tài khoản Apple Developer (99 USD/năm).
- Logo trên iOS: thay ảnh trong Xcode (Assets > AppIcon) bằng icon-512.png.

## Lưu ý về dữ liệu
- Dữ liệu lưu ngay trong máy (bộ nhớ của trình duyệt/app), không lên mạng. Không có tài khoản hay đồng bộ giữa các máy.
- Hãy dùng thẻ **Sao Lưu** > **Xuất File** định kỳ. Khi đổi máy hoặc cài lại, bấm **Nhập File** để khôi phục.
- Mở bằng Safari và mở từ biểu tượng Màn hình chính lưu dữ liệu tách nhau. Chọn một cách và dùng cố định.
