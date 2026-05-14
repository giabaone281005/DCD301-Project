# Bảng tín hiệu, ý nghĩa và action liên quan – Đề tài MUX

## Bảng tín hiệu ngõ vào (Data Inputs)

| Tín hiệu | Ký hiệu | Loại | Ý nghĩa |
|---|---|---|---|
| Data Input 0 | D0 | Nhị phân (0/1) | Nguồn dữ liệu kênh 0, được chọn khi S1=0, S0=0 |
| Data Input 1 | D1 | Nhị phân (0/1) | Nguồn dữ liệu kênh 1, được chọn khi S1=0, S0=1 |
| Data Input 2 | D2 | Nhị phân (0/1) | Nguồn dữ liệu kênh 2, được chọn khi S1=1, S0=0 |
| Data Input 3 | D3 | Nhị phân (0/1) | Nguồn dữ liệu kênh 3, được chọn khi S1=1, S0=1 |

## Bảng tín hiệu điều khiển (Select Lines)

| Tín hiệu | Ký hiệu | Loại | Ý nghĩa |
|---|---|---|---|
| Select bit 0 | S0 | Nhị phân (0/1) | Bit điều khiển thấp (LSB), kết hợp với S1 để chọn kênh |
| Select bit 1 | S1 | Nhị phân (0/1) | Bit điều khiển cao (MSB), kết hợp với S0 để chọn kênh |

## Bảng ngõ ra (Output)

| Tín hiệu | Ký hiệu | Loại | Ý nghĩa |
|---|---|---|---|
| Output | Y | Nhị phân (0/1) | Giá trị ngõ ra duy nhất, bằng giá trị Dx được chọn |

---

## Bảng chân trị MUX 4-to-1

| S1 | S0 | D0 | D1 | D2 | D3 | Y |
|----|----|----|----|----|-----|---|
| 0  | 0  | d  | x  | x  | x   | d (= D0) |
| 0  | 1  | x  | d  | x  | x   | d (= D1) |
| 1  | 0  | x  | x  | d  | x   | d (= D2) |
| 1  | 1  | x  | x  | x  | d   | d (= D3) |

*(x = don't care, d = giá trị thực sự của ngõ vào)*

---

## Biểu thức Boolean

```
Y = (S1' · S0' · D0) + (S1' · S0 · D1) + (S1 · S0' · D2) + (S1 · S0 · D3)
```

---

## Bảng Action liên quan đến từng RQ

| RQ | Tín hiệu liên quan | Action / Nhiệm vụ cần thực hiện |
|---|---|---|
| RQ7.1 | D0–D3, S0–S1, Y | Vẽ sơ đồ khối MUX, xác định vai trò từng thành phần |
| RQ7.2 | S1, S0 → D0–D3 → Y | Lập bảng chân trị đầy đủ, viết biểu thức Boolean |
| RQ7.3 | Tất cả | Thiết kế mạch ứng dụng: chọn dữ liệu bus, thực hiện hàm logic |
