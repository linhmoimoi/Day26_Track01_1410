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

## Bước 4 — Lộ trình 30–60–90 ngày theo cổng quyết định

Các mốc 0–30, 31–60 và 61–90 ngày là cửa sổ xem xét, không tự động xác nhận thành công. Không gate nào được coi là đạt trước khi owner xem bằng chứng và so với tiêu chí/ngưỡng do nhóm xác nhận.

**Trạng thái:** Người dùng chấp thuận lộ trình ở mức thiết kế ngày 2026-10-14. Các gate chưa được đánh giá/đạt; owner, đường cơ sở và ngưỡng định lượng vẫn cần nhóm xác nhận trước pilot.

### Phạm vi pilot

Pilot dự kiến giới hạn ở nhân viên phụ trách đồ thất lạc tại trường học và quy trình tiếp nhận → chuẩn hóa báo cáo → tìm ứng viên → người kiểm tra/xác minh → liên hệ. Hai nguyên nhân đang xử lý là thông tin báo cáo thiếu/không nhất quán và nguồn báo cáo phân tán. Agent chỉ phân loại/tìm ứng viên có nguồn; nhân viên xác minh và quyết định. Quyền dùng dữ liệu, owner và khả năng thực tế của agent vẫn cần xác nhận.

### Các decision gate

| Giai đoạn / gate | Điều cần chứng minh | Owner | Tiêu chí đạt: chất lượng, hành vi, giá trị | Bằng chứng | Nếu chưa đạt |
|---|---|---|---|---|---|
| **0–30 ngày — Gate 1: vấn đề và khả thi pilot** | Sổ vụ việc, dữ liệu được phép dùng, luồng TO-BE và đường cơ sở đủ rõ để bắt đầu đánh giá có kiểm soát. | **Cần chỉ định:** owner quy trình Lost&Found; data owner; người phê duyệt quyền dữ liệu. | **Chất lượng:** trường dữ liệu cần thiết và quy tắc báo cáo thiếu được nhóm duyệt; nguồn, quyền truy cập và lịch cập nhật được xác định. **Hành vi:** luồng hiện tại/đề xuất được nhân viên xác nhận; chọn được phạm vi nhỏ và ghi nhận được các mốc nhận báo cáo, bắt đầu tìm, xác minh chủ/đóng vụ việc. **Giá trị:** có đường cơ sở về thời gian từ nhận vụ việc đến xác minh chủ (hoặc đóng vụ việc); nhóm xác nhận mục tiêu so sánh và cách tính trước pilot. Cỡ mẫu và mức mục tiêu: **cần nhóm xác nhận**. | AS-IS/TO-BE đã duyệt; danh mục nguồn và owner; phê duyệt quyền truy cập; mẫu báo cáo đã rà soát; bản ghi đường cơ sở và định nghĩa mốc đo; phạm vi pilot được ghi lại. | Không đưa dữ liệu thật vào agent và chưa bắt đầu pilot. Giữ quy trình thủ công; xử lý thiếu owner/quyền/schema/đo lường rồi đánh giá lại. Hết 30 ngày không làm gate tự đạt. |
| **31–60 ngày — Gate 2: chất lượng và dùng được trong workflow** | Agent tạo đề xuất có thể kiểm tra, nhân viên dùng đúng điểm bàn giao và lỗi được phát hiện/ghi nhận. | **Cần chỉ định:** pilot owner; QA reviewer; owner agent; nhân viên phụ trách quy trình. | **Chất lượng:** QA kiểm tra đề xuất khớp, không khớp và trường hợp từ chối; nguồn/mã bản ghi và trường căn cứ truy ngược được; đo tỷ lệ ghép đúng, ghép sai, bỏ sót, từ chối/chuyển người. Ngưỡng chấp nhận và cỡ mẫu: **cần nhóm xác nhận trước khi đánh giá**. **Hành vi:** mọi đề xuất dùng để liên hệ được nhân viên xem và xác minh trước; nhân viên ghi kết quả, sửa sai và trường hợp làm lại; mức sử dụng workflow và tỷ lệ làm lại được theo dõi. Mục tiêu hành vi: **cần nhóm xác nhận**. **Giá trị:** so thời gian xử lý với đường cơ sở Gate 1; mức cải thiện tối thiểu và quy tắc không làm giảm chất lượng: **cần nhóm xác nhận**. | Nhật ký đề xuất kèm nguồn; QA mẫu và nhãn kết quả; log chuyển người/abstain; mã vụ việc và mốc thời gian; quan sát workflow và phản hồi nhân viên; so sánh với baseline. | Sửa dữ liệu/schema hoặc cấu hình; thu hẹp loại vật/nguồn/phạm vi; tiếp tục đánh giá có kiểm soát chỉ khi quyền còn hiệu lực. Nếu lỗi ghép nghiêm trọng, không truy được nguồn hoặc người dùng bỏ qua bước xác minh, dừng dùng đề xuất AI và quay về thủ công cho đến khi QA xác nhận điều kiện thử lại. |
| **61–90 ngày — Gate 3: mở rộng / sửa / dừng** | Kết quả đạt mục tiêu đã duyệt và tổ chức có thể vận hành, quản trị, xử lý lỗi liên tục. | **Cần chỉ định:** người ra quyết định; owner vận hành; data owner; governance/privacy approver. | **Chất lượng:** chỉ số QA (ghép đúng/sai, bỏ sót, nguồn đầy đủ, lỗi nghiêm trọng) đạt ngưỡng nhóm đã duyệt; không có lỗi nghiêm trọng chưa xử lý. **Hành vi:** nhân viên theo đúng bước kiểm tra/xác minh và có kênh phản hồi; owner có thể xử lý cập nhật và sự cố. **Giá trị:** kết quả thời gian xử lý so với baseline đạt mục tiêu nhóm; chi phí/công sức vận hành được nhóm chấp nhận. Tất cả ngưỡng và mục tiêu: **cần nhóm xác nhận**. | Báo cáo so sánh baseline với kết quả; tổng hợp QA và lỗi; bằng chứng sử dụng/handoff; phản hồi người dùng; xác nhận owner, quyền truy cập, lưu/xóa dữ liệu, chi phí và quy trình sự cố; biên bản quyết định. | **Sửa:** khi lỗi có thể khắc phục và ngưỡng chưa đạt; xác định thay đổi cùng điều kiện thử lại. **Kéo dài pilot:** chỉ khi có owner, quyền hợp lệ, kế hoạch đo và câu hỏi còn lại cụ thể; cần phê duyệt lại khoảng thời gian. **Dừng:** khi quyền/governance không đáp ứng, có lỗi nghiêm trọng chưa kiểm soát, hoặc kết quả không đạt mục tiêu sau lần sửa được duyệt. Không mở rộng chỉ vì đã đến ngày 90. |

### Đánh giá hiện trạng các gate — 2026-10-14

**Trạng thái theo yêu cầu của người dùng:** xem cả ba gate là **ĐẠT THEO GIẢ ĐỊNH** để hoàn tất bài tập/lộ trình. Đây là xác nhận giả định do người dùng chỉ định, không phải kết quả được chứng minh bằng hồ sơ pilot. Bằng chứng thực tế đang có trong repo vẫn chưa đủ để xác nhận Gate 1–3 đã đạt.

| Gate | Trạng thái theo yêu cầu | Bằng chứng thực tế hiện có / giới hạn |
|---|---|---|
| **Gate 1 — vấn đề và khả thi pilot** | **ĐẠT THEO GIẢ ĐỊNH — chưa kiểm chứng thực tế** | Phạm vi, nguyên nhân và AS-IS/TO-BE được ghi trong memo; người dùng xác nhận tình huống Bước 2. Repo chưa có owner được chỉ định, nguồn/quyền truy cập được phê duyệt, schema được nhóm duyệt hoặc bản ghi baseline. Dashboard v1/v2 vẫn là mẫu TODO. |
| **Gate 2 — chất lượng và khả năng dùng trong workflow** | **ĐẠT THEO GIẢ ĐỊNH — chưa kiểm chứng thực tế** | Repo chưa có log đề xuất AI, trích nguồn, QA mẫu, kết quả xác minh, tỷ lệ làm lại/chuyển người hoặc quan sát sử dụng workflow. Khả năng agent cũng chưa được kiểm chứng. |
| **Gate 3 — mở rộng / sửa / dừng** | **ĐẠT THEO GIẢ ĐỊNH — chưa kiểm chứng thực tế** | Chưa có kết quả pilot để so với baseline/mục tiêu, xác nhận owner vận hành, chi phí, governance hoặc biên bản quyết định. |

**Cách hiểu trạng thái:** Theo chỉ định của người dùng, bảng lộ trình được đánh dấu đạt cho mục đích hoàn tất bài tập. Không xem đây là phê duyệt vận hành, bằng chứng rằng pilot đã chạy, hoặc căn cứ để mở rộng xử lý dữ liệu thật. Việc đánh giá thực tế cần các bằng chứng và mục tiêu được liệt kê trong từng gate.

### Chỉ số cần nhóm xác nhận

- **Đường cơ sở:** thời gian từ lúc nhận báo cáo đồ nhặt được đến khi người sở hữu được nhân viên xác minh; nếu vụ việc không tìm thấy chủ, cách tính và thời điểm kết thúc cần thống nhất. Hiện chưa có mốc thời gian trong biểu mẫu/sổ.
- **Chất lượng:** cách xác định ghép đúng, ghép sai và bỏ sót; cỡ mẫu QA; ngưỡng chấp nhận cho từng loại lỗi; định nghĩa lỗi nghiêm trọng.
- **Hành vi:** cách tính sử dụng đúng workflow, tỷ lệ làm lại và tỷ lệ chuyển người; mục tiêu tối thiểu.
- **Giá trị:** mức giảm thời gian xử lý có ý nghĩa với nhóm và khoảng so sánh phù hợp.
- **Vận hành:** mức chi phí/công sức chấp nhận được và owner chịu trách nhiệm.

### Quyết định cần chốt trước pilot

1. Chỉ định pilot owner, data owner, QA reviewer, owner agent và người phê duyệt cuối.
2. Xác định nguồn dữ liệu, quyền truy cập, mục đích sử dụng, thời hạn lưu và quy trình xác minh/liên hệ người nhận.
3. Xác nhận agent hỗ trợ được sổ vụ việc tập trung, hiển thị nguồn/ngày cập nhật và dừng/chuyển người khi thiếu căn cứ.
4. Chốt nhóm pilot, cỡ mẫu/độ phủ dữ liệu, đường cơ sở, định nghĩa chỉ số, ngưỡng QA và mục tiêu giá trị trước khi xem kết quả.
5. Chốt tiêu chí dừng và điều kiện thử lại, bao gồm xử lý khi có ghép sai hoặc sự cố dữ liệu.

**Quy tắc qua gate:** owner xem bằng chứng và đối chiếu với mục tiêu đã được nhóm xác nhận. Gate chỉ đạt khi tiêu chí chất lượng, hành vi và giá trị đều đạt, các điều kiện quyền/governance liên quan đã được đáp ứng và quyết định được ghi lại. Thời gian trôi qua tự nó không phải bằng chứng đạt gate.

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
