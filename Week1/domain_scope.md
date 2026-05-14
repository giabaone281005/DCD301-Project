# Domain Scope - Smart Greenhouse Monitoring

## 1. Domain đã chọn: Smart Greenhouse Monitoring

Hệ thống giám sát và điều khiển môi trường nhà kính thông minh, tập trung vào việc quản lý đa điểm các thông số sinh trưởng của cây trồng.

---

## 2. Làm rõ lý do chọn (Deep Dive)

### A. Tính thực tế và nhu cầu phối hợp dữ liệu

#### Giám sát đa điểm

Nhà kính hiện đại không chỉ đo một điểm duy nhất mà cần đo ở nhiều vị trí:
- Gần cửa
- Giữa vườn  
- Dưới tán lá

Một mạch MUX 4-to-1 hoặc 8-to-1 cho phép hệ thống "quét" qua các cảm biến này một cách có hệ thống mà không cần nâng cấp lên các vi điều khiển đắt tiền có nhiều cổng đầu vào.

#### Phù hợp với đặc thù nông nghiệp

Các thông số như độ ẩm đất hay nồng độ CO2 thường thay đổi chậm, cho phép MUX thực hiện chuyển mạch luân phiên (time-division multiplexing) mà vẫn đảm bảo tính thời gian thực cho hệ thống xử lý.

---

### B. Sự kết hợp hoàn hảo giữa MUX và Agentic RAG

#### MUX là "Cánh cổng" (Gatekeeper)

MUX quyết định nguồn dữ liệu nào được đưa vào pipeline RAG tại mỗi thời điểm.

#### Agentic RAG làm nhiệm vụ "Kiểm soát viên"

**Vấn đề tiềm ẩn:**  
Nếu MUX bị nhiễu hoặc chọn sai kênh (ví dụ: chân chọn $S_1, S_0$ bị lỏng), dữ liệu trả về sẽ bị sai lệch hoàn toàn.

**Giải pháp Agent:**  
Agent trong hệ thống sẽ không chỉ đọc số liệu mà còn sử dụng kiến thức từ RAG (Tài liệu kỹ thuật) để nhận định:

> "Hiện tại MUX đang báo nhiệt độ $80^{\circ}C$, nhưng tài liệu kỹ thuật nói rằng mức này là bất khả thi trong điều kiện hiện tại"

**Hành động được đề xuất:**
- ✓ Kiểm tra lại mạch chọn kênh MUX
- ✓ Tính toán lại điểm tin cậy (Confidence Score)

---

### C. Khả năng mô phỏng và Kiểm chứng (Stress Test)

#### Lỗi chọn kênh (Selection Error)

Mô phỏng tình huống tín hiệu điều khiển MUX bị sai, dẫn đến việc lấy dữ liệu cảm biến Nhiệt độ nhưng hệ thống lại tưởng là độ ẩm.

**Mục đích:** Đây là kịch bản hoàn hảo để kiểm tra khả năng phát hiện mâu thuẫn của Data Quality Module trong RQ2.

#### Nhiễu xuyên kênh (Crosstalk)

Mô phỏng tình huống các tín hiệu trong MUX bị nhiễu lẫn nhau, tạo ra dữ liệu "trôi dạt" (drift).

**Mục đích:** Đánh giá độ nhạy của Agentic RAG trong việc phân biệt dữ liệu thực và dữ liệu lỗi.