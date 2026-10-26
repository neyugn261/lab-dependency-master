# Lab quản lý phụ thuộc và Dependabot

Sinh viên: Nguyễn Quốc Nguyên — MSSV 102230362 — Lớp 23T-DT4.

## Thực hiện cục bộ

```bash
npm ci
npm test
npm pack
npm publish --dry-run --offline
```

`package.json` khai báo `lodash: ^4.17.15`; `package-lock.json` khóa phiên bản thực tế ở 4.17.15 và chứa `integrity`. Phiên bản cũ này được giữ có chủ đích để quan sát cảnh báo bảo mật và quy trình Dependabot. Không dùng cấu hình phụ thuộc này cho sản phẩm thật.

Gói `.tgz` chỉ chứa `index.js` và `package.json` nhờ thuộc tính `files`. Lệnh `npm publish --dry-run --offline` chỉ mô phỏng, không đăng gói lên npm Registry.

Sau khi đẩy dự án lên GitHub, xem `Insights → Dependency graph → Dependabot` và `Settings → Security & analysis` để kiểm tra trạng thái. Tệp `.github/dependabot.yml` cấu hình cập nhật npm hàng tuần và GitHub Actions hàng tháng.
