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

## Bước 3 — Thiết kế cách làm mới

### Đầu vào sử dụng

Phạm vi: Lost&Found AI Agent cho nhân viên phụ trách đồ thất lạc tại trường học; tiếp nhận báo cáo → phân loại → đối chiếu → liên hệ người báo. Chẩn đoán Bước 2 nêu hai nguyên nhân: báo cáo thiếu chi tiết nhận diện/đối chiếu và dữ liệu nằm trên nhiều kênh, buộc nhân viên tìm thủ công. Biểu mẫu/sổ hiện tại không ghi đủ mốc thời gian xử lý.

### AS-IS / TO-BE

| Bước | AS-IS | TO-BE | Nguyên nhân được xử lý |
|---|---|---|---|
| Tiếp nhận | Báo cáo đến qua biểu mẫu, tin nhắn và ghi nhận trực tiếp; chưa rõ có sổ tổng hợp thống nhất hay không. | Nhân viên nhập mỗi báo cáo vào sổ vụ việc tập trung, cấp mã, ghi kênh và thời điểm nhận. Nếu chưa tích hợp được kênh, nhập thủ công vẫn tạo một bản ghi chuẩn. | Nhiều kênh |
| Hoàn thiện thông tin | Một số báo cáo thiếu chi tiết; cách xử lý thiếu trường chưa được xác định. | Dùng bộ trường thống nhất: loại đồ, đặc điểm riêng, thời gian/địa điểm mất hoặc nhặt, thông tin liên hệ tối thiểu cần thiết. Nhân viên yêu cầu bổ sung khi thiếu; không coi thiếu dữ liệu là không có kết quả khớp. | Thiếu/không nhất quán thông tin |
| Tìm ứng viên | Nhân viên lần lượt tìm và so sánh báo cáo qua các kênh. | Agent phân loại và tìm ứng viên trong sổ tập trung, hiển thị mã bản ghi, trường căn cứ và ngày cập nhật nếu có. Đây là yêu cầu thiết kế, chưa xác nhận là tính năng hiện có của agent. | Cả hai |
| Xác minh | Chưa rõ có bước kiểm tra chuẩn hoặc lưu lý do ghép/bỏ ghép không. | Nhân viên kiểm tra nguồn, xác minh ứng viên theo quy trình trường phê duyệt và quyết định cuối. Agent không tự xác nhận chủ, liên hệ hoặc bàn giao đồ vật. | Độ tin cậy / trách nhiệm |
| Ngoại lệ và liên hệ | Cách xử lý báo cáo thiếu, nhiều ứng viên hoặc không tìm thấy chưa rõ. | Nếu thiếu căn cứ, nguồn mâu thuẫn, nhiều ứng viên hoặc độ tin cậy chưa được kiểm chứng, agent dừng và chuyển cho nhân viên. Chỉ nhân viên liên hệ qua kênh được trường duyệt sau khi xác minh. | Độ tin cậy / chất lượng dữ liệu |
| Đóng vụ việc và phản hồi | Không có mốc thời gian xử lý đã xác nhận; cách ghi lỗi chưa rõ. | Ghi thời điểm đề xuất, xác minh, liên hệ và đóng vụ việc; nhân viên có thể báo đề xuất sai, thiếu ứng viên hoặc nguồn sai/cũ theo mã vụ việc. Owner xem lỗi và ghi thay đổi. | Đo lường / duy trì |

### Luồng tin cậy

**Nguồn → Trích nguồn → QA mẫu → Chuyển người → Phản hồi**

1. **Nguồn:** Nhân viên ghi báo cáo vào sổ vụ việc; lưu mã, kênh, trường dữ liệu và thời điểm. Cần chỉ định owner chịu trách nhiệm về chất lượng, quyền dùng và lịch cập nhật nguồn. Chỉ chuyển tiếp khi trường cho phép sử dụng; quyền truy cập và thời hạn lưu phải được xác định.
2. **Trích nguồn:** Agent đưa ra đề xuất kèm mã bản ghi, trường dùng để so khớp và ngày cập nhật nếu có. Lưu đề xuất, nguồn tham chiếu, phiên bản dữ liệu và thời điểm. Trích dẫn giúp truy lại căn cứ nhưng không chứng minh kết quả đúng. Không truy được nguồn hoặc có mâu thuẫn thì dừng.
3. **QA mẫu:** Người QA cần được chỉ định. Kiểm tra mẫu gồm đề xuất khớp, không khớp và trường hợp agent từ chối; ghi lỗi ghép, bỏ sót và quyết định sửa/dừng. Mọi đề xuất dùng để liên hệ vẫn phải được nhân viên kiểm tra; QA mẫu không thay thế kiểm tra đó. Cỡ mẫu, tần suất và ngưỡng lỗi phải thống nhất trước khi dùng kết quả; hiện chưa có căn cứ để đặt số.
4. **Chuyển người:** Nhân viên phụ trách đồ thất lạc nhận ca khi dữ liệu thiếu, nguồn mâu thuẫn, có nhiều ứng viên hoặc độ tin cậy chưa được hiệu chỉnh. Lưu lý do, người nhận và trạng thái. Nhân viên chịu trách nhiệm quyết định; cần chỉ định owner cho dữ liệu và agent.
5. **Phản hồi:** Nhân viên báo lỗi kèm mã vụ việc. Owner được chỉ định xem xét, sửa nguồn/quy tắc và lưu nội dung sửa, người sửa, ngày sửa, kết quả QA. Nếu lỗi có thể dẫn tới ghép nhầm lặp lại, dừng đề xuất AI đến khi được kiểm tra.

### Giải pháp gắn với nguyên nhân

| Nguyên nhân gốc | Thay đổi thiết kế | Vì sao phù hợp | Điều kiện phụ thuộc |
|---|---|---|---|
| Thông tin báo cáo thiếu hoặc không nhất quán | Chuẩn hóa trường, đánh dấu trường thiếu, yêu cầu bổ sung; agent chỉ đề xuất khi có căn cứ hiển thị. | Giảm so sánh trên mô tả thiếu và tránh suy diễn từ dữ liệu trống. | Cần thống nhất schema, cách ghi “không biết”, owner và quy tắc lưu. |
| Báo cáo phân tán trên nhiều kênh | Sổ vụ việc tập trung và tìm ứng viên trong cùng một tập bản ghi. | Loại bỏ việc nhân viên lần lượt dò từng nguồn trong bước đối chiếu. | Cần quyền dùng dữ liệu, cách nhập/tích hợp và xác minh khả năng của agent. |
| Thiếu mốc thời gian (khoảng trống đo lường) | Ghi thời điểm nhận, bắt đầu xử lý, đề xuất, xác minh chủ và đóng vụ việc. | Tạo đường cơ sở và xác định bước mất thời gian; chưa xem đây là nguyên nhân gốc độc lập. | Cần định nghĩa mốc, người/cách ghi và cách xử lý vụ việc chưa đóng. |

### Mức sẵn sàng

| Điều kiện | Trạng thái | Căn cứ | Việc cần làm |
|---|---|---|---|
| Nguồn có owner và lịch cập nhật | Thiếu | Nhiều kênh nguồn; owner/lịch cập nhật chưa rõ. | Chỉ định owner, nguồn có thẩm quyền, lịch cập nhật, xử lý trùng/lỗi và thời hạn lưu. |
| Quyền truy cập đúng người, đúng mục đích | Chưa rõ | Chưa có thông tin về phân quyền hoặc quy định dữ liệu của trường. | Trường xác định dữ liệu tối thiểu, vai trò được xem, phạm vi agent và kênh liên hệ. Chưa rõ quyền thì không đưa dữ liệu cá nhân thật vào agent. |
| Phạm vi AI rõ | Đạt ở mức thiết kế; cần phê duyệt | Agent chỉ phân loại/tìm ứng viên; con người xác minh và quyết định. | Trường phê duyệt phạm vi; kiểm tra agent có thể trích nguồn, từ chối và chuyển người. |
| Chi phí, năng lực vận hành và governance | Chưa rõ | Chưa có chi phí, năng lực hỗ trợ, chính sách xử lý dữ liệu hay owner vận hành. | Ước tính chi phí/công sức; xác định QA, sự cố, lưu/xóa dữ liệu và quyền dừng. Chưa vận hành với dữ liệu thật khi chưa được phê duyệt. |

### Thiết kế cần chốt

- Trường dữ liệu bắt buộc và xử lý báo cáo cũ/thiếu.
- Sổ vụ việc tập trung ở đâu, owner là ai, nguồn nào được phép nhập.
- Agent có thể tìm trong nguồn được phép, hiển thị mã/ngày cập nhật và dừng/chuyển người không.
- Owner dữ liệu, người QA, owner agent và người có quyền xác minh/liên hệ.
- Quy trình trường phê duyệt để xác minh chủ; kênh liên hệ được phép.
- Mốc thời gian, đường cơ sở, cỡ mẫu QA, ngưỡng lỗi và điều kiện dừng; chưa đặt số khi chưa có dữ liệu.
- Chi phí, phân quyền, thời hạn lưu, hỗ trợ vận hành và governance.

**Mô tả quy trình mới:** Nhân viên nhập mỗi báo cáo vào sổ vụ việc tập trung theo trường thống nhất. Agent phân loại và đề xuất ứng viên có mã nguồn, trường căn cứ và ngày cập nhật nếu có. Nhân viên kiểm tra nguồn, xác minh theo quy trình trường duyệt rồi mới liên hệ hoặc bàn giao. Khi thiếu dữ liệu, nguồn mâu thuẫn, có nhiều ứng viên hoặc agent không chắc chắn, agent dừng và chuyển người. Các đề xuất, quyết định, mốc thời gian và phản hồi lỗi được lưu để QA và đo thời gian xử lý.
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
