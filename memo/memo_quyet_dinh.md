# Memo quyết định

## Tóm tắt bàn giao theo §6.5 — năm phần

### 1. Vấn đề và nguyên nhân gốc

Nhân viên phụ trách đồ thất lạc tại trường mất thời gian tìm chủ; biểu mẫu/sổ chưa ghi mốc bắt đầu và kết thúc. Hai nguyên nhân chẩn đoán (độ tin cậy vừa): thông tin báo cáo thiếu/không nhất quán; báo cáo nằm rải rác qua biểu mẫu, tin nhắn và ghi nhận trực tiếp nên phải tìm thủ công. Bằng chứng người dùng xác nhận: trong một tuần có 8 báo cáo, 5 báo cáo thiếu ít nhất một chi tiết đối chiếu. Chưa có hồ sơ gốc để kiểm tra độc lập.

### 2. Framework đã dùng và bằng chứng

Dùng Năm trục chẩn đoán và Gartner-Lite. Cả hai cùng chỉ về chất lượng thông tin và workflow phân tán; thiếu mốc thời gian là khoảng trống đo lường, chưa kết luận là nguyên nhân gốc độc lập. Nguồn bằng chứng hiện là xác nhận của người dùng trong cuộc trò chuyện ngày 2026-10-14; chưa có biểu mẫu, sổ hoặc log gốc. Xem bảng framework và bằng chứng trong phần phân tích chi tiết bên dưới.

### 3. Ít nhất hai thay đổi sau kiểm tra chéo

Đây là **tự kiểm tra của Codex**, không phải góp ý peer review thực tế. Hai thay đổi v2 so với v1:

1. **Metric giá trị:** trước đây tỷ lệ hoàn trả chưa chốt mẫu số/cửa sổ; v2 yêu cầu báo cáo đồ nhặt đủ điều kiện được trả cho chủ đã xác minh trong cửa sổ do nhóm duyệt, áp dụng cùng định nghĩa cho baseline và pilot. Lý do: phép so sánh nhất quán, không tự đặt target.
2. **Trạng thái gate:** v1 chưa phân biệt rõ giả định bài tập với bằng chứng vận hành trong workbook; v2 ghi “đạt theo giả định” riêng với bằng chứng thực tế còn thiếu. Lý do: tránh hiểu nhầm giả định là kết quả pilot.

### 4. Quyết định

**Sửa** readiness trước khi pilot dữ liệu thật. Đây là quyết định cho bài nộp cá nhân của Nguyễn Ngọc Linh; không phải phê duyệt vận hành của trường.

### 5. Lý do, bước tiếp theo và owner

Cho bài nộp cá nhân, Nguyễn Ngọc Linh là owner tài liệu và chọn quyết định “Sửa”. Target thiết kế được đặt trong dashboard theo ràng buộc của TO-BE (100% truy vết nguồn, 100% xác minh trước liên hệ, 0 lỗi ghép nghiêm trọng; các chỉ số thời gian/rework/hoàn trả cải thiện so baseline). Baseline vận hành, log QA và phê duyệt nguồn/quyền chưa tồn tại trong hồ sơ; các vai trò vận hành được gán theo chức năng, chưa gán tên người thật. Bước tiếp theo nếu trường triển khai: tạo log, đo baseline, phê duyệt dữ liệu và kiểm thử dừng/chuyển người trước pilot.

---

## Phân tích chi tiết và căn cứ

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

1. **Nguồn:** Nhân viên ghi báo cáo vào sổ vụ việc; lưu mã, kênh, trường dữ liệu và thời điểm. Data steward theo vai trò chịu trách nhiệm chất lượng/lịch cập nhật; người được trường ủy quyền quyết định quyền dùng. Chỉ chuyển tiếp sau khi trường cho phép; hiện repo chưa có phê duyệt hoặc tên người được ủy quyền.
2. **Trích nguồn:** Agent đưa ra đề xuất kèm mã bản ghi, trường dùng để so khớp và ngày cập nhật nếu có. Lưu đề xuất, nguồn tham chiếu, phiên bản dữ liệu và thời điểm. Trích dẫn giúp truy lại căn cứ nhưng không chứng minh kết quả đúng. Không truy được nguồn hoặc có mâu thuẫn thì dừng.
3. **QA mẫu:** QA reviewer độc lập là vai trò trong thiết kế; chưa có người thật được chỉ định. Kiểm tra mẫu gồm đề xuất khớp, không khớp và trường hợp agent từ chối; ghi lỗi ghép, bỏ sót và quyết định sửa/dừng. Mọi đề xuất dùng để liên hệ vẫn phải được nhân viên kiểm tra; QA mẫu không thay thế kiểm tra đó. Cỡ mẫu và tần suất được xác định từ quy mô pilot; target bài tập là không có lỗi ghép nghiêm trọng chưa xử lý.
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
| Nguồn có owner và lịch cập nhật | Chưa triển khai | TO-BE gán vai trò data steward; nguồn thực tế/lịch cập nhật chưa có trong repo. | Data steward duy trì danh mục nguồn, ngày cập nhật, xử lý trùng/lỗi; xác lập lịch trước pilot. |
| Quyền truy cập đúng người, đúng mục đích | Chưa được phê duyệt | Repo không có quy định/phê duyệt truy cập của trường. | Mặc định an toàn cho bài tập: chỉ dữ liệu giả lập/đã khử định danh; không đưa dữ liệu cá nhân thật vào agent khi chưa được trường cho phép. |
| Phạm vi AI rõ | Đạt ở mức thiết kế; cần phê duyệt | Agent chỉ phân loại/tìm ứng viên; con người xác minh và quyết định. | Trường phê duyệt phạm vi; kiểm tra agent có thể trích nguồn, từ chối và chuyển người. |
| Chi phí, năng lực vận hành và governance | Chưa đo/chưa phê duyệt | Chưa có chi phí, năng lực hỗ trợ hoặc chính sách xử lý dữ liệu. | Trước pilot, process owner ghi công sức xử lý; data steward và QA reviewer thực hiện kiểm tra; trường phê duyệt lưu/xóa dữ liệu và quyền dừng. Chưa vận hành với dữ liệu thật khi chưa được phê duyệt. |

### Thiết kế cần chốt

- Trường dữ liệu bắt buộc và xử lý báo cáo cũ/thiếu.
- Sổ vụ việc tập trung ở đâu, owner là ai, nguồn nào được phép nhập.
- Agent có thể tìm trong nguồn được phép, hiển thị mã/ngày cập nhật và dừng/chuyển người không.
- Owner dữ liệu, người QA, owner agent và người có quyền xác minh/liên hệ.
- Quy trình trường phê duyệt để xác minh chủ; kênh liên hệ được phép.
- Mốc thời gian, đường cơ sở, cỡ mẫu QA, ngưỡng lỗi và điều kiện dừng; chưa đặt số khi chưa có dữ liệu.
- Chi phí, phân quyền, thời hạn lưu, hỗ trợ vận hành và governance.

**Mô tả quy trình mới:** Nhân viên nhập mỗi báo cáo vào sổ vụ việc tập trung theo trường thống nhất. Agent phân loại và đề xuất ứng viên có mã nguồn, trường căn cứ và ngày cập nhật nếu có. Nhân viên kiểm tra nguồn, xác minh theo quy trình trường duyệt rồi mới liên hệ hoặc bàn giao. Khi thiếu dữ liệu, nguồn mâu thuẫn, có nhiều ứng viên hoặc agent không chắc chắn, agent dừng và chuyển người. Các đề xuất, quyết định, mốc thời gian và phản hồi lỗi được lưu để QA và đo thời gian xử lý.

## Bước 4 — Lộ trình 30–60–90 ngày theo cổng quyết định

Các mốc 0–30, 31–60 và 61–90 ngày là cửa sổ xem xét, không tự động xác nhận thành công. Target thiết kế cho bài tập được ghi ở dashboard; khi vận hành, owner của trường phải xem bằng chứng và phê duyệt ngưỡng trước pilot.

**Trạng thái:** Lộ trình được chấp thuận ở mức thiết kế ngày 2026-10-14. Theo yêu cầu bài tập, ba gate được đánh dấu đạt theo giả định; thực tế chưa có đánh giá. Owner theo vai trò và target thiết kế đã ghi, còn baseline vận hành, phê duyệt dữ liệu và QA pilot chưa có.

### Phạm vi pilot

Pilot dự kiến giới hạn ở nhân viên phụ trách đồ thất lạc tại trường học và quy trình tiếp nhận → chuẩn hóa báo cáo → tìm ứng viên → người kiểm tra/xác minh → liên hệ. Hai nguyên nhân đang xử lý là thông tin báo cáo thiếu/không nhất quán và nguồn báo cáo phân tán. Agent chỉ phân loại/tìm ứng viên có nguồn; nhân viên xác minh và quyết định. Owner được xác định theo vai trò trong thiết kế, chưa gắn tên người vận hành; quyền dữ liệu chưa được phê duyệt và khả năng agent chưa được kiểm chứng.

### Các decision gate

| Giai đoạn / gate | Điều cần chứng minh | Owner | Tiêu chí đạt: chất lượng, hành vi, giá trị | Bằng chứng | Nếu chưa đạt |
|---|---|---|---|---|---|
| **0–30 ngày — Gate 1: vấn đề và khả thi pilot** | Sổ vụ việc, quyền nguồn, luồng TO-BE và baseline đủ rõ cho đánh giá có kiểm soát. | **Owner theo vai trò:** process owner, data steward và người phê duyệt dữ liệu của trường. | **Chất lượng:** chuẩn hóa trường và nguồn. **Hành vi:** ghi các mốc nhận, bắt đầu, xác minh/đóng. **Giá trị:** có baseline thời gian. Target thiết kế: 100% nguồn truy lại, 100% xác minh trước liên hệ; baseline được thu trước pilot. | Schema và danh mục nguồn; phê duyệt quyền; baseline thời gian; phạm vi pilot. | Chưa có quyền hoặc baseline thì chỉ dùng dữ liệu giả lập/đã khử định danh; không pilot dữ liệu thật. |
| **31–60 ngày — Gate 2: chất lượng và dùng được trong workflow** | Agent tạo đề xuất truy vết được; nhân viên kiểm tra và lỗi được phát hiện. | **Owner theo vai trò:** pilot/process owner, QA reviewer, owner agent và case handler. | QA đề xuất đúng/sai/bỏ sót/abstain. Target thiết kế: 100% đề xuất có nguồn; 0 lỗi ghép nghiêm trọng; 100% liên hệ có xác minh trước. Hiệu quả thời gian/rework phải tốt hơn baseline mà không giảm chất lượng. | Log đề xuất, QA nhãn kết quả, log chuyển người, mốc vụ việc và so sánh baseline. | Nếu lỗi nghiêm trọng, mất nguồn hoặc thiếu xác minh: dừng đề xuất AI, quay về thủ công, sửa rồi QA lại. |
| **61–90 ngày — Gate 3: mở rộng / sửa / dừng** | Kết quả theo target thiết kế, vai trò vận hành và quản trị sẵn sàng. | **Owner theo vai trò:** người ra quyết định của trường, process owner, data steward, privacy approver. | Chỉ xem xét mở rộng khi 0 lỗi nghiêm trọng chưa xử lý, target được đo đạt, quy trình được tuân thủ và chi phí/quyền dữ liệu được phê duyệt. | QA, báo cáo baseline so sánh, bằng chứng sử dụng, chi phí, quyền/lưu trữ và quyết định có thẩm quyền. | Sửa, kéo dài có phê duyệt, hoặc dừng; ngày thứ 90 tự nó không làm gate đạt. |

### Đánh giá hiện trạng các gate — 2026-10-14

**Trạng thái theo yêu cầu của người dùng:** xem cả ba gate là **ĐẠT THEO GIẢ ĐỊNH** để hoàn tất bài tập/lộ trình. Đây là xác nhận giả định do người dùng chỉ định, không phải kết quả được chứng minh bằng hồ sơ pilot. Bằng chứng thực tế đang có trong repo vẫn chưa đủ để xác nhận Gate 1–3 đã đạt.

| Gate | Trạng thái theo yêu cầu | Bằng chứng thực tế hiện có / giới hạn |
|---|---|---|
| **Gate 1 — vấn đề và khả thi pilot** | **ĐẠT THEO GIẢ ĐỊNH — chưa kiểm chứng thực tế** | Phạm vi, nguyên nhân và AS-IS/TO-BE đã ghi; người dùng xác nhận tình huống Bước 2. Dashboard v2 có target thiết kế và owner theo vai trò; repo chưa có baseline thời gian hoặc phê duyệt quyền nguồn. |
| **Gate 2 — chất lượng và khả năng dùng trong workflow** | **ĐẠT THEO GIẢ ĐỊNH — chưa kiểm chứng thực tế** | Repo chưa có log đề xuất AI, trích nguồn, QA mẫu, kết quả xác minh, tỷ lệ làm lại/chuyển người hoặc quan sát sử dụng workflow. Khả năng agent cũng chưa được kiểm chứng. |
| **Gate 3 — mở rộng / sửa / dừng** | **ĐẠT THEO GIẢ ĐỊNH — chưa kiểm chứng thực tế** | Chưa có kết quả pilot để so với baseline/mục tiêu, xác nhận owner vận hành, chi phí, governance hoặc biên bản quyết định. |

**Cách hiểu trạng thái:** Theo chỉ định của người dùng, bảng lộ trình được đánh dấu đạt theo giả định cho bài tập. Không xem đây là phê duyệt vận hành, bằng chứng pilot đã chạy, hoặc căn cứ mở rộng dữ liệu thật. Target trong v2 là thiết kế cho bài tập; baseline thực tế và QA vẫn phải được đo trước pilot.

### Baseline chưa có và target thiết kế cho bài tập

- **Đã có dữ kiện chẩn đoán:** 5/8 báo cáo (62,5%) thiếu ít nhất một chi tiết đối chiếu trong một tuần, theo xác nhận người dùng. Đây không phải baseline AI, thời gian hoặc outcome.
- **Chưa có baseline vận hành:** bắt đầu log sự kiện trước pilot; tính thời gian nhận→xác minh/đóng theo median/P90, QA sai ghép, rework và hoàn trả bằng các công thức ở workbook.
- **Target chất lượng:** 100% đề xuất có mã nguồn/trường căn cứ truy lại; 0 lỗi ghép nghiêm trọng trong QA. Đây là ngưỡng thiết kế thận trọng cho bài tập, không phải mức rủi ro trường đã phê duyệt.
- **Target kiểm soát workflow:** 100% liên hệ dựa trên AI phải có xác minh nhân viên được ghi trước liên hệ (đúng TO-BE).
- **Target hiệu quả:** median thời gian và tỷ lệ rework thấp hơn baseline; P90 không xấu hơn; tỷ lệ hoàn trả cao hơn baseline trong cùng mẫu số/cửa sổ. Không đặt mức phần trăm khi chưa có baseline.
- **Owner theo vai trò:** nhân viên Lost&Found ghi vụ việc/xác minh; data steward quản lý nguồn; QA reviewer độc lập gán nhãn; process owner xem kết quả và quyết định sửa/dừng. Nguyễn Ngọc Linh là owner của bài nộp, không phải mặc định owner vận hành trường.

### Điều kiện trước pilot

1. Bố trí vai trò pilot/process owner, data steward, QA reviewer, owner agent và người phê duyệt theo tổ chức trường.
2. Ghi nguồn dữ liệu, quyền/mục đích sử dụng, thời hạn lưu và quy trình xác minh/liên hệ; dùng dữ liệu giả lập/đã khử định danh đến khi quyền thật được duyệt.
3. Kiểm tra agent có sổ tập trung, hiển thị nguồn/ngày cập nhật và dừng/chuyển người khi thiếu căn cứ.
4. Ghi baseline trước pilot; dùng các target thiết kế trong memo/dashboard để đánh giá thử, và xin phê duyệt trường trước khi áp dụng thật.
5. Áp dụng điều kiện dừng khi có ghép sai nghiêm trọng, mất nguồn, hoặc bỏ qua xác minh; thử lại sau khi QA kiểm chứng sửa lỗi.

**Quy tắc qua gate:** owner vận hành của trường xem bằng chứng và target thiết kế, phê duyệt ngưỡng trước pilot. Gate chỉ đạt khi tiêu chí chất lượng, hành vi và giá trị đều đạt, điều kiện quyền/governance được đáp ứng và quyết định được ghi lại. Thời gian trôi qua tự nó không phải bằng chứng đạt gate.

## Bước 5 — Dashboard Hành Động v1

Dashboard được lập tại `v1/dashboard_hanh_dong_v1.xlsx`, với ba sheet: Dashboard v1, Định nghĩa chỉ số, và Gate & quyết định. Đây là bản trước phản biện, chưa phải dữ liệu kết quả: hiện chưa có log pilot, mốc đầu định lượng, target thiết kế hay owner theo vai trò trong workbook v1.

Bảy chỉ số đề xuất bao phủ năm tầng: tỷ lệ vụ đủ điều kiện có đề xuất AI được xem (sử dụng, product; chỉ báo chẩn đoán); tỷ lệ đề xuất truy vết được về nguồn (chất lượng, product); tỷ lệ có xác minh người thật trước liên hệ (hành vi, workflow); thời gian đến khi xác minh chủ/đóng vụ (năng suất, workflow); tỷ lệ ghép sai trong QA (chất lượng, product); tỷ lệ vụ phải tìm lại/sửa (chất lượng, workflow); và tỷ lệ đồ nhặt được trả cho chủ đã xác minh (giá trị, workflow).

Trong v1, baseline vận hành và owner chưa có; v2 nêu target thiết kế và owner theo vai trò, còn baseline phải đo bằng log trước pilot. Sheet định nghĩa nêu công thức, quyết định hỗ trợ và giới hạn diễn giải. Không dùng mức sử dụng đơn lẻ để kết luận giá trị; có nguồn trích dẫn cũng không thay QA kết quả ghép. Gate 1 cần tạo log, có quyền dùng nguồn và đo baseline; Gate 2 cần QA và log hành vi; Gate 3 so kết quả với target để quyết định tiếp tục, sửa hoặc dừng.
## Bước 6 — Kiểm tra chéo và chốt bản v2

> Đây là **tự kiểm tra phản biện của Codex** dựa trên các tài liệu hiện có. Chưa có góp ý thực tế từ nhóm khác; nội dung dưới đây không được ghi là phản hồi của peer reviewer.

### Kết quả kiểm tra chéo

| Trục | Nhận định dựa trên bản hiện tại | Góp ý cụ thể | Trạng thái |
|---|---|---|---|
| Phạm vi | README/memo nêu Lost&Found AI Agent, nhân viên phụ trách đồ thất lạc, bốn bước từ tiếp nhận đến liên hệ và vấn đề mất nhiều thời gian tìm chủ. Memo có chỉ số thời gian nhưng hiện chưa đo; khả năng cụ thể của agent chưa được xác minh. | Chốt định nghĩa mốc bắt đầu/kết thúc và trường hợp chưa tìm thấy chủ; kiểm tra sản phẩm thật có thể trả mã nguồn/ngày cập nhật và chuyển người không. | Cần sửa |
| Framework | Năm trục và Gartner-Lite gắn với hai quan sát người dùng xác nhận: báo cáo thiếu chi tiết và phân tán. Memo ghi độ tin cậy vừa, nhưng chưa có mẫu hồ sơ gốc; quan hệ nhân quả chưa được đo. | Giữ nhãn đây là chẩn đoán có căn cứ từ xác nhận người dùng, nhưng chưa kiểm chứng độc lập; không coi trích nguồn của AI là bằng chứng câu trả lời đúng. | Cần lưu ý |
| Chỉ số | v1 có bảy chỉ số qua năm tầng, có nguồn đề xuất và hành động khi xấu; baseline thật chưa có. Chỉ số hoàn trả thiếu định nghĩa rõ về mẫu số/cửa sổ theo dõi. | Chỉ rõ “đủ điều kiện” và cửa sổ theo dõi nhất quán; ghi baseline là chưa có và target theo điều kiện/so sánh baseline. | Đã sửa trong v2 |
| Hành động | Bước 4 có ba gate và xử lý khi chưa đạt. Gate được đánh dấu đạt theo giả định theo yêu cầu người dùng, chưa có bằng chứng pilot. | V2 ghi owner theo vai trò, target thiết kế và tách trạng thái giả định khỏi bằng chứng vận hành. | Đã làm cho bài tập; vận hành còn chặn bởi baseline/quyền/QA |

### Hai góp ý ưu tiên

1. **Chỉ số giá trị chưa đủ định nghĩa để so sánh:** tỷ lệ hoàn trả cần mẫu số “báo cáo đồ nhặt đủ điều kiện” và cửa sổ theo dõi thống nhất; nếu không, baseline/pilot có thể không tương đương.
2. **Trạng thái gate có thể bị hiểu nhầm:** “đạt theo giả định” là chỉ định hoàn tất bài tập, không phải kết quả QA/pilot. Workbook v2 cần cho thấy riêng trạng thái giả định và bằng chứng thực tế hiện có.

### Các thay đổi trong bản v2

| Thay đổi | Nội dung trước | Nội dung v2 | Góp ý hoặc vấn đề được xử lý |
|---|---|---|---|
| 1. Định nghĩa lại chỉ số giá trị | “Tỷ lệ báo cáo đồ nhặt được được hoàn trả cho chủ đã xác minh”; mẫu số và thời hạn theo dõi chưa rõ. | “Tỷ lệ báo cáo đồ nhặt đủ điều kiện được trả cho chủ đã xác minh trong cửa sổ theo dõi do nhóm duyệt”; công thức yêu cầu cùng tiêu chí đủ điều kiện và cửa sổ ở baseline/pilot. | Góp ý ưu tiên 1; giúp chỉ số so sánh được mà không tự đặt mẫu số hay thời hạn. |
| 2. Tách trạng thái gate khỏi bằng chứng | Dashboard v1 nêu logic gate nhưng chưa ghi trong workbook việc gate nào chỉ được giả định đạt và dữ liệu nào thực sự có. | Sheet “Gate & quyết định” của v2 ghi “đạt theo giả định” cùng bằng chứng thực tế còn thiếu; target thiết kế và owner theo vai trò được điền cho bài tập. | Tự kiểm ưu tiên 2; tránh trình bày giả định như kết quả vận hành. |

### Quyết định cuối

- **Quyết định bài tập:** Nguyễn Ngọc Linh chọn **SỬA** và hoàn tất điều kiện readiness trước khi cân nhắc pilot dữ liệu thật.
- **Phạm vi quyết định:** Đây là lựa chọn cho bài nộp cá nhân, không phải phê duyệt vận hành hoặc quyết định thay mặt nhà trường.
- **Căn cứ:** Chưa có phê duyệt quyền truy cập, baseline, QA output hoặc log pilot; nguồn dữ liệu và khả năng agent chưa được kiểm chứng trong repo. Dashboard v2 ghi rõ dữ kiện nào chưa tồn tại và target nào là đề xuất thiết kế.
- **Điều kiện tiếp theo:** Chỉ xem xét bắt đầu pilot sau khi chỉ định owner, duyệt nguồn/quyền, chốt định nghĩa đo và baseline, xác nhận mục tiêu/ngưỡng QA, và kiểm tra agent có thể truy vết nguồn/chuyển người như TO-BE yêu cầu.

**Bản v2 đã cập nhật:** [`dashboard/dashboard_hanh_dong_v2.xlsx`](../dashboard/dashboard_hanh_dong_v2.xlsx). Workbook giữ bảy chỉ số, thêm định nghĩa chặt hơn cho chỉ số hoàn trả và thêm ghi chú bằng chứng/trạng thái gate. Dashboard v1 được giữ nguyên để đối chiếu.

## Checklist checkpoint và tự kiểm bổ sung

Rubric §6.2–§6.5 được người dùng cung cấp và đã dùng để cập nhật cấu trúc README, dashboard và memo. Một yêu cầu trước đó còn nhắc checkpoint phút 40/80, năm dấu hiệu đạt, lỗi thường gặp và năm câu tự kiểm, nhưng nguyên văn các tiêu chí này chưa có trong repo hoặc nội dung được cung cấp. Không tự đặt tiêu chí thay thế.

| Mục bổ sung | Trạng thái |
|---|---|
| Checkpoint phút 40 | Chưa thể đối chiếu checklist cụ thể nếu không có nguyên văn. |
| Checkpoint phút 80 | **Đạt có điều kiện cho bài tập:** target thiết kế và owner tài liệu/owner theo vai trò đã ghi; baseline vận hành chưa có nên chưa đạt điều kiện pilot thực tế. |
| Năm dấu hiệu đạt, lỗi thường gặp, năm câu tự kiểm | Cần cung cấp checklist nguyên văn để đối chiếu. |
