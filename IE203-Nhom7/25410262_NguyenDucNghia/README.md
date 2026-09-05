# 25410262 – Nguyễn Đức Nghĩa

Phần việc được phân công (theo `IE203-Nhom7/Phan cong.md`):
- **Chương 2 – Kiến trúc quy trình nghiệp vụ** + Sơ đồ kiến trúc 10 quy trình
- **Quy trình Quản lý**: Mua hàng & Quản lý chuỗi cung ứng
- **Quy trình Cốt lõi 2**: Xử lý đơn hàng Online & Giao hàng tươi tốc hành

## Cấu trúc thư mục

| Thư mục / File | Nội dung |
|---|---|
| `Chuong_2_Kien_truc_Quy_trinh.docx` | Chương 2 đầy đủ |
| `Kien_truc_10_Quy_trinh/` | Sơ đồ kiến trúc "ngôi nhà" 10 quy trình (.drawio + .png + .svg) |
| `Quy_trinh_Mua_hang_Chuoi_cung_ung/` | **Quy trình Quản lý** – BPMN + phân tích |
| `Quy_trinh_Don_hang_Online/` | **Quy trình Cốt lõi CL2** – BPMN + phân tích |

## Trạng thái 2 sơ đồ BPMN (đối chiếu rubric)

| Tiêu chí rubric | Mua hàng & CCU | Đơn hàng Online |
|---|---|---|
| Cổng điều kiện | **11** (ngưỡng quản lý: >7) | **8** (ngưỡng cốt lõi: >5) |
| Split & Join (song song) | Có (1 cặp AND) | Có (1 cặp AND) |
| Sự kiện bắt đầu / kết thúc | 2 / 3 | 1 / 3 |
| Data object (biểu mẫu) | 7 | 4 |
| Cạnh đứt / node cô lập | Không | Không |

## Quy trình Mua hàng & Chuỗi cung ứng – ghi chú

Gộp từ 3 quy trình con trong tài liệu tham khảo: **MM.03** (hỏi giá NCC) +
**MM.04** (quản lý hợp đồng) + **MM.05** (mua hàng nội địa). Lý do gộp: 3 quy
trình này vốn tham chiếu lẫn nhau và tạo thành một chuỗi Procure-to-Pay liên tục.

Các bước bổ sung so với 3 ảnh gốc (do ảnh gốc thiếu): kiểm tra hạn mức ngân
sách, gửi PO đã duyệt cho NCC (ME9F), đối chiếu 3 chiều PO–phiếu nhập kho–hoá
đơn, và thực hiện thanh toán (F110).

## Nội dung 2 file phân tích

Mỗi quy trình có 1 file Word gồm 2 phần:

- **Phần A – Bộ 6 mục**: Mục tiêu & Phạm vi · RACI · SIPOC · Bảng bước AS-IS ·
  Sơ đồ BPMN · KPI và điểm nghẽn/rủi ro
- **Phần B – Phân tích quy trình (rubric mục 4)**:
  - Định tính: VA/VBA/NVA · Lãng phí (Move–Hold–Overdo) · Xương cá (Fishbone)
  - Định lượng: Thời gian (lead time, PCE) · Chất lượng · Chi phí

Kết quả định lượng chính:

| | Mua hàng & CCU | Đơn hàng Online |
|---|---|---|
| Lead time | 21,0 ngày (mục tiêu < 15) | 3,6 giờ (cam kết 2–4h) |
| Hiệu suất chu trình (PCE) | 6,1 % | 83,2 % |
| Chi phí nhân công / 1 giao dịch | ~1.674.000 đ / PO | ~115.600 đ / đơn |
| Trong đó lãng phí | ~63.400 đ (3,8 %) | ~20.900 đ (18,1 %) |

## Việc còn lại (chưa làm)

- [ ] Rubric mục 3 – Phỏng vấn: 10 câu định tính + 10 câu định lượng
      (chưa rõ làm theo cá nhân hay cả nhóm — cần hỏi Lead).

## Mở file .drawio

Mở tại https://app.diagrams.net → File → Open From → Device.
