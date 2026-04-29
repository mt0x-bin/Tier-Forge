# TierForge

Ứng dụng tạo tierlist với drag & drop, lưu ảnh qua ImgBB và sync dữ liệu qua GitHub Gist. Chạy hoàn toàn trên trình duyệt, không cần backend.

## Yêu cầu

- GitHub Personal Access Token (scope: `gist`)
- ImgBB API Key — đăng ký miễn phí tại [imgbb.com](https://imgbb.com)

## Cài đặt

### 1. Fork / clone repo, deploy lên GitHub Pages

### 2. Tạo Bootstrap Gist

Vào [gist.github.com](https://gist.github.com) → tạo một Gist mới bất kỳ → copy ID trong URL:

```
https://gist.github.com/username/ID_Ở_ĐÂY
```

### 3. Hardcode vào `index.html`

```js
const BOOTSTRAP_GIST_ID = 'id_của_bạn';
```

Push lại lên GitHub.

### 4. Setup lần đầu

Vào web → **Owner** → **Lần đầu setup?** → làm 3 bước:

1. Đặt mật khẩu (≥ 6 ký tự)
2. Nhập GitHub PAT + ImgBB API Key
3. Nhập Bootstrap Gist ID → **Mã hóa & Lưu**

Xong. Lần sau chỉ cần nhập mật khẩu trên bất kỳ thiết bị nào.

## Chế độ Guest

Chọn **Guest** → nhập PAT + ImgBB key → dùng ngay. Keys lưu trong localStorage, dữ liệu hoàn toàn tách biệt với Owner.

## Tính năng

- Drag & drop ảnh giữa các tier và pool
- 5 chế độ hiển thị: Square / Landscape / Portrait / Round / No Crop
- Quản lý nhiều tierlist
- Chỉnh màu, nhãn, thứ tự từng tier
- Tự động backup localStorage, sync lên Gist khi nhấn 💾
- API keys mã hóa AES-256 (PBKDF2 / 200k iterations)

## Console helpers

```js
_session()           // xem trạng thái session
_testDecrypt("pass") // kiểm tra giải mã bootstrap Gist
```
