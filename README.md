# Smart Home Frontend

Giao diện web cho hệ thống nhà thông minh — theo dõi cảm biến, điều khiển thiết bị từ xa qua trình duyệt.

## Tech Stack

| Layer        | Công nghệ                |
| ------------ | ------------------------ |
| Framework    | React 19                 |
| Build tool   | Vite 6                   |
| Routing      | React Router DOM 7       |
| HTTP Client  | Axios                    |
| Linting      | ESLint 9                 |
| Formatting   | Prettier                 |

## Cài đặt & Chạy local

```bash
# 1. Clone repo
git clone https://github.com/<your-username>/smart-home-frontend.git
cd smart-home-frontend

# 2. Cài dependencies
npm install

# 3. Tạo file .env từ mẫu
cp .env.example .env
# Sửa các giá trị trong .env nếu cần

# 4. Chạy dev server
npm run dev
```

Mở trình duyệt tại `http://localhost:5173`

## Biến môi trường

Xem file `.env.example`:

| Biến                 | Mô tả                          | Mặc định                 |
| -------------------- | ------------------------------- | ------------------------ |
| `VITE_API_BASE_URL`  | URL của backend API             | `http://localhost:5000`  |
| `VITE_APP_TITLE`     | Tiêu đề ứng dụng (tuỳ chọn)    | `Smart Home`             |

## Scripts

| Lệnh             | Mô tả                                |
| ----------------- | ------------------------------------- |
| `npm run dev`     | Chạy dev server (HMR)                |
| `npm run build`   | Build production vào `dist/`          |
| `npm run preview` | Preview bản build                     |
| `npm run lint`    | Kiểm tra lỗi ESLint                  |
| `npm run lint:fix`| Tự động sửa lỗi ESLint               |
| `npm run format`  | Format code với Prettier              |

## Cấu trúc thư mục

```
src/
├── api/               # Axios instance & API services
│   ├── axios.js        # Cấu hình Axios (interceptors, base URL)
│   └── index.js        # Export các API modules
├── assets/             # Hình ảnh, font, static files
├── components/         # Components dùng chung (Button, Card, Modal...)
│   └── layout/         # Layout components (Navbar, Sidebar)
├── contexts/           # React Context providers (Auth, Theme...)
├── hooks/              # Custom hooks (useAuth, useDevices...)
├── pages/              # Các trang chính
│   ├── Login.jsx       # Đăng nhập
│   ├── Dashboard.jsx   # Tổng quan hệ thống
│   ├── Devices.jsx     # Quản lý thiết bị
│   ├── Sensors.jsx     # Dữ liệu cảm biến
│   └── NotFound.jsx    # Trang 404
├── routes/             # Cấu hình routing
│   └── AppRouter.jsx
├── utils/              # Hàm tiện ích
├── App.jsx             # Root component
├── App.css
├── main.jsx            # Entry point
└── index.css
```

## Các màn hình chính

1. **Login** — Đăng nhập / đăng ký tài khoản
2. **Dashboard** — Tổng quan: trạng thái thiết bị, biểu đồ cảm biến
3. **Devices** — Danh sách thiết bị, bật/tắt, thêm/xoá
4. **Sensors** — Biểu đồ nhiệt độ, độ ẩm, ánh sáng theo thời gian
5. **404** — Trang không tìm thấy

## Branch Strategy

| Branch           | Mục đích                                    |
| ---------------- | ------------------------------------------- |
| `main`           | Stable — chỉ merge khi code đã ổn định     |
| `develop`        | Tích hợp — merge feature vào đây trước      |
| `feature/*`      | Branch tính năng (vd: `feature/auth-api`)   |
| `fix/*`          | Branch sửa lỗi (vd: `fix/login-bug`)       |

**Quy ước:**
- Không push thẳng vào `main`
- Làm việc trên branch riêng → merge vào `develop` → ổn định → merge `main`
- Tạo Pull Request để review trước khi merge

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
