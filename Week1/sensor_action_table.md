# Bảng sensor, ý nghĩa và action liên quan

| Sensor | Ý nghĩa | Action liên quan |
|---|---|---|
| Temperature | Nhiệt độ không khí trong nhà kính | Bật/tắt quạt, bật/cản nhiệt, cảnh báo nhiệt độ cao/thấp |
| Humidity | Độ ẩm không khí | Bật/tắt máy sưởi ẩm/giảm ẩm, bật quạt, cảnh báo môi trường ẩm ướt |
| Soil moisture | Độ ẩm đất | Tưới nước, dừng tưới, cảnh báo đất khô |
| Light | Cường độ ánh sáng | Bật đèn bổ sung, điều chỉnh rèm che, cảnh báo thiếu sáng |

## Giải thích từng sensor
- Temperature: kiểm soát điều kiện nhiệt để cây không quá nóng hoặc quá lạnh.
- Humidity: độ ẩm không khí ảnh hưởng đến sự phát triển và bệnh hại của cây.
- Soil moisture: độ ẩm đất quyết định thời điểm tưới nước.
- Light: ánh sáng ảnh hưởng đến quang hợp và phát triển cây trồng.

## Các action ví dụ
- `turn_on_fan`: giảm nhiệt, tăng lưu thông không khí.
- `start_irrigation`: tưới nước khi đất khô.
- `turn_on_grow_light`: bổ sung ánh sáng khi thiếu sáng.
- `send_warning`: gửi cảnh báo khi sensor có dấu hiệu lỗi hoặc điều kiện nguy hiểm.
