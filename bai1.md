# RÀ SOÁT TỔNG HỢP BẢN THẢO SRS RIKKEISHOP
## Phân hệ: Giỏ hàng & Thanh toán

---

## Bước 1 — Xác định đúng vị trí IEEE 830 cho toàn bộ nội dung/sơ đồ

| Nội dung                                        | Vị trí đề xuất              | Đúng/Sai — vị trí đúng nếu sai |
| ----------------------------------------------- | --------------------------- | ------------------------------ |
| Mục A (định nghĩa "Giỏ hàng")                   | 3.2 Functional Requirements | **Sai** — đúng là **1.3 Definitions, Acronyms, and Abbreviations** (hoặc Appendix Glossary) |
| Mục B (3 yêu cầu chức năng)                     | 3.2 Functional Requirements | **Đúng** |
| Danh sách Actor/Use Case tổng thể               | *(chưa điền)*               | **2.2 Product Functions** hoặc **2.3 User Characteristics** (Overall Description) |
| Sơ đồ Sequence áp mã giảm giá (minh họa REQ-02) | *(chưa điền)*               | **3.2 Functional Requirements** (đặt kèm / minh họa ngay sau REQ-02) |

### Giải thích ngắn gọn vị trí đúng:

- **Định nghĩa "Giỏ hàng"**: Thuộc phần thuật ngữ. Theo IEEE 830, mọi định nghĩa thuật ngữ chuyên môn phải đặt tại **1.3 Definitions, Acronyms, and Abbreviations** (hoặc phụ lục Glossary) để toàn bộ tài liệu sử dụng thống nhất, không đặt lẫn vào Functional Requirements.
- **Danh sách Actor / Use Case tổng thể**: Đây là thông tin mô tả tổng quan hệ thống và người dùng, thuộc **Section 2 – Overall Description** (thường là 2.2 Product Functions hoặc 2.3 User Characteristics). Không đặt trực tiếp vào 3.2 vì 3.2 chỉ chứa các yêu cầu chi tiết có thể kiểm chứng.
- **Sequence Diagram minh họa REQ-02**: Sơ đồ tuần tự dùng để làm rõ hành vi của một yêu cầu chức năng cụ thể → đặt ngay trong **3.2 Functional Requirements**, gắn liền với REQ-02 (hoặc trong phần Supporting Information / Appendix nếu muốn tách riêng, nhưng vị trí ưu tiên vẫn là đi kèm yêu cầu chức năng tương ứng).

---

## Bước 2 — Chuẩn hóa các yêu cầu chức năng theo đặc tính vàng

| Mã     | Đặc tính vàng bị vi phạm                                  | Viết lại đạt chuẩn |
| ------ | --------------------------------------------------------- | ------------------ |
| REQ-02 | **Complete (Đầy đủ)** — Chỉ mô tả trường hợp mã hợp lệ, thiếu xử lý mã không hợp lệ / hết hạn / đã sử dụng | **REQ-02 (viết lại):** Khi khách hàng nhập mã giảm giá:<br>1. Nếu mã hợp lệ, còn hạn và chưa được sử dụng → Hệ thống trừ đúng số tiền giảm giá tương ứng vào tổng hóa đơn và hiển thị thông báo thành công.<br>2. Nếu mã không tồn tại, đã hết hạn hoặc đã được sử dụng → Hệ thống không trừ tiền, hiển thị thông báo lỗi cụ thể tương ứng (ví dụ: "Mã không hợp lệ", "Mã đã hết hạn", "Mã đã được sử dụng"). |
| REQ-03 | **Verifiable (Có thể kiểm chứng)** — "nhanh chóng" và "ổn định" là từ ngữ mơ hồ, không đo lường được | **REQ-03 (viết lại):** Hệ thống phải hoàn tất xử lý thanh toán (từ lúc khách hàng xác nhận đến khi nhận được kết quả thành công/thất bại) trong thời gian ≤ 5 giây với tỷ lệ thành công ≥ 99,5% trong điều kiện tải bình thường (≤ 100 giao dịch đồng thời). |

---

**Ghi chú thêm:**
- REQ-01 đã đạt chuẩn (Complete + Verifiable) nên giữ nguyên.
- Sau khi chuẩn hóa, REQ-02 và REQ-03 đều thỏa mãn cả **Complete** và **Verifiable**, sẵn sàng đưa vào bản SRS chính thức.