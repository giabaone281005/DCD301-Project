# Giải thích các Research Questions (RQ) – Đề tài Multiplexer (MUX)

## RQ-07 (Câu hỏi chính)
**Multiplexer (MUX) là gì? Làm thế nào để sử dụng MUX nhằm chọn một trong nhiều tín hiệu đầu vào và đưa ra một ngõ ra duy nhất?**

**Giải thích:**
Câu hỏi này yêu cầu ta hiểu bản chất của mạch MUX – một mạch tổ hợp có nhiệm vụ "chọn lọc" tín hiệu. Trong hệ thống số, nhiều nguồn dữ liệu không thể cùng lúc dùng chung một đường truyền, vì vậy MUX đóng vai trò như một công tắc thông minh, chỉ cho phép một tín hiệu đi qua tại một thời điểm dựa trên tín hiệu điều khiển (select lines).

---

## RQ7.1
**Multiplexer có các thành phần chính nào, bao gồm data inputs, select lines và output?**

**Giải thích:**
- **Data inputs (ngõ vào dữ liệu):** Là các tín hiệu nguồn muốn chọn, ký hiệu D0, D1, D2, ... Dn.
- **Select lines (đường chọn):** Là các bit điều khiển xác định ngõ vào nào được kết nối với ngõ ra. Số lượng select lines = log₂(số ngõ vào).
- **Output (ngõ ra):** Là tín hiệu duy nhất được xuất ra, bằng giá trị của ngõ vào được chọn.

Hiểu rõ ba thành phần này là nền tảng để thiết kế và phân tích bất kỳ mạch MUX nào.

---

## RQ7.2
**Với MUX 4-to-1, các đường chọn S1 và S0 quyết định ngõ vào được chọn như thế nào?**

**Giải thích:**
MUX 4-to-1 có 4 ngõ vào (D0–D3) và 2 đường chọn (S1, S0). Tổ hợp của S1 và S0 xác định ngõ vào được chọn theo bảng sau:

| S1 | S0 | Ngõ vào được chọn |
|----|----|--------------------|
| 0  | 0  | D0                 |
| 0  | 1  | D1                 |
| 1  | 0  | D2                 |
| 1  | 1  | D3                 |

Câu hỏi này yêu cầu ta hiểu cách viết biểu thức Boolean và bảng chân trị cho MUX 4-to-1.

---

## RQ7.3
**Multiplexer có thể được ứng dụng như thế nào trong việc chọn dữ liệu trong hệ thống số?**

**Giải thích:**
Câu hỏi này mở rộng sang ứng dụng thực tế:
- **Bus dữ liệu:** Chọn nguồn dữ liệu nào được ghi vào thanh ghi hoặc bộ nhớ.
- **Truyền thông đa kênh:** Gộp nhiều tín hiệu truyền qua một đường duy nhất (time-division multiplexing).
- **Thực hiện hàm logic:** Dùng MUX để hiện thực hóa bất kỳ hàm Boolean nào bằng cách nạp giá trị hàm vào các ngõ vào dữ liệu.
- **Thiết kế ALU/CPU:** Chọn toán hạng hoặc kết quả phép tính phù hợp.
