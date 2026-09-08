# ReStoreApp

Ứng dụng Flutter hỗ trợ người dùng đăng bán, tìm kiếm và trao đổi hàng hoá đã qua sử dụng. Dự án dùng Firebase cho các chức năng như xác thực, cơ sở dữ liệu và thông báo.

## Công nghệ

- Flutter & Dart (SDK Dart `^3.8.1`)
- Firebase: Authentication, Cloud Firestore, Cloud Messaging
- GetX
- Google Sign-In

## Tính năng chính

- Đăng ký, đăng nhập và đăng nhập Google
- Hồ sơ người dùng
- Đăng, xem, tìm kiếm và lọc sản phẩm
- Thương lượng/đề xuất giá và quản lý giao dịch
- Thông báo đẩy
- Quyền truy cập vị trí và chọn ảnh khi cần thiết

## Yêu cầu trước khi chạy

- [Flutter SDK](https://docs.flutter.dev/get-started/install/windows) đã được thêm vào `PATH`
- Android Studio (để tạo Android Emulator) hoặc một điện thoại Android bật USB debugging
- VS Code cùng hai extension: **Flutter** và **Dart**
- Một Firebase project đã được cấu hình cho Android. File `android/app/google-services.json` phải tồn tại và khớp application ID của dự án.

Kiểm tra môi trường bằng:

```powershell
flutter doctor
```

Các mục Android toolchain và Android Studio nên có dấu tick xanh. Nếu Flutter yêu cầu chấp nhận license, chạy:

```powershell
flutter doctor --android-licenses
```

## Chạy bằng Android Emulator trong VS Code

### 1. Tạo và khởi động máy ảo trong Android Studio

1. Mở **Android Studio** → **More Actions** → **Virtual Device Manager**.
2. Chọn **Create device**, chọn một thiết bị (ví dụ Pixel 6), rồi chọn một system image có Google APIs.
3. Hoàn tất để tạo AVD, sau đó bấm nút ▶ cạnh máy ảo để khởi động.
4. Đợi màn hình Android hiện hoàn chỉnh.

### 2. Mở dự án trong VS Code

Mở đúng thư mục gốc `TradeUpApp` (thư mục chứa `pubspec.yaml`), rồi mở Terminal trong VS Code và chạy:

```powershell
flutter pub get
flutter devices
```

Lệnh `flutter devices` phải hiển thị emulator đang chạy. Sau đó chạy ứng dụng bằng một trong hai cách:

**Cách 1 — VS Code:** nhấn `F5`, chọn Android emulator tại thanh trạng thái nếu VS Code hỏi chọn thiết bị.

**Cách 2 — Terminal:**

```powershell
flutter run
```

Khi app đang chạy, nhấn `r` trong terminal để hot reload hoặc `R` để hot restart.

### Nếu VS Code không thấy emulator

1. Bảo đảm emulator đang chạy từ Device Manager.
2. Đóng/mở lại terminal VS Code, rồi chạy `flutter devices`.
3. Chạy `flutter doctor` và xử lý các mục có dấu `X` hoặc `!`.
4. Trong VS Code, dùng Command Palette (`Ctrl+Shift+P`) → **Flutter: Select Device** → chọn emulator.

## Cài đặt dự án

```powershell
git clone https://github.com/NTMTriett/ReStoreApp.git
cd ReStoreApp
flutter pub get
flutter run
```

## Cấu trúc chính

```text
lib/
├── constants/      # Hằng số, màu sắc và cấu hình dùng chung
├── firebase/       # Dịch vụ/cấu hình Firebase
├── models/         # Các model dữ liệu
├── screens/        # Các màn hình của ứng dụng
├── widgets/        # Widget tái sử dụng
└── main.dart       # Điểm khởi chạy ứng dụng

assets/
├── fonts/          # Phông chữ Roboto
└── images/         # Ảnh, icon và tài nguyên giao diện
```

## Lệnh hữu ích

```powershell
flutter analyze
flutter test
flutter clean
flutter pub get
```

## Lưu ý bảo mật

Không commit khóa bí mật, token hay file cấu hình Firebase của môi trường production lên repository công khai.
