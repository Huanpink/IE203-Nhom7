# 25410262 – Nguyễn Đức Nghĩa

Phần việc được phân công (theo `IE203-Nhom7/Phan cong.md`):
- **Chương 2 – Kiến trúc quy trình nghiệp vụ** + Sơ đồ kiến trúc 10 quy trình
- **Quy trình Quản lý QL1**: Quản lý chuỗi cung ứng & Thu mua nông sản (Phê duyệt NCC)
- **Quy trình Cốt lõi 2**: Xử lý đơn hàng Online & Giao hàng tươi tốc hành

## Cấu trúc thư mục

| Thư mục / File | Nội dung |
|---|---|
| `Chuong_2_Kien_truc_Quy_trinh.docx` | Chương 2 đầy đủ |
| `Kien_truc_10_Quy_trinh/` | Sơ đồ kiến trúc "ngôi nhà" 10 quy trình (.drawio + .png + .svg) |
| `Quy_trinh_Mua_hang_Chuoi_cung_ung/` | **QL1 – Quản lý chuỗi cung ứng & Thu mua nông sản** – BPMN + sơ đồ tổ chức + xương cá + phân tích |
| `Quy_trinh_Don_hang_Online/` | **Quy trình Cốt lõi CL2** – BPMN + phân tích |

## Trạng thái 2 sơ đồ BPMN (đối chiếu rubric)

| Tiêu chí rubric | QL1 – Chuỗi cung ứng & Thu mua | CL2 – Đơn hàng Online |
|---|---|---|
| Số pool | **2** (Farmers Market + Nhà cung cấp) | 1 |
| Số lane | **11** (2 băng) | 6 |
| Cổng điều kiện (XOR) | **18** (ngưỡng quản lý: >7) | **8** (ngưỡng cốt lõi: >5) |
| Split & Join (song song, AND) | **2 cặp** | 1 cặp |
| Sự kiện bắt đầu / kết thúc | 5 / 8 | 1 / 3 |
| Data object (biểu mẫu) | 11 | 4 |
| Luồng thông điệp giữa 2 pool | 10 | — |
| Cạnh đứt / node cô lập | Không (đã kiểm tra bằng script) | Không |

## QL1 – Quản lý chuỗi cung ứng & Thu mua nông sản – ghi chú

Quy trình được xây dựng theo bối cảnh **Farmers Market** (chuỗi thực phẩm tươi),
bám đúng tên quy trình trong `Phan cong.md` và bảng danh mục QL1 ở Chương 2.
Toàn bộ tài liệu chuẩn bên ngoài chỉ dùng để **tham khảo cấu trúc**; không có mã
quy trình hay mã giao dịch của tài liệu tham khảo nào được đưa vào bài — cột
"Hệ thống" chỉ ghi công cụ chung (ERP, Excel, Portal NCC, Lab kiểm nghiệm, Email).

Phạm vi trải đủ 6 giai đoạn: phát sinh nhu cầu → tập hợp & tính nhu cầu ròng →
khảo sát thị trường và tìm nguồn → thẩm định & phê duyệt NCC → đặt hàng →
nhận hàng, kiểm soát chất lượng đầu vào, nhập kho và thanh toán.

Bốn nguồn phát sinh nhu cầu được mô tả riêng ở mục A.4.1: đề nghị cấp hàng của
cửa hàng (theo tồn min–max và sức bán), dự báo ngành hàng theo mùa vụ từ QL3,
số liệu bù hụt từ CL3, và nhu cầu hàng mới / thay thế nguồn.

## Cấu trúc file phân tích QL1

Bám theo cách trình bày thống nhất trong nhóm (tham khảo bố cục file của Hữu Huy),
file Word gồm 3 phần:

**1. Quy trình QL1** — sơ đồ tổng quan 12 bước + mô tả từng bước.

**2. Mô hình hoá quy trình**
- 2.1 Phương pháp thực hiện: Dựa trên bằng chứng · Mô tả quy trình theo từng
  nhánh · Sơ đồ tổ chức · Kế hoạch làm việc (ngày / tuần–tháng–quý) ·
  Công nghệ hỗ trợ · Biểu mẫu & chứng từ (5 biểu mẫu) · Phỏng vấn (10 câu định
  tính + 10 câu định lượng)
- 2.2 Bộ 6 mục: Mục tiêu & Phạm vi · RACI · SIPOC · Bảng bước AS-IS · Sơ đồ BPMN ·
  KPI và điểm nghẽn/rủi ro

**3. Phân tích quy trình**
- 3.1 Định tính: VA/VBA/NVA · Lãng phí (Move–Hold–Overdo) · Các bên liên quan +
  Xương cá (Fishbone)
- 3.2 Định lượng: Xác suất rẽ nhánh 18 cổng điều kiện · Thời gian · Chất lượng ·
  Chi phí

Kết quả định lượng chính (QL1 tính theo 2 kịch bản):

| | QL1 – Kịch bản A (phê duyệt NCC mới) | QL1 – Kịch bản B (đặt lại theo HĐ khung) | CL2 – Đơn hàng Online |
|---|---|---|---|
| Lead time | 23,6 ngày (mục tiêu < 15) | 7,7 ngày | 3,6 giờ (cam kết 2–4h) |
| Hiệu suất chu trình (PCE) | 12,2 % | 10,6 % | 83,2 % |
| Chi phí nhân công / 1 giao dịch | ~3.690.909 đ | ~1.100.568 đ | ~115.600 đ / đơn |
| Lãng phí / 1 đơn hàng | — | ~130.000 đ (11,8 %) | ~20.900 đ (18,1 %) |

Tính theo xác suất rẽ nhánh (80% đơn đi kịch bản B, 20% đi kịch bản A) và cộng
thời gian làm lại kỳ vọng: **lead time kỳ vọng 11,4 ngày · chi phí nhân công kỳ
vọng 1.618.636 đ/đơn**. Quy mô giả định 250 đơn hàng + 8 chu trình phê duyệt NCC
mới mỗi tháng → lãng phí ~32,5 triệu đ/tháng (~390 triệu đ/năm).

## Việc còn lại

- [ ] Đối chiếu lần cuối với rubric trước khi nộp.
- [ ] Huân import lại phần QL1 mới vào file tổng hợp trong `00_TONG_HOP/`
      (bản `Farmers_Market_Bao_cao_Tong_hop_V1.docx` vẫn còn nội dung cũ).
