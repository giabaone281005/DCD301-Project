# Domain đã chọn và lý do chọn

## Domain được chọn
**Smart greenhouse monitoring**

## Lý do chọn
- Dễ mô phỏng sensor và tạo test case.
- Các chỉ số như nhiệt độ, độ ẩm, độ ẩm đất và ánh sáng là những thông số phổ biến, có tài liệu tham khảo nhiều.
- Khuyến nghị có thể hiển thị rõ ràng: bật quạt, tưới nước, bật đèn, cảnh báo.
- Đây là một phạm vi vừa đủ để làm rõ RAG, data quality và agent reasoning mà không quá phức tạp.

## Phạm vi cụ thể
- Thiết bị giám sát nhà kính (greenhouse) cho rau/rau ăn lá.
- Sensor chính: nhiệt độ, độ ẩm không khí, độ ẩm đất, cường độ ánh sáng.
- Hành động đề xuất: điều chỉnh quạt, tưới, bật đèn bổ sung, gửi cảnh báo.

## Mục tiêu của domain
- Xây hệ thống AIoT giúp giữ điều kiện môi trường phù hợp cho cây trồng.
- Kiểm tra chất lượng dữ liệu sensor trước khi tạo khuyến nghị.
- Dùng RAG để truy xuất kiến thức kỹ thuật và giải thích lý do khuyến nghị.
