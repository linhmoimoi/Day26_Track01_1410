# Day26_Track01_1410 — Bàn giao Lost&Found AI Agent

## 1. Thành viên

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
|---|---|---|---|
| CẦN NHÓM XÁC NHẬN — chưa có danh sách thành viên | CẦN NHÓM XÁC NHẬN | CẦN NHÓM XÁC NHẬN người chịu trách nhiệm viết từng phần | CẦN NHÓM XÁC NHẬN nhóm được phản biện và góp ý cụ thể; chưa có ghi nhận peer review trong repo. Nếu chưa tham gia phản biện, ghi rõ “chưa tham gia”. |

Danh sách trên là ô chờ xác nhận, không phải thành viên giả lập. Cần một dòng cho mỗi thành viên thật; phần phụ trách ghi người chịu trách nhiệm viết, không loại trừ đóng góp của các thành viên khác.

## 2. Phạm vi

Lost&Found AI Agent phục vụ nhân viên phụ trách đồ thất lạc tại trường học. Quy trình gồm tiếp nhận báo cáo mất/nhặt được → chuẩn hóa/phân loại → đối chiếu ứng viên → nhân viên xác minh và liên hệ. Vấn đề là mất thời gian tìm chủ; biểu mẫu/sổ chưa ghi mốc bắt đầu và kết thúc.

## 3. Nguyên nhân gốc

Hai nguyên nhân ở mức tin cậy vừa: thông tin báo cáo thiếu/không nhất quán; báo cáo phân tán qua biểu mẫu, tin nhắn và ghi nhận trực tiếp nên phải tìm thủ công. Framework đã dùng: Năm trục chẩn đoán và Gartner-Lite. Bằng chứng là xác nhận của người dùng trong cuộc trò chuyện: 8 báo cáo trong một tuần, 5 thiếu ít nhất một chi tiết đối chiếu; chưa có hồ sơ gốc để kiểm chứng độc lập. Chi tiết nằm trong [memo](memo/memo_quyet_dinh.md).

## 4. Cách làm mới

| Thay đổi bắt buộc | Thiết kế |
|---|---|
| Nguồn kiểm chứng | Sổ vụ việc tập trung; mỗi đề xuất AI hiển thị mã bản ghi, trường căn cứ và ngày cập nhật nếu có. Nguồn/quyền sử dụng cần trường phê duyệt. |
| Người chịu trách nhiệm | Nhân viên kiểm tra nguồn, xác minh chủ và quyết định liên hệ; cần nhóm chỉ định data owner, process/pilot owner và QA reviewer. |
| AI không chắc | Khi thiếu dữ liệu, nguồn mâu thuẫn, nhiều ứng viên hoặc không truy được căn cứ, agent dừng và chuyển cho nhân viên. |

## 5. Chỉ số

| Cấp | Chỉ số | Baseline | Target | Nguồn dữ liệu | Owner |
|---|---|---|---|---|---|
| Product — chất lượng | Tỷ lệ đề xuất truy vết được về nguồn và trường căn cứ | Chưa đo: chưa có đầu ra AI/log nguồn. | CẦN NHÓM XÁC NHẬN ngưỡng QA trước pilot. | Log đề xuất AI: mã vụ việc/nguồn, trường căn cứ, thời điểm; hiện chưa được xác minh có sẵn. | CẦN NHÓM XÁC NHẬN owner agent và data owner. |
| Workflow — năng suất | Thời gian từ nhận báo cáo đồ nhặt đến xác minh chủ hoặc đóng vụ việc (median, P90) | Chưa đo: biểu mẫu/sổ chưa ghi đủ mốc. | CẦN NHÓM XÁC NHẬN sau khi đo baseline và chốt cách tính vụ chưa đóng. | Sổ vụ việc ghi thời điểm nhận, bắt đầu xử lý, xác minh chủ, đóng vụ; cần triển khai/kiểm tra khả năng thu thập. | CẦN NHÓM XÁC NHẬN process owner và data owner. |

Dashboard v2 có 7 metric qua năm tầng. Các nguồn nêu là nguồn cần thu thập theo thiết kế; chưa phải log vận hành hiện có. Không dùng dữ kiện chẩn đoán 5/8 làm baseline KPI nếu chưa xác nhận cùng định nghĩa và cửa sổ đo.

## 6. Quyết định

**Sửa** readiness trước khi pilot dữ liệu thật vì chưa có baseline, target, owner được chỉ định, hoặc phê duyệt nguồn/quyền. Hai thay đổi v2 so với v1: (1) chốt cách định nghĩa mẫu số và cửa sổ theo dõi cho tỷ lệ hoàn trả; (2) tách trạng thái gate “đạt theo giả định” khỏi bằng chứng pilot thực tế. Đây là đề xuất của Codex, chưa phải quyết định của nhóm.

## Artifact và trạng thái

- [Dashboard hành động v2](dashboard/dashboard_hanh_dong_v2.xlsx) — bản hiện hành sau tự kiểm tra của Codex.
- [Memo quyết định](memo/memo_quyet_dinh.md) — năm phần theo §6.5 và phân tích chi tiết.
- [Dashboard hành động v1](v1/dashboard_hanh_dong_v1.xlsx) — bản trước phản biện, được giữ để đối chiếu.

| Tiêu chí | Trạng thái |
|---|---|
| Repo theo cấu trúc §6.2 | Đạt về các artifact bắt buộc; tên thư mục nhóm và thông tin thành viên cần nhóm xác nhận. |
| Dashboard theo §6.4 | Đạt có điều kiện: đủ metric, công thức, nguồn dự kiến, baseline/target/owner placeholder và hành động; chưa có số baseline/target hay owner thật. |
| Memo năm phần theo §6.5 | Đạt có điều kiện: nội dung và hai thay đổi đã ghi; peer review là tự kiểm của Codex, owner và quyết định nhóm còn thiếu. |
| Gate 30–60–90 | Đạt theo giả định cho bài tập; chưa xác nhận thực tế, không phải kết quả pilot hay phê duyệt vận hành. |
| Checkpoint phút 80 | Chưa đạt: baseline, target và owner chưa được xác nhận. |

### Việc cần nhóm xác nhận

- Tên nhóm để đặt tên repo/thư mục theo quy ước và danh sách họ tên, MSSV, phần phụ trách của từng thành viên.
- Nhóm đã phản biện, nội dung góp ý thực tế; nếu chưa phản biện thì ghi chưa tham gia.
- Baseline, mục tiêu/ngưỡng QA, định nghĩa metric và cách thu thập log.
- Process/pilot owner, data owner, QA reviewer, owner agent và người quyết định cuối.
- Quyền dùng nguồn dữ liệu và thời hạn lưu; hiện chưa có phê duyệt được ghi nhận.

Cập nhật tài liệu: 2026-10-14.
