# 4EYEWEAR

Website bán mắt kính mô phỏng theo mô hình sàn thương mại điện tử.
Dự án học phần **Marketing số**, **Nhóm 4 MKTSO D26TDK1**.

## Công nghệ

- React 19 + Vite 8 + Tailwind CSS 4
- React Router 7
- Zustand (lưu dữ liệu trên trình duyệt ở Giai đoạn 1-2)
- Recharts (biểu đồ), Lucide (icon)
- Supabase (từ Giai đoạn 3), Vercel (triển khai)

## Chạy trên máy

```bash
npm install
npm run dev
```

Mở địa chỉ hiển thị trong terminal (thường là http://localhost:5173).

## Tài khoản demo

| Vai trò | Email | Mật khẩu |
| --- | --- | --- |
| Khách hàng | khach@4eyewear.demo | demo123 |
| Quản trị viên | admin@4eyewear.demo | admin123 |

Khách hàng vào trang chủ và đặt hàng. Quản trị viên vào `/admin` để quản lý đơn, sản phẩm, danh mục, khách hàng và thống kê.

## Cấu trúc thư mục

```
src/
  components/   Giao diện dùng chung (common, layout, product, order, admin)
  data/         Dữ liệu mẫu: sản phẩm, danh mục, khách, đơn hàng
  hooks/        Hook dùng chung
  pages/        Trang khách hàng (Home, Products, Cart, ...)
  pages/admin/  Trang quản trị
  store/        Trạng thái ứng dụng (Zustand)
  utils/        Định dạng tiền tệ, ngày tháng, thống kê sự kiện
public/products/  Ảnh minh họa sản phẩm
```

## Trạng thái các giai đoạn

- [x] Giai đoạn 1-2: khung dự án, giao diện khách hàng và quản trị, dữ liệu mẫu, luồng đặt hàng chạy trên trình duyệt.
- [ ] Giai đoạn 3: Supabase, tạo bảng và phân quyền RLS.
- [ ] Giai đoạn 4: đăng nhập thật, giỏ hàng và đơn hàng lưu trên server.
- [ ] Giai đoạn 5: quản trị đọc ghi trực tiếp từ database, thống kê, kiểm thử bảo mật.
- [ ] Giai đoạn 6: đưa lên GitHub, triển khai Vercel, tài liệu bàn giao.

## Lưu ý về dữ liệu

- Ảnh sản phẩm là **ảnh minh họa** do nhóm tự tạo cho bản demo, không phải ảnh sản phẩm thật.
- Hiện tại dữ liệu (sản phẩm, đơn hàng, tài khoản) chỉ lưu trên trình duyệt. Trong trang quản trị có nút **Khôi phục dữ liệu demo** để làm lại từ đầu.
- Không có cổng thanh toán thật. Đơn hàng dùng phương thức COD mô phỏng.
- Biểu đồ lưu lượng truy cập là dữ liệu mẫu để minh họa. Trang **Thống kê Marketing** ghi nhận hành vi thật trên trình duyệt đang dùng.
- Đây là dự án học tập, không phục vụ kinh doanh thực tế.

## Biến môi trường (từ Giai đoạn 3)

Tạo file `.env.local` từ `.env.example` và điền giá trị Supabase:

```
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=
```

Không đưa `.env.local` lên GitHub. Không bao giờ đặt `service_role` key vào mã frontend.

## Triển khai Vercel

1. Đưa mã lên GitHub.
2. Trên Vercel, chọn **Add New Project**, chọn repo vừa đưa lên.
3. Vercel tự nhận diện Vite. Build command: `npm run build`, thư mục output: `dist`.
4. Thêm các biến môi trường ở bước trên trong phần Settings của project.

File `vercel.json` đã cấu hình để tải lại trang (F5) ở đường dẫn con như `/products/p1` không bị lỗi 404.

---

Dự án học tập, không phục vụ kinh doanh thực tế.
