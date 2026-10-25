# DESIGN.md — Lá Xanh (cửa hàng cây cảnh)

> Tài liệu thiết kế chốt cho landing page Lá Xanh — TEC-290.
> Dev và QA bám đúng tài liệu này; mọi màu/font/khối ngoài tài liệu này đều coi là lệch thiết kế.

## 1. Phong cách tham chiếu (duy nhất)

**Tạp chí Kinfolk** — phong cách tạp chí lối sống tối giản của Đan Mạch/Hàn Quốc:
- Tối giản: mỗi khối chỉ có 1 ý chính, không nhồi nhiều cột/nội dung.
- Khoảng trắng lớn: ảnh và chữ "thở" được — khoảng trống là một phần của thiết kế, không phải chỗ thừa.
- Ảnh lớn làm nội dung chính: ảnh chiếm diện tích lớn hơn chữ ở hầu hết các khối.
- Chữ serif thanh lịch cho tiêu đề, bố cục lệch trục nhẹ (tiêu đề và ảnh không căn giữa máy móc), đường kẻ mảnh ngăn khối thay vì hộp viền dày.

CẤM: template thương mại điện tử (giỏ hàng, nút mua ngay, lưới sản phẩm dày đặc), icon stock đủ màu, banner khuyến mãi chớp nháy, bố cục lưới đều tăm tắp không khoảng thở.

## 2. Bảng màu (đúng 6 mã, không dùng màu ngoài bảng)

| Mã | Tên | Vai trò |
|---|---|---|
| `#F5F2EA` | Kem ấm | Nền chính toàn trang; chữ trên nền nhấn đất nung và trên ảnh tối |
| `#EAE3D3` | Kem đậm | Nền khối xen kẽ (khối "Chọn cây theo ánh sáng"), nền thẻ cây, đường kẻ mảnh ngăn khối |
| `#22392B` | Xanh rừng đậm | Chữ chính (tiêu đề + nội dung), nền footer |
| `#5C6B5A` | Xám xanh lá | Chữ phụ: mô tả, ghi chú, nhãn nhỏ, placeholder trong form |
| `#C96F4A` | Đất nung | Điểm nhấn duy nhất: nút CTA, giá cây, nhãn "Cây của tuần", gạch chân liên kết khi rê chuột |
| `#A3B18A` | Xanh sage nhạt | Điểm nhấn phụ: nền nhãn mức ánh sáng, nền vòng tròn số thứ tự mẹo chăm cây, nền khối ảnh khi ảnh lỗi/chưa tải |

Quy tắc dùng màu:
- Mỗi màn hình chỉ xuất hiện 1 điểm nhấn đất nung chính (nút CTA hoặc giá) — không rải đất nung khắp nơi.
- Ảnh phải đồng tông với bảng màu: xanh lá + kem ấm + ánh sáng vàng nhẹ; ảnh tông lạnh xanh dương hoặc quá rực là lệch tông.

## 3. Chữ (typography)

- Font tiêu đề: **Playfair Display** (serif, dùng cho H1/H2/H3 và tên cây nổi bật).
- Font nội dung: **Be Vietnam Pro** (dùng cho đoạn văn, nút, form, ghi chú).
- Nạp font từ Google Fonts, khai báo `font-display: swap`.

Thang kích thước:

| Cấp | Desktop | Mobile (≤768px) | Ghi chú |
|---|---|---|---|
| H1 | 64px / dòng 1.1 | 40px / dòng 1.15 | Chỉ 1 H1 ở hero |
| H2 | 40px / dòng 1.2 | 30px / dòng 1.25 | Tiêu đề mỗi khối |
| H3 | 24px / dòng 1.3 | 20px / dòng 1.35 | Tên cây, tên mẹo |
| Nội dung | 17px / dòng 1.6 | 16px / dòng 1.6 | Đoạn văn chính |
| Nhỏ/ghi chú | 14px / dòng 1.5 | 14px / dòng 1.5 | Giá mẫu, nhãn, chân trang |

- Breakpoint duy nhất: **768px** (trên = desktop, dưới hoặc bằng = mobile).
- Tiêu đề căn trái theo lưới 1200px; chỉ H1 hero được căn trái lệch trục kèm ảnh phủ toàn màn hình.

## 4. Lưới và khoảng cách

- Khung nội dung tối đa **1200px**, lề hai bên 24px (mobile 16px).
- Khoảng cách dọc giữa các khối: **96px desktop / 56px mobile** (padding trên + dưới của khối).
- Khoảng cách giữa tiêu đề khối và nội dung dưới nó: 32px desktop / 24px mobile.
- Bo góc: ảnh và thẻ bo **4px**; nút bo **999px** (dạng viên thuốc) — giữ đúng 2 con số này, không tự thêm kiểu bo khác.

## 5. Bố cục trang (đúng thứ tự 6 khối)

### Khối 1 — Hero (ảnh lớn toàn màn hình)
- Ảnh toàn màn hình (chiều cao 100vh, tối thiểu 640px): một góc cửa hàng ngập nắng — kệ cây xanh nhiều tầng, ánh sáng cửa sổ hắt ngang.
- Lớp chữ phủ ở góc dưới trái: nhãn nhỏ "Cửa hàng cây cảnh — [CẦN BỔ SUNG: khu vực/thành phố]", H1, 1 câu mô tả ngắn, 1 nút CTA đất nung "Đặt lịch tư vấn" trỏ xuống form ở khối 6.
- Dòng địa chỉ + điện thoại dưới nút: để placeholder **[CẦN BỔ SUNG]**.

### Khối 2 — Cây của tuần
- Tiêu đề H2 "Cây của tuần" + nhãn đất nung.
- 3–4 cây tiêu biểu, mỗi cây: ảnh dọc, tên cây (H3), 1 dòng hợp với ai/không gian nào, giá ghi rõ **"Giá mẫu"**.
- Giá mẫu tham khảo (chỉ là giá mẫu, chờ giá thật): Monstera 450.000đ · Bàng Singapore 650.000đ · Lưỡi hổ 180.000đ · Trầu bà treo 150.000đ.
- Không có nút mua/giỏ hàng — chỉ 1 liên kết chữ "Hỏi về cây này" trỏ xuống form khối 6.

### Khối 3 — Chọn cây theo ánh sáng nhà bạn
- Nền khối dùng kem đậm `#EAE3D3` để đổi nhịp.
- 3 mức ánh sáng, mỗi mức 1 cột: **Nhiều nắng trực tiếp** (gần cửa sổ hướng Nam/ban công), **Nắng gián tiếp** (trong phòng sáng, cách cửa sổ 1–2m), **Ít sáng** (góc phòng, hành lang chung cư) — mỗi mức gợi ý 2–3 loại cây phù hợp + 1 ảnh minh họa.
- Nhãn mức ánh sáng nền sage `#A3B18A`, chữ xanh rừng.

### Khối 4 — Chăm cây không khó
- 3 mẹo ngắn, đánh số 01/02/03 trong vòng tròn nền sage: tưới theo độ khô của đất (không tưới theo lịch cứng), xoay chậu mỗi tuần cho cây đều nắng, lau lá để cây quang hợp tốt.
- Mỗi mẹo tối đa 2 câu — viết như lời khuyên của người bán cây, không viết kiểu sách giáo khoa.

### Khối 5 — Không gian cửa hàng (khối ảnh)
- Lưới ảnh lớn 3 ảnh (tỉ lệ 3:2): góc cửa sổ đầy cây, bàn tư vấn chọn cây, kệ cây để bàn.
- Chỉ 1 câu chú thích ngắn dưới lưới ảnh; khối này chủ yếu để ảnh nói thay chữ.

### Khối 6 — Form liên hệ / đặt lịch tư vấn (CHỈ giao diện) + chân trang
- H2 "Đặt lịch tư vấn chọn cây" + 1 câu nói rõ form chỉ là giao diện mẫu.
- Trường: Họ tên · Số điện thoại · Loại cây quan tâm (ô chọn: cây để bàn / cây nội thất lớn / cây ban công / chưa biết — cần tư vấn) · Thời gian mong muốn · Ghi chú.
- Nút gửi đất nung; khi bấm chỉ hiện dòng cảm ơn tại chỗ (JavaScript `preventDefault`), KHÔNG gửi đi thật, không có backend/thanh toán.
- Chân trang nền xanh rừng `#22392B`, chữ kem: địa chỉ, điện thoại, giờ mở cửa, người phụ trách — tất cả để placeholder **[CẦN BỔ SUNG]**.

## 6. Quy tắc hình ảnh

- Ảnh là nội dung chính: tổng diện tích ảnh trên trang lớn hơn diện tích chữ; hero và khối 5 gần như chỉ có ảnh.
- Chất lượng: ảnh mẫu chất lượng cao (rộng tối thiểu 1600px cho hero, 900px cho ảnh thẻ), nét, không vỡ hạt; mọi ảnh đều khai báo là **ảnh mẫu** trong kết quả bàn giao.
- Tông ảnh: cây xanh dưới **ánh sáng tự nhiên**, nền sáng kem/gỗ nhạt, đồng tông xanh lá với bảng màu. Cấm ảnh tông lạnh, ảnh tối u ám, ảnh chụp flash gắt.
- Tỉ lệ khung chốt: hero **16:9** (cắt phủ toàn màn hình), ảnh cây ở khối 2 **4:5** (dọc), ảnh mức ánh sáng **4:3**, ảnh không gian khối 5 **3:2**. Đặt `object-fit: cover`, không méo ảnh.
- Mọi ảnh có `onerror` dự phòng: lỗi tải thì hiện nền sage `#A3B18A` kèm tên cây/không gian bằng chữ — không để khung ảnh trống vỡ.

## 7. Dữ liệu mẫu và placeholder (bắt buộc giữ đúng)

- Giá cây: luôn ghi kèm chữ **"Giá mẫu"**; giá thật chờ PO/khách cấp.
- Các mục **[CẦN BỔ SUNG]** (địa chỉ, điện thoại, giờ mở cửa, người phụ trách, khu vực ở hero) giữ nguyên dạng placeholder trên bản demo — Dev/QA không tự bịa số liệu thật.
- Form khối 6 chỉ là giao diện: không nối backend, không thu thập dữ liệu thật.

## 8. Kiểm tra lệch thiết kế (cho QA đối chiếu)

Coi là LỆCH và phải sửa nếu: xuất hiện màu/font ngoài mục 2–3; hero không phải ảnh lớn toàn màn hình; khối nào bị nhồi lưới sản phẩm kiểu sàn thương mại; có nút mua/giỏ hàng/thanh toán; giá không ghi "Giá mẫu"; form gửi dữ liệu đi thật; ảnh lệch tông lạnh hoặc kém rõ.
