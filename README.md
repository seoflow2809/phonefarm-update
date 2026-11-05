# phonefarm-update

Kênh cập nhật tự động cho **PhoneFarm**.

## Cách phát hành bản mới

1. Trong project PhoneFarm, tăng `version` trong `package.json` (ví dụ `0.1.0` → `0.1.1`).
2. Build:
   ```bat
   npm.cmd run dist
   ```
   File ra: `release/PhoneFarm.exe` (hoặc trong thư mục `release`).
3. Trên GitHub repo này → **Releases** → **Create a new release**
   - Tag: `v0.1.1` (trùng version)
   - Upload file `PhoneFarm.exe`
4. Sửa file `update.json` trên nhánh `main`:

```json
{
  "version": "0.1.1",
  "notes": "Mô tả thay đổi cho người dùng",
  "url": "https://github.com/seoflow2809/phonefarm-update/releases/download/v0.1.1/PhoneFarm.exe",
  "mandatory": false
}
```

5. Commit & push `update.json`. App sẽ đọc file này khi mở / khi bấm **Kiểm tra cập nhật**.

## Lưu ý

- Repo nên để **Public** để máy người dùng tải `update.json` và release không cần token.
- Tên file artifact nên là `PhoneFarm.exe` cho đúng URL ở trên.
