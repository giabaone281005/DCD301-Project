# Giải thích Research Questions (RQ)

## Tổng quan
Tài liệu này giải thích chi tiết các Research Questions (RQ) cho Research Theme 7: Mạch tổ hợp (Multiplexer), tập trung vào ứng dụng MUX trong hệ thống số và tích hợp với domain Smart Greenhouse.

## RQ-07: Multiplexer (MUX) là gì? Làm thế nào để sử dụng MUX nhằm chọn một trong nhiều tín hiệu đầu vào và đưa ra một ngõ ra duy nhất?
**Câu hỏi:** Multiplexer (MUX) là gì? Làm thế nào để sử dụng MUX nhằm chọn một trong nhiều tín hiệu đầu vào và đưa ra một ngõ ra duy nhất?

- **Định nghĩa MUX:** MUX là mạch logic số dùng để chọn một trong nhiều tín hiệu đầu vào (data inputs) và chuyển nó đến một ngõ ra duy nhất (output).
- **Cách sử dụng:** Cung cấp tín hiệu đầu vào, thiết lập đường chọn (select lines) để chỉ định đầu vào mong muốn, và ngõ ra sẽ phản ánh tín hiệu đã chọn.
- **Ví dụ:** MUX 4-to-1 có 4 đầu vào và 2 đường chọn; MUX giúp tiết kiệm chân I/O trong hệ thống như Smart Greenhouse để chọn dữ liệu từ sensors.
- **Ứng dụng trong domain:** Trong greenhouse, MUX có thể chọn dữ liệu từ cảm biến nhiệt độ hoặc độ ẩm để xử lý quyết định.

## RQ7.1: Multiplexer có các thành phần chính nào, bao gồm data inputs, select lines và output?
**Câu hỏi:** Multiplexer có các thành phần chính nào, bao gồm data inputs, select lines và output?

- **Data inputs:** Các tín hiệu đầu vào (ví dụ, D0, D1, D2, D3 cho MUX 4-to-1), mỗi tín hiệu là một bit hoặc bus dữ liệu từ sensors như nhiệt độ, độ ẩm.
- **Select lines:** Các đường điều khiển (ví dụ, S0, S1), dùng mã nhị phân để chọn đầu vào (2^n đường chọn cho 2^n đầu vào).
- **Output:** Một ngõ ra duy nhất (ví dụ, Y), phản ánh tín hiệu từ đầu vào đã chọn, dùng để đưa ra quyết định như bật quạt.
- **Thành phần bổ sung:** Một số MUX có enable input để kích hoạt mạch, giúp kiểm soát trong hệ thống greenhouse.

## RQ7.2: Với MUX 4-to-1, các đường chọn S1 và S0 quyết định ngõ vào được chọn như thế nào?
**Câu hỏi:** Với MUX 4-to-1, các đường chọn S1 và S0 quyết định ngõ vào được chọn như thế nào?

- **Cấu trúc MUX 4-to-1:** Có 4 data inputs (D0-D3) và 2 select lines (S1, S0).
- **Quy tắc chọn:** Dựa trên giá trị nhị phân của S1S0.
  - S1=0, S0=0: Chọn D0 (ví dụ, dữ liệu nhiệt độ).
  - S1=0, S0=1: Chọn D1 (ví dụ, độ ẩm).
  - S1=1, S0=0: Chọn D2 (ví dụ, độ ẩm đất).
  - S1=1, S0=1: Chọn D3 (ví dụ, ánh sáng).
- **Ngõ ra:** Y = D[selected], nơi selected là giá trị thập phân của S1S0, dùng để quyết định action trong greenhouse.

## RQ7.3: Multiplexer có thể được ứng dụng như thế nào trong việc chọn dữ liệu trong hệ thống số?
**Câu hỏi:** Multiplexer có thể được ứng dụng như thế nào trong việc chọn dữ liệu trong hệ thống số?

- **Chọn kênh dữ liệu:** Trong hệ thống đa kênh như Smart Greenhouse, MUX chọn tín hiệu từ sensors (nhiệt độ, độ ẩm, độ ẩm đất, ánh sáng) để xử lý tuần tự.
- **Định tuyến dữ liệu:** Trong mạch logic (FPGA, ALU), MUX chọn nguồn dữ liệu cho phép tính toán linh hoạt, như chọn giữa hai sensors để ra quyết định.
- **Tiết kiệm tài nguyên:** Giảm chân I/O trong vi điều khiển, chia sẻ chân GPIO cho nhiều thiết bị sensors.
- **Ứng dụng cụ thể:** Trong greenhouse, MUX chọn dữ liệu sensor để kích hoạt actions như bật quạt (nóng), tưới nước (khô đất), bật đèn (ít sáng), hoặc cảnh báo (mâu thuẫn dữ liệu).
