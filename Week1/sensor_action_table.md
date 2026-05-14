# Bảng Sensor, Ý Nghĩa và Action Liên Quan

## Tổng quan Sensors

| # | Sensor | Ký hiệu | Ý nghĩa | Action liên quan | Ưu tiên |
|---|--------|---------|---------|------------------|---------|
| D0 | **Temperature** 🌡️ | T | Nhiệt độ không khí trong greenhouse | Bật quạt (giảm nhiệt), cảnh báo | 🔴 Cao |
| D1 | **Humidity** 💧 | H | Độ ẩm không khí | Bật quạt (lưu thông), cảnh báo | 🟡 Trung bình |
| D2 | **Soil moisture** 🌱 | SM | Độ ẩm đất | Tưới nước (khi khô), cảnh báo | 🔴 Cao |
| D3 | **Light** 💡 | L | Cường độ ánh sáng | Bật đèn (bổ sung sáng), cảnh báo | 🟡 Trung bình |

---

## Chi tiết từng Sensor

### 🌡️ Temperature (Nhiệt độ)
- **Phạm vi bình thường:** 18-28°C cho hầu hết cây trồng
- **Chức năng:** Kiểm soát nhiệt độ để tránh quá nóng hoặc lạnh, ảnh hưởng đến sự phát triển cây
- **Action:**
  - Nếu T > 28°C → **Bật quạt** (giảm nhiệt)
  - Nếu T < 18°C → **Cảnh báo** (quá lạnh)

### 💧 Humidity (Độ ẩm không khí)
- **Phạm vi bình thường:** 60-80% RH (Relative Humidity)
- **Chức năng:** Duy trì độ ẩm không khí phù hợp, ngăn ngừa bệnh hại và khô lá
- **Action:**
  - Nếu H < 60% → **Bật quạt** (lưu thông không khí, tăng độ ẩm)
  - Nếu H > 85% → **Cảnh báo** (nguy cơ bệnh nấm)

### 🌱 Soil Moisture (Độ ẩm đất)
- **Phạm vi bình thường:** 40-60% (tùy loại cây)
- **Chức năng:** Theo dõi độ ẩm đất để quyết định tưới nước hiệu quả
- **Action:**
  - Nếu SM < 30% → **Tưới nước** (đất quá khô)
  - Nếu SM > 70% → **Cảnh báo** (nguy cơ rễ thối)

### 💡 Light (Cường độ ánh sáng)
- **Phạm vi bình thường:** 400-800 μmol/m²/s (PPFD - Photosynthetic Photon Flux Density)
- **Chức năng:** Đảm bảo đủ ánh sáng cho quang hợp, sử dụng đèn bổ sung khi cần
- **Action:**
  - Nếu L < 300 μmol → **Bật đèn** (bổ sung sáng)
  - Nếu L > 1000 μmol → **Cảnh báo** (quá sáng, nguy cơ cháy lá)

---

## Ứng dụng MUX trong Hệ thống

### Cấu trúc MUX 4-to-1

```
Select Lines (S1, S0) → Chọn Sensor → Output (Y) → Action
```

| S1 | S0 | Giá trị | Sensor chọn | Nhân xét |
|----|----|----|------------|----------|
| 0 | 0 | 0 | Temperature 🌡️ | Ưu tiên cao |
| 0 | 1 | 1 | Humidity 💧 | Ưu tiên trung bình |
| 1 | 0 | 2 | Soil Moisture 🌱 | Ưu tiên cao |
| 1 | 1 | 3 | Light 💡 | Ưu tiên trung bình |

### Ví dụ Luồng Hoạt động

1. **Chu kỳ 1:** S1=0, S0=0 → Chọn Temperature → Nếu T > 28°C → Bật quạt
2. **Chu kỳ 2:** S1=0, S0=1 → Chọn Humidity → Kiểm tra độ ẩm
3. **Chu kỳ 3:** S1=1, S0=0 → Chọn Soil Moisture → Nếu SM < 30% → Tưới nước
4. **Chu kỳ 4:** S1=1, S0=1 → Chọn Light → Kiểm tra ánh sáng

---

## Ghi chú quan trọng

⚠️ **Agentic RAG sẽ:**
- Kiểm tra tính hợp lệ của dữ liệu từ MUX
- So sánh với các quy tắc trong tài liệu kỹ thuật
- Phát hiện các dữ liệu bất thường (ví dụ: nhiệt độ bất kỳ nếu MUX chọn sai kênh)
- Đề xuất hành động với độ tin cậy (confidence score)
