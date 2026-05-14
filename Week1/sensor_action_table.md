# Bảng sensor, ý nghĩa và action liên quan

| Sensor          | Ý nghĩa                          | Action liên quan                  |
|-----------------|----------------------------------|-----------------------------------|
| Temperature    | Nhiệt độ không khí trong greenhouse | Bật quạt (giảm nhiệt), cảnh báo  |
| Humidity       | Độ ẩm không khí                  | Bật quạt (lưu thông), cảnh báo   |
| Soil moisture  | Độ ẩm đất                        | Tưới nước (khi khô), cảnh báo    |
| Light          | Cường độ ánh sáng                | Bật đèn (bổ sung sáng), cảnh báo |

## Giải thích
- **Temperature:** Kiểm soát nhiệt độ để tránh quá nóng hoặc lạnh, ảnh hưởng đến sự phát triển cây.
- **Humidity:** Duy trì độ ẩm không khí phù hợp, ngăn ngừa bệnh hại.
- **Soil moisture:** Theo dõi độ ẩm đất để quyết định tưới nước hiệu quả.
- **Light:** Đảm bảo đủ ánh sáng cho quang hợp, sử dụng đèn bổ sung khi cần.

## Ứng dụng MUX
Multiplexer có thể chọn dữ liệu từ các sensors này để xử lý quyết định, ví dụ: MUX 4-to-1 chọn sensor dựa trên select lines để kích hoạt action tương ứng.
