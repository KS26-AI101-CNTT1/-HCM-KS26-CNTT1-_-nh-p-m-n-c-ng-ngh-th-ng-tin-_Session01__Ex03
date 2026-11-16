Đề bài / Yêu cầu

Lựa chọn giải pháp Zero-shot vs Few-shot trong lọc phản hồi khách hàng

1. Mục tiêu bài tập 

Giúp các bạn hiểu rõ sự khác biệt và đánh đổi (Trade-off) khi viết prompt không có ví dụ (Zero-shot) và prompt có ví dụ mẫu (Few-shot) để lọc thông tin chính xác.

2. Bối cảnh & yêu cầu bài toán

Cửa hàng cần phân loại các tin nhắn phản hồi của khách thành 3 nhóm: TÍCH CỰC, TIÊU CỰC, và CẦN HỖ TRỢ.

3. Quy tắc nghiệp vụ phân loại

- Nhóm Tích cực: Khen sản phẩm ngon, rẻ.\

•	Nhóm Tiêu cực: Chê giao hàng chậm, thái độ tệ.\

•	Nhóm Cần hỗ trợ: Hỏi địa chỉ cửa hàng, hỏi giá.

4. Ràng buộc & bẫy dữ liệu cần chú ý

Khách gửi câu mỉa mai: 'Quán phục vụ chu đáo quá, bắt khách đợi hẳn 1 tiếng!'. AI rất dễ nhầm là Tích cực vì có từ 'chu đáo quá'.

5. Yêu cầu bài làm chi tiết

Bước 1: Thiết kế 2 phương án prompt:

Phương án 1 (Zero-shot): Viết prompt chỉ nêu luật phân loại và bắt AI tự làm.

Zero-shot: "Phân loại tin nhắn sau vào 1 trong 3 nhóm: TÍCH CỰC (khen ngon, rẻ), TIÊU CỰC (chê chậm, thái độ tệ), CẦN HỖ TRỢ (hỏi địa chỉ, giá). Tin nhắn: 'Quán phục vụ chu đáo quá, bắt khách đợi hẳn 1 tiếng!'"

Phương án 2 (Few-shot): Viết prompt cung cấp 3 ví dụ mẫu rõ ràng, có cả ví dụ câu mỉa mai ở trên.

Few-shot: "Phân loại tin nhắn theo mẫu:

'Đồ ăn ngon, giá rẻ' -> TÍCH CỰC

'Cho xin địa chỉ quán' -> CẦN HỖ TRỢ

'Nhân viên nhiệt tình ghê, hỏi mãi không trả lời' -> TIÊU CỰC

Phân loại câu sau: 'Quán phục vụ chu đáo quá, bắt khách đợi hẳn 1 tiếng!'"

Bước 2: Lập bảng so sánh Trade-off:

Lập bảng so sánh tiêu chí.

Tiêu chí	Giải pháp 1 (Zero-shot)	Giải pháp 2 (Few-shot)

Độ dễ hiểu	Cao, dễ viết nhanh	Trung bình, cần viết dài

Tốn token	Ít tốn token	Tốn nhiều token hơn

Xử lý câu mỉa mai	Kém, dễ bị lừa	Tốt, do có ví dụ mẫu làm theo

Tiêu chí	Giải pháp 1 (Zero-shot)	Giải pháp 2 (Few-shot)

Độ dễ hiểu	Cao, viết nhanh.	Trung bình, phải viết ví dụ.

Tốn token	Ít tốn token.	Tốn nhiều token hơn.

Xử lý câu mỉa mai	Kém, dễ bị lừa.	Tốt, hiểu đúng ngữ cảnh.

Bước 3: Thử nghiệm thực tế:

Chạy cả 2 prompt với câu mỉa mai và báo cáo kết quả phương án nào chính xác hơn.

Zero-shot: Trả về sai là TÍCH CỰC (do mắc bẫy từ "chu đáo quá").

Few-shot: Trả về đúng là TIÊU CỰC (học được cách nhận diện câu mỉa mai từ ví dụ mẫu).Kết luận: Few-shot chính xác hơn.
