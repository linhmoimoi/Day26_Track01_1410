# Day26_Track01 — Bộ bàn giao Lost&Found AI Agent

## Kết luận rà soát

| Hạng mục | Trạng thái | Căn cứ |
|---|---|---|
| Phạm vi, chẩn đoán, AS-IS/TO-BE, luồng tin cậy | Đạt có điều kiện | Đã ghi theo xác nhận trong cuộc trò chuyện; chưa có hồ sơ gốc để kiểm chứng độc lập. |
| Dashboard v2 và năm tầng chỉ số | Đạt có điều kiện | Có 7 metric, định nghĩa/cách tính, nguồn dự kiến, baseline, mục tiêu, owner và hành động khi xấu. Giá trị thật, nguồn log vận hành và owner vẫn cần nhóm xác nhận. |
| Gate 30–60–90 | Đạt theo giả định cho bài tập; chưa xác nhận thực tế | Chưa có phê duyệt nguồn/quyền, baseline, log pilot/QA hay owner được chỉ định. |
| Checkpoint phút 40/80 và checklist đánh giá | Chưa thể xác nhận đầy đủ | Repo không có nguyên văn checklist, năm dấu hiệu đạt, lỗi thường gặp hay năm câu tự kiểm. Checkpoint phút 80 còn thiếu baseline, target và owner. |
| §6.3/§6.4 | Chưa thể hoàn thiện chính xác | Không tìm thấy đề bài/nguyên văn phần này trong repo; memo giữ TODO có giải thích. |
| Quyết định cuối của nhóm / peer review | Chưa có | Memo nêu đề xuất của Codex; không có góp ý peer review hoặc quyết định nhóm được cung cấp. |

**Không đánh dấu toàn bộ lab đạt.** Gate “đạt theo giả định” là trạng thái bài tập được yêu cầu, không phải kết quả pilot hoặc phê duyệt vận hành.

## Phạm vi và bằng chứng

- **Product:** Lost&Found AI Agent.
- **User:** Nhân viên phụ trách đồ thất lạc tại trường học.
- **Workflow:** Tiếp nhận báo cáo mất/nhặt được → phân loại → đối chiếu → liên hệ người báo sau khi nhân viên xác minh.
- **Vấn đề:** Mất thời gian tìm chủ; biểu mẫu/sổ chưa ghi mốc bắt đầu và kết thúc.
- **Bằng chứng đã xác nhận:** Trong một tuần có 8 báo cáo, 5 báo cáo thiếu ít nhất một chi tiết đối chiếu; báo cáo đến từ biểu mẫu, tin nhắn và ghi nhận trực tiếp, nhân viên tìm lần lượt qua các kênh. Đây là xác nhận của người dùng trong cuộc trò chuyện, chưa có hồ sơ gốc để kiểm tra độc lập.
- **Hai nguyên nhân được chẩn đoán:** thông tin thiếu/không nhất quán; báo cáo phân tán khiến phải tìm thủ công. Mức tin cậy hiện tại vừa.

Chi tiết framework, giới hạn bằng chứng, quy trình và quyết định được ghi trong [memo quyết định](memo/memo_quyet_dinh.md).

## Artifact bàn giao

- [Dashboard hành động v2](dashboard/dashboard_hanh_dong_v2.xlsx) — bản hiện hành, sau tự kiểm tra của Codex.
- [Memo quyết định](memo/memo_quyet_dinh.md) — chẩn đoán, thiết kế, gate, metric, phản biện, thay đổi v2 và TODO theo §6.4.
- [Dashboard hành động v1](v1/dashboard_hanh_dong_v1.xlsx) — bản đối chiếu được giữ nguyên.

v2 gồm 3 sheet và 7 chỉ số qua năm tầng: sử dụng, chất lượng/độ tin cậy, hành vi, năng suất và giá trị; có metric product và workflow. Mỗi chỉ số có định nghĩa/cách tính, nguồn cần thu thập, baseline hiện trạng, mục tiêu, owner và hành động khi xấu. Chỗ chưa có dữ kiện được để rõ “chưa đo được” hoặc “cần nhóm xác nhận”, không điền số giả.

## Thay đổi thực chất từ v1 sang v2

1. **Metric giá trị:** v1 chưa chốt mẫu số/cửa sổ theo dõi; v2 yêu cầu báo cáo đồ nhặt đủ điều kiện được trả cho chủ đã xác minh trong cửa sổ do nhóm duyệt, và dùng cùng tiêu chí ở baseline/pilot. Lý do: tạo phép so sánh nhất quán mà không tự đặt target.
2. **Trạng thái gate:** v1 ghi logic quyết định; v2 ghi riêng “đạt theo giả định” và bằng chứng thực tế hiện có, cùng đề xuất của Codex chờ nhóm xác nhận. Lý do: tránh nhầm giả định bài tập với kết quả pilot.

Bảng phản biện là **tự kiểm tra của Codex**; không có nhận xét nào được gán cho peer reviewer.

## Việc cần nhóm xác nhận

- Tên nhóm và quyết định cuối có thẩm quyền.
- Nguồn dữ liệu gốc để đối chiếu xác nhận 8/5 báo cáo; nguồn được phép dùng, quyền truy cập, thời hạn lưu và owner.
- Pilot/process owner, data owner, QA reviewer, owner agent và người phê duyệt cuối.
- Schema, định nghĩa baseline, mục tiêu, ngưỡng QA, cỡ mẫu và cách tính vụ việc chưa đóng.
- Nội dung chính thức §6.3/§6.4 và checklist nguyên văn (checkpoint phút 40/80, năm dấu hiệu đạt, lỗi thường gặp, năm câu tự kiểm).
- Người kiểm tra chéo thực tế, nếu có; hiện chưa có peer review trong repo.

Cách lấy số: nhóm thống nhất định nghĩa và người ghi; bổ sung mã vụ việc cùng các mốc nhận, bắt đầu tìm, đề xuất, xác minh, liên hệ, đóng; lưu nhãn QA và trạng thái hoàn trả. Tính baseline trước khi đặt mục tiêu, rồi so sánh cùng định nghĩa/cửa sổ theo dõi. Chưa có log thì giữ “chưa đo được”.

## Quyết định và checkpoint

Đề xuất của Codex là hoàn thiện readiness trước pilot với dữ liệu thật. Chưa có quyết định pilot do nhóm cung cấp. Checkpoint phút 40/80 không thể đối chiếu trọn vẹn khi thiếu checklist gốc; theo tiêu chí được nêu trong yêu cầu, checkpoint phút 80 **chưa đạt** vì baseline, target và owner còn thiếu. Năm dấu hiệu đạt, lỗi thường gặp và năm câu tự kiểm cần đối chiếu khi nhóm cung cấp nguyên văn.

Cập nhật tài liệu: 2026-10-14.
