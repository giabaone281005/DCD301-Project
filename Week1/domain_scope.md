# Domain đã chọn và lý do chọn

## Domain được chọn
**Smart Greenhouse Monitoring**

## Lý do chọn
- **Dễ mô phỏng và test:** Sensors như nhiệt độ, độ ẩm, độ ẩm đất và ánh sáng dễ triển khai và tạo test case đa dạng.
- **Thông số phổ biến:** Có nhiều tài liệu tham khảo về nông nghiệp và greenhouse, hỗ trợ tích hợp tri thức chuyên ngành.
- **Khuyến nghị rõ ràng:** Actions như bật quạt, tưới nước, bật đèn, cảnh báo dễ hiển thị và đánh giá hiệu quả.
- **Liên kết với RQ:** Domain này cho phép ứng dụng Multiplexer (MUX) để chọn dữ liệu từ sensors, minh họa cách MUX hoạt động trong hệ thống số để ra quyết định thông minh.
- **Phạm vi phù hợp:** Vừa đủ để khám phá RAG, chất lượng dữ liệu và agent reasoning mà không quá phức tạp.

## Phạm vi cụ thể
- Thiết bị giám sát nhà kính (greenhouse) cho rau/rau ăn lá.
- Sensor chính: nhiệt độ, độ ẩm không khí, độ ẩm đất, cường độ ánh sáng.
- Hành động đề xuất: điều chỉnh quạt, tưới, bật đèn bổ sung, gửi cảnh báo.

## Mục tiêu của domain
- Xây hệ thống AIoT giúp giữ điều kiện môi trường phù hợp cho cây trồng.
- Kiểm tra chất lượng dữ liệu sensor trước khi tạo khuyến nghị.
- Dùng RAG để truy xuất kiến thức kỹ thuật và giải thích lý do khuyến nghị.
