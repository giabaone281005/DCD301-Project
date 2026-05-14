# Giải thích Research Questions (RQ) - MUX & Smart Greenhouse

## Tổng quan

Tài liệu này giải thích chi tiết các Research Questions (RQ) cho **Research Theme 7: Mạch tổ hợp (Multiplexer)**, tập trung vào ứng dụng MUX trong hệ thống số và tích hợp với domain **Smart Greenhouse**.

---

## RQ-07: Multiplexer (MUX) là gì?

**Câu hỏi:** Multiplexer (MUX) là gì? Làm thế nào để sử dụng MUX nhằm chọn một trong nhiều tín hiệu đầu vào và đưa ra một ngõ ra duy nhất?

### Định nghĩa MUX
MUX là mạch logic số dùng để **chọn một trong nhiều tín hiệu đầu vào** (data inputs) và chuyển nó đến một **ngõ ra duy nhất** (output).

### Cách sử dụng
1. Cung cấp tín hiệu đầu vào từ các sensors
2. Thiết lập đường chọn (select lines) để chỉ định đầu vào mong muốn
3. Ngõ ra sẽ phản ánh tín hiệu đã chọn

### Ví dụ thực tế
- **MUX 4-to-1:** Có 4 đầu vào và 2 đường chọn
- **Ứng dụng:** MUX giúp tiết kiệm chân I/O trong hệ thống Smart Greenhouse để chọn dữ liệu từ 4 sensors (Temperature, Humidity, Soil Moisture, Light)

### Ứng dụng trong domain Smart Greenhouse
Trong greenhouse, MUX có thể chọn dữ liệu từ cảm biến nhiệt độ hoặc độ ẩm để xử lý quyết định tự động điều khiển các thiết bị (quạt, bơm tưới, đèn).

---

## RQ7.1: Các thành phần chính của Multiplexer

**Câu hỏi:** Multiplexer có các thành phần chính nào, bao gồm data inputs, select lines và output?

### Data Inputs (Đầu vào dữ liệu)
- Các tín hiệu đầu vào: D0, D1, D2, D3 (cho MUX 4-to-1)
- Mỗi tín hiệu là một bit hoặc bus dữ liệu từ sensors
- **Ví dụ trong Smart Greenhouse:**
  - D0: Dữ liệu từ cảm biến nhiệt độ
  - D1: Dữ liệu từ cảm biến độ ẩm không khí
  - D2: Dữ liệu từ cảm biến độ ẩm đất
  - D3: Dữ liệu từ cảm biến ánh sáng

### Select Lines (Đường chọn)
- Các đường điều khiển: S0, S1, S2, ... (tùy số đầu vào)
- Dùng mã nhị phân để chọn đầu vào
- **Công thức:** 2^n đường chọn cho 2^n đầu vào
  - MUX 4-to-1 → 2 select lines (S1, S0)
  - MUX 8-to-1 → 3 select lines (S2, S1, S0)

### Output (Ngõ ra)
- Một ngõ ra duy nhất: Y
- Phản ánh tín hiệu từ đầu vào đã chọn
- Dùng để đưa ra quyết định (ví dụ: bật quạt)

### Thành phần bổ sung
- **Enable input (EN):** Kích hoạt/vô hiệu hóa mạch
- **Giúp kiểm soát** trong hệ thống greenhouse (tiết kiệm năng lượng)

---

## RQ7.2: Cách Select Lines (S1, S0) hoạt động trong MUX 4-to-1?

**Câu hỏi:** Với MUX 4-to-1, các đường chọn S1 và S0 quyết định ngõ vào được chọn như thế nào?

### Cấu trúc MUX 4-to-1
- **Data inputs:** D0, D1, D2, D3 (4 đầu vào)
- **Select lines:** S1, S0 (2 đường chọn)
- **Output:** Y (1 ngõ ra)

### Bảng Chân lý (Truth Table)

| S1 | S0 | Giá trị | Chọn | Ứng dụng Smart Greenhouse |
|----|----|----|------|---------------------------|
| 0 | 0 | 0 | D0 | Dữ liệu Temperature  |
| 0 | 1 | 1 | D1 | Dữ liệu Humidity  |
| 1 | 0 | 2 | D2 | Dữ liệu Soil Moisture  |
| 1 | 1 | 3 | D3 | Dữ liệu Light |

### Công thức Ngõ ra
$$Y = D[selected]$$
Trong đó: `selected` = giá trị thập phân của nhị phân S1S0

### Ví dụ thực tế
- Nếu S1=0, S0=0 → Y = D0 = dữ liệu từ cảm biến nhiệt độ
- Nếu S1=1, S0=0 → Y = D2 = dữ liệu từ cảm biến độ ẩm đất
- Dữ liệu Y được sử dụng để quyết định action (bật quạt, tưới nước, bật đèn)

---

## RQ7.3: Ứng dụng MUX trong việc chọn dữ liệu trong hệ thống số

**Câu hỏi:** Multiplexer có thể được ứng dụng như thế nào trong việc chọn dữ liệu trong hệ thống số?

### 1️ Chọn kênh dữ liệu
Trong hệ thống đa kênh như **Smart Greenhouse**:
- MUX chọn tín hiệu từ 4 sensors (Temperature, Humidity, Soil Moisture, Light) để xử lý tuần tự
- Xử lý dữ liệu từng sensor một theo chu kỳ

### 2️ Định tuyến dữ liệu
Trong mạch logic (FPGA, ALU):
- MUX chọn nguồn dữ liệu cho phép tính toán linh hoạt
- Ví dụ: Chọn giữa hai sensors để ra quyết định

### 3️ Tiết kiệm tài nguyên
- Giảm chân I/O trong vi điều khiển
- Chia sẻ chân GPIO cho nhiều thiết bị sensors
- Giảm chi phí hardware

### 4️ Ứng dụng cụ thể trong Smart Greenhouse
MUX chọn dữ liệu sensor để kích hoạt actions:

| Sensor | Dữ liệu | Action |
|--------|---------|--------|
| Temperature | > 28°C | Bật quạt (giảm nhiệt) |
| Humidity | < 60% | Bật quạt (lưu thông) |
| Soil Moisture | < 30% | Tưới nước |
| Light | < 300 μmol | Bật đèn (bổ sung) |

---

##  Tóm tắt mối liên hệ giữa RQ

```
RQ-07: MUX là gì? (Định nghĩa cơ bản)
   ↓
RQ7.1: Các thành phần? (Cấu trúc)
   ↓
RQ7.2: Select lines hoạt động? (Chi tiết công nghệ)
   ↓
RQ7.3: Ứng dụng? (Thực tế trong Smart Greenhouse)
```

---

## Ghi chú

- Agentic RAG sẽ sử dụng các kiến thức này để **xác thực tính hợp lệ** của dữ liệu từ MUX
- Nếu MUX chọn sai kênh, dữ liệu sẽ không khớp với expected range → Agent sẽ phát hiện lỗi
- Đây là trung tâm của **Data Quality Module (RQ2)** trong hệ thống Agentic RAG
