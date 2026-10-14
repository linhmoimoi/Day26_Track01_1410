# Memo quyết định

## Phạm vi vấn đề (Bước 1)

- **Product:** Lost&Found AI Agent
- **User:** Nhân viên phụ trách đồ thất lạc tại trường học
- **Workflow:** Tiếp nhận báo cáo mất/nhặt được → phân loại đồ vật → đối chiếu báo cáo → liên hệ người báo khi có kết quả phù hợp
- **Problem:** Nhân viên mất nhiều thời gian tìm chủ sở hữu đồ vật được nhặt thấy; thời gian xử lý chưa được đo bằng mốc bắt đầu/kết thúc.

**Một dòng phạm vi:** “Nhân viên phụ trách đồ thất lạc tại trường học dùng Lost&Found AI Agent để tiếp nhận và phân loại báo cáo, đối chiếu đồ vật mất/nhặt được rồi liên hệ người báo, nhưng mất nhiều thời gian tìm chủ sở hữu.”

## Chẩn đoán Bước 2

### Framework đã dùng

| Framework | Nhận định chính | Trạng thái |
|---|---|---|
| Năm trục chẩn đoán | Điểm nghẽn nằm ở đối chiếu thủ công giữa các báo cáo không đồng nhất và nằm trên nhiều kênh. Không có mốc thời gian để định lượng độ trễ. | GỐC / THIẾU |
| Gartner-Lite | Direction: vấn đề và nhóm người dùng đã xác định. Readiness: dữ liệu báo cáo thiếu thông tin và chưa có cách đo thời gian xử lý. Absorption: chưa có thông tin về owner, hỗ trợ vận hành hoặc cơ chế học từ lỗi. | ĐẠT / NGHẼN / THIẾU |

### Bằng chứng

Các tình huống bên dưới được người dùng xác nhận là đúng với thực tế vào ngày 2026-10-14. Nguồn hiện có là xác nhận trực tiếp trong cuộc trò chuyện; chưa có báo cáo, biểu mẫu hoặc log gốc để đối chiếu độc lập.

| Bằng chứng | Nguồn và thời điểm | Nhận định được hỗ trợ | Độ chắc chắn |
|---|---|---|---|
| Trong một tuần, 8 báo cáo được xem xét; 5 báo cáo thiếu ít nhất một chi tiết nhận diện hoặc đối chiếu như thời gian, địa điểm hoặc đặc điểm riêng của đồ vật. | Người dùng xác nhận trong cuộc trò chuyện, 2026-10-14; hồ sơ gốc chưa được cung cấp. | Thông tin không đầy đủ làm bước so khớp báo cáo khó hơn. | Vừa: xác nhận trực tiếp, chưa kiểm tra mẫu báo cáo. |
| Báo cáo đến từ biểu mẫu, tin nhắn và ghi nhận trực tiếp; nhân viên lần lượt tìm qua các kênh để đối chiếu. | Người dùng xác nhận trong cuộc trò chuyện, 2026-10-14; chưa quan sát trực tiếp. | Quy trình phân tán tạo thao tác tìm kiếm thủ công và có thể làm tăng thời gian tìm chủ. | Vừa: xác nhận trực tiếp, chưa có walkthrough hoặc log. |
| Biểu mẫu và sổ theo dõi không ghi thời điểm bắt đầu tìm chủ và thời điểm xác nhận được chủ. | Người dùng xác nhận trong cuộc trò chuyện, 2026-10-14; chưa xem biểu mẫu/sổ thực tế. | Nhóm chưa thể tính thời gian xử lý hoặc xác định bước chậm nhất bằng dữ liệu vận hành. | Vừa: xác nhận trực tiếp, chưa kiểm tra tài liệu gốc. |

### Nguyên nhân gốc

1. **Thông tin trong báo cáo mất/nhặt không đầy đủ hoặc không nhất quán, khiến việc đối chiếu khó hơn.** Framework: Năm trục — Workflow và Sẵn sàng; Gartner-Lite — Readiness. Bằng chứng: 5/8 báo cáo trong mẫu một tuần thiếu ít nhất một chi tiết đối chiếu. Độ chắc chắn: **vừa**; xác nhận trực tiếp nhưng chưa kiểm tra mẫu gốc. Mối liên hệ nhân quả hợp lý, chưa được đo riêng.
2. **Báo cáo nằm trên nhiều kênh, buộc nhân viên tìm và so sánh lần lượt.** Framework: Năm trục — Workflow; Gartner-Lite — Readiness. Bằng chứng: báo cáo đến từ biểu mẫu, tin nhắn và ghi nhận trực tiếp, được tìm thủ công qua từng kênh. Độ chắc chắn: **vừa**; xác nhận trực tiếp nhưng chưa quan sát quy trình hoặc đo thời gian theo kênh.

Việc thiếu mốc thời gian là một khoảng trống đo lường đã được xác nhận, chưa được xem là nguyên nhân gốc độc lập vì hiện chưa có bằng chứng cho thấy nó trực tiếp làm việc tìm chủ kéo dài.

### Kết luận chẩn đoán

Cần xử lý hai điểm được xác nhận trước khi chọn giải pháp: chất lượng thông tin trong báo cáo và việc báo cáo phân tán qua nhiều kênh. Đồng thời, hiện chưa có mốc thời gian xử lý nên chưa thể định lượng mức độ chậm hoặc xác định tác động của từng nguyên nhân; các quan hệ nhân quả hiện có độ tin cậy vừa, chưa được kiểm tra bằng hồ sơ gốc.

## Phần 1 — TODO: tên phần theo §6.4

- Nội dung quyết định: TODO
- Căn cứ/dữ liệu: TODO

## Phần 2 — TODO: tên phần theo §6.4

- Nội dung quyết định: TODO
- Căn cứ/dữ liệu: TODO

## Phần 3 — TODO: tên phần theo §6.4

- Nội dung quyết định: TODO
- Căn cứ/dữ liệu: TODO

## Phần 4 — TODO: tên phần theo §6.4

- Nội dung quyết định: TODO
- Căn cứ/dữ liệu: TODO

## Phần 5 — TODO: tên phần theo §6.4

- Nội dung quyết định: TODO
- Căn cứ/dữ liệu: TODO
