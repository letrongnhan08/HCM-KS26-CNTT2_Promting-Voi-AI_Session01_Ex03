Bài 3: Giải mã hiện tượng "Đau ví" do Chênh lệch Tokenization Tiếng Việt


**Phần 1 (Phân tích BPE)**:
giải thích cơ chế cắt từ của BPE (Sub-word Tokenization) là khởi tạo từ điển từ các ký tự đơn lẻ (hoặc byte) và quét qua kho dữ liệu huấn luyện (Pre-training corpus) để gộp các cặp ký tự xuất hiện thường xuyên nhất thành một token mới (sub-word unit)

Lý do khiến Mẫu B tốn gấp 2.4 lần Token của Mẫu A: Vì các mô hình AI lớn hiện nay chủ yếu được dạy bằng Tiếng Anh, nên khi gặp Tiếng Việt (ngôn ngữ có hệ thống dấu thanh phức tạp dạng mã hóa Unicode), AI buộc phải bẻ nhỏ 1 từ tiếng Việt thành 2 đến 3 mảnh token rời rạc để hiểu.

**Phần 2 (Tối ưu Prompt)**:
**Tối giản câu từ Tiếng Việt:** Lược bỏ các câu từ rườm rà ,  từ đệm thừa thãi để tiết kiệm số lượng Token đầu vào và đầu ra ví dụ:
câu gốc: "Siêu thị MartX cung cấp các loại rau củ hữu cơ tươi ngon nhất..." -> 285 token
câu tối giản: "MarkX có các loại rau ngon nhất" -> giảm 35-40% token

**Sử dụng vừa tiếng Anh và tiếng Việt:** vì LLM tối ưu cho Tiếng Anh, sử dụng thuật ngữ chuyên ngành như marketing, tên công ty, từ khóa chuyên môn kỹ thuật giúp tiết kiệm token.

câu thường:"Hãy phân tích tỷ lệ chuyển đổi khách hàng qua chiến dịch marketing vừa rồi"

câu kết hợp: "Analyze Conversion Rate của campaign Marketing vừa rồi"

