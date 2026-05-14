# 📚 Domain Scope - MUX trong Hệ thống Số

## 🎯 Domain: Mạch tổ hợp – Multiplexer (MUX)

Multiplexer (bộ dồn kênh) là một **mạch tổ hợp cơ bản** trong kỹ thuật số, có chức năng **chọn một trong nhiều tín hiệu ngõ vào** và truyền tín hiệu đó đến **ngõ ra duy nhất**, dựa trên giá trị của các đường chọn (select lines).

---

## 📋 Phạm vi cụ thể của đề tài

| Thành phần | Mô tả |
|-----------|-------|
| **Cấu trúc MUX** | Phân tích cấu trúc và nguyên lý hoạt động của MUX |
| **Bảng chân trị** | Xây dựng bảng chân trị và biểu thức Boolean |
| **Thiết kế mạch** | Thiết kế mạch MUX 2-to-1 và 4-to-1 |
| **Ứng dụng** | MUX trong việc chọn dữ liệu và thực hiện hàm logic |

---

## ✅ Lý do chọn domain này

### 1️⃣ Tính nền tảng
MUX là **khối xây dựng cơ bản** trong thiết kế mạch số, xuất hiện trong hầu hết các hệ thống số hiện đại
- CPU, GPU, vi điều khiển
- Hệ thống xử lý dữ liệu
- Bộ đếm, lưu trữ

### 2️⃣ Phạm vi rõ ràng
Đề tài có **giới hạn rõ ràng**, không quá rộng, dễ kiểm soát trong thời gian một học kỳ
- Không quá phức tạp
- Có thể hoàn thành trong khung thời gian học tập
- Dễ chia nhỏ thành các bài tập

### 3️⃣ Dễ kiểm chứng
Có thể **mô phỏng và kiểm tra**:
- Phần mềm: Logisim, Proteus
- Kiểm tra bằng bảng chân trị
- Xác minh kết quả thực nghiệm

### 4️⃣ Ứng dụng thực tế
**Liên kết trực tiếp** với các hệ thống thực:
- Thiết kế ALU (Arithmetic Logic Unit)
- Bus dữ liệu trong máy tính
- Hệ thống truyền thông
- IoT & Smart Systems (Smart Greenhouse)

### 5️⃣ Tài liệu phong phú
Có **nhiều tài liệu** tham khảo:
- Giáo trình kỹ thuật số quốc tế
- Các paper nghiên cứu
- Mã nguồn mở để học hỏi

---

## 🔒 Giới hạn phạm vi

### ✓ TRONG phạm vi

| Chủ đề | Ví dụ |
|--------|-------|
| **Loại MUX** | MUX 2-to-1, MUX 4-to-1, MUX 8-to-1 |
| **Biểu thức** | Biểu thức Boolean, Karnaugh Map |
| **Ứng dụng** | Chọn dữ liệu, thực hiện hàm logic |
| **Kiểm chứng** | Mô phỏng, bảng chân trị |

### ✗ NGOÀI phạm vi

| Chủ đề | Lý do loại trừ |
|--------|-----------------|
| **DEMUX** | Đảo ngược của MUX, vượt quá phạm vi |
| **Encoder/Decoder** | Hàm khác với MUX |
| **Mạch tuần tự** | Flip-flop, counter là mạch động, không phải tổ hợp |
| **FPGA/ASIC** | Vượt quá phạm vi học tập cơ bản |

---

## 🔗 Liên kết với Agentic RAG & Smart Greenhouse

MUX không chỉ là một thành phần lý thuyết mà còn được áp dụng thực tế:

```
MUX (Chọn kênh dữ liệu)
    ↓
Cảm biến Smart Greenhouse (Temperature, Humidity, Soil Moisture, Light)
    ↓
Agentic RAG (Xác thực & Ra quyết định)
    ↓
Hành động (Bật quạt, tưới nước, bật đèn)
```
