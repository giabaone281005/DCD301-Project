# Giải thích Research Questions (RQ)

## RQ1
**Làm thế nào để tích hợp dữ liệu cảm biến IoT thời gian thực với tri thức chuyên ngành nông nghiệp để hỗ trợ ra quyết định giải thích được?**

- Dữ liệu IoT thời gian thực cung cấp trạng thái hiện tại của môi trường (nhiệt độ, độ ẩm, độ ẩm đất, v.v.).
- Tri thức chuyên ngành nông nghiệp (tài liệu kỹ thuật, hướng dẫn canh tác) giúp xác định ngưỡng an toàn và hành động phù hợp.
- RAG sẽ tìm tài liệu liên quan đến trạng thái sensor và dùng thông tin đó để giải thích khuyến nghị.
- Kết quả cần là một output có thể giải thích được: vì sao hệ thống đề xuất hành động, dựa trên dữ liệu sensor và thông tin tham chiếu.

## RQ2
**Chất lượng dữ liệu sensor ảnh hưởng thế nào đến độ tin cậy của khuyến nghị AIoT?**

- Dữ liệu sensor có thể bị thiếu, nhiễu, lỗi hoặc mâu thuẫn.
- Nếu chất lượng dữ liệu kém, hệ thống cần giảm độ tin cậy (confidence) hoặc yêu cầu xác minh thêm.
- RQ2 hướng tới thiết kế module đánh giá chất lượng dữ liệu và xem cách nó ảnh hưởng đến khuyến nghị cuối cùng.
- Output cần thể hiện rõ quality score và mức độ tự tin của hệ thống.

## RQ3
**Liệu Agentic RAG có cải thiện độ liên quan ngữ cảnh và khả năng giải thích của hỗ trợ ra quyết định nông nghiệp so với rule-based hoặc LLM-only không?**

- Rule-based chỉ dùng luật cố định, thiếu linh hoạt khi dữ liệu phức tạp.
- LLM-only có thể đưa ra câu trả lời tự do nhưng thiếu evidence từ tài liệu chuyên ngành.
- Agentic RAG kết hợp kiểm tra chất lượng dữ liệu, truy xuất tri thức và workflow agent để tạo khuyến nghị có giải thích.
- RQ3 yêu cầu so sánh kết quả giữa các phương pháp và kiểm chứng khả năng giải thích, tính liên quan ngữ cảnh.

## RQ4
**Khung đề xuất hiệu quả đến mức nào trong các kịch bản bình thường, thiếu dữ liệu, lỗi sensor và sensor mâu thuẫn?**

- Hệ thống cần được đánh giá trên các tình huống khác nhau: dữ liệu bình thường, cảnh báo, dữ liệu thiếu, lỗi sensor, mâu thuẫn sensor.
- Mục tiêu là kiểm tra độ bền, độ chính xác và khả năng xử lý tình huống nguy hiểm.
- RQ4 yêu cầu xác định xem proposed framework có duy trì được hiệu quả khi dữ liệu không hoàn hảo hay không.
