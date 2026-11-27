---
name: thuypd-site-stripe-design-system
source: https://github.com/VoltAgent/awesome-design-md/tree/main/design-md/stripe
description: Design system chuẩn Stripe dành cho hệ sinh thái THUYPD.SITE (Landing Page & Admin CMS Portal). Xây dựng trên nền trắng sáng #ffffff / #f6f9fc, mực navy sâu #0d253d, điểm nhấn indigo #533afd, viền hairline 1px #e3e8ee, lưới chuyển sắc atmospheric trên Hero, số liệu tabular-nums và nút pill gọn gàng.
---

# DESIGN.md — THUYPD.SITE (Stripe Design System)

Tài liệu quy chuẩn UI/UX duy nhất cho **THUYPD.SITE** (`thuypd.site` & `admin.thuypd.site`), áp dụng chuẩn thiết kế **Stripe** từ `VoltAgent/awesome-design-md`.

## 1. Bảng Màu (Color Tokens)

### Light Surface (Landing Page & Admin Light Mode)
| Token | Giá trị | Vai trò |
|---|---|---|
| `canvas` | `#ffffff` | Nền chính các khối nội dung & card nổi |
| `canvas-soft` | `#f6f9fc` | Nền xen kẽ nhẹ nhàng, nền dashboard Admin |
| `ink` | `#0d253d` | Tiêu đề chính, văn bản quan trọng độ tương phản cao |
| `ink-secondary` | `#273951` | Nội dung mô tả, đoạn văn |
| `ink-mute` | `#64748d` | Nhãn phụ, chú thích, metadata |
| `primary` | `#533afd` | CTA chính, liên kết nhấn mạnh, focus ring |
| `primary-deep` | `#4434d4` | Hover của nút chính & text trên badge indigo nhạt |
| `primary-press` | `#2e2b8c` | Trạng thái nhấn (active) |
| `primary-soft` | `#eef2ff` | Nền badge / tag / sidebar active |
| `hairline` | `#e3e8ee` | Viền mảnh 1px phân tách card, bảng, header, footer |
| `hairline-input` | `#a8c3de` | Viền input trạng thái mặc định |
| `success` | `#0f9d58` | Trạng thái thành công / khả dụng |
| `ruby` | `#ea2261` | Cảnh báo lỗi / trạng thái hủy |

### Dark Surface (Admin Dark Mode)
| Token | Giá trị | Vai trò |
|---|---|---|
| `canvas-dark` | `#0a101d` | Nền chính dashboard dark mode |
| `card-dark` | `#11192c` | Nền card / modal / sidebar dark mode |
| `ink-dark` | `#f8fafc` | Tiêu đề & text chính trên nền tối |
| `muted-dark` | `#94a3b8` | Text phụ trên nền tối |
| `primary-dark` | `#6b5afd` | Nút & focus ring dễ đọc trên nền tối |
| `hairline-dark` | `#222d42` | Viền 1px trên nền tối |

## 2. Typography & Số Liệu

- **Font chữ**: `Be Vietnam Pro` (hỗ trợ đầy đủ dấu tiếng Việt), `font-feature-settings: "ss01"` áp dụng toàn trang.
- **Tiêu đề Hero & Section**: Tight negative tracking (`-0.025em` đến `-0.03em`), `text-wrap: balance`, tránh chữ hoa toàn bộ rườm rà.
- **Số liệu tiền tệ, KPI, bảng biểu**: Bắt buộc dùng `font-variant-numeric: tabular-nums` (`font-feature-settings: "tnum"`). Định dạng giá tiền chuẩn Việt Nam qua `Intl.NumberFormat('vi-VN')`.

## 3. Hình Khối, Viền & Bóng Đổ

- **Buttons (Landing Page)**: Dạng pill (`rounded-full`) với padding tối thiểu `px-5 py-2.5` (cao >= 40px cho chuẩn chạm).
- **Buttons (Admin CMS)**: Bo gọn `rounded-md` (`6px`), chiều cao thống nhất `h-9` / `h-8`.
- **Cards**: `rounded-xl` (`12px`) hoặc `rounded-lg` (`8px`), viền `1px solid #e3e8ee`, bóng đổ nhẹ `0 1px 2px rgba(13, 37, 61, 0.04), 0 8px 24px -12px rgba(13, 37, 61, 0.08)`.
- **Inputs**: `rounded-md` (`6px`), chiều cao >= `40px` trên Landing (`36px` trên Admin), viền `1px`, chuyển sang `#533afd` khi focus.

## 4. Thành Phần Đặc Trưng (Signature Patterns)

- **Stripe Hero Gradient Mesh**: Lớp nền radial mesh nhẹ (indigo nhạt, sky nhạt, cream ấm mờ) trải trên nền trắng `#ffffff` ở phần Hero — không lạm dụng blur nặng hay vòng ping vô hạn.
- **Composited Product UI Showcase**: Hiển thị trực quan năng lực sản phẩm (PageSpeed 99/100, SEO, Tỷ lệ chuyển đổi) ngay trên Hero bằng các panel trắng viền mảnh.
- **Footer Sáng (`footer-light`)**: Nền `#ffffff` / `#f6f9fc`, viền trên `1px solid #e3e8ee`, bố cục gọn gàng không lặp CTA thừa.

## 5. Nguyên Tắc Bắt Buộc (Do & Don't)

### Nên làm (Do)
- Mỗi section chỉ dùng **1 thiết kế chuẩn duy nhất** — không rẽ nhánh nhiều variant gây phân mảnh.
- Giữ CTA chính và thông điệp giá trị hiển thị ngay trong màn hình đầu tiên (above the fold).
- Tối đa 1 nút `primary` nổi bật trên mỗi vùng hành động; hành động phụ dùng viền mảnh (`outline`) hoặc ghost.
- Mọi thao tác trong Admin (tìm kiếm, lọc, sửa, lưu, xóa) phải trực tiếp, ít bước nhất có thể.

### Không làm (Don't)
- Không dùng hiệu ứng gây giật lag hoặc phô trương (`animate-ping`, `BorderBeam`, `SpotlightCard` theo chuột).
- Không dùng các class không tồn tại trong Tailwind v3 (`shadow-xs`, `shadow-2xs`, `/05`, `/08`, `w-4.5`, `h-13`).
- Không lặp nút Lưu / CTA ở nhiều vị trí cho cùng một hành động.
- Không trả về thành công giả (`success: true`, `isAvailable: true`) khi API lỗi.
