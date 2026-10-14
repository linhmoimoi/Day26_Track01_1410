# Day26_Track01_1410 — Bàn giao Lost&Found AI Agent

## 1. Thành viên

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
|---|---|---|---|
| Nguyễn Ngọc Linh | 2A202602480 | Toàn bộ bài lab: chẩn đoán, thiết kế, dashboard, memo và tổng hợp | Không có góp ý peer review được ghi nhận trong bộ bàn giao; Bước 6 là tự kiểm tra của Codex. |

Đây là bài nộp cá nhân của Nguyễn Ngọc Linh. Phần phụ trách ghi người chịu trách nhiệm viết; ID thư mục hiện tại `Day26_Track01_1410` được giữ nguyên.

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
| Product — chất lượng | Tỷ lệ đề xuất truy vết được về nguồn và trường căn cứ | Chưa có baseline AI vì chưa có đầu ra/log nguồn; đo trên QA đầu tiên trước pilot. | Target thiết kế: 100% đề xuất có nguồn và trường căn cứ truy lại được; thiếu nguồn thì dừng. | Log đề xuất AI gồm mã vụ việc/nguồn, trường căn cứ, thời điểm; hiện chưa có trong repo, cần tạo trước pilot. | Data steward duy trì nguồn; QA reviewer kiểm mẫu. Owner vận hành theo cá nhân chưa có tên. |
| Workflow — năng suất | Thời gian từ nhận báo cáo đồ nhặt đến xác minh chủ hoặc đóng vụ việc (median, P90) | Chưa có baseline vì sổ hiện tại thiếu mốc; thu thập trong quy trình hiện tại trước pilot. | Target thiết kế: median thấp hơn baseline, P90 không xấu hơn, chất lượng không giảm. | Sổ vụ việc ghi thời điểm nhận, bắt đầu xử lý, xác minh chủ, đóng vụ; cần tạo trước pilot. | Nhân viên Lost&Found ghi mốc; process owner xem báo cáo. Chưa có cá nhân vận hành được chỉ định. |

Dashboard v2 có 7 metric qua năm tầng. Baseline chẩn đoán duy nhất hiện có là 5/8 báo cáo (62,5%) thiếu chi tiết đối chiếu trong mẫu một tuần do người dùng xác nhận; đây không phải baseline KPI của agent hay thời gian xử lý. Các nguồn nêu là nguồn cần thu thập theo thiết kế, chưa phải log vận hành hiện có.

## 6. Quyết định

**Quyết định bài tập: Sửa** readiness trước khi pilot dữ liệu thật. Người chọn quyết định cho bài nộp cá nhân: Nguyễn Ngọc Linh. Lý do: chưa có log baseline, phê duyệt nguồn/quyền hay QA pilot. Hai thay đổi v2 so với v1: (1) chốt cách định nghĩa mẫu số và cửa sổ theo dõi cho tỷ lệ hoàn trả; (2) tách trạng thái gate “đạt theo giả định” khỏi bằng chứng pilot thực tế. Đây không phải phê duyệt vận hành của trường.

## Artifact và trạng thái

- [Dashboard hành động v2](dashboard/dashboard_hanh_dong_v2.xlsx) — bản hiện hành sau tự kiểm tra của Codex.
- [Memo quyết định](memo/memo_quyet_dinh.md) — năm phần theo §6.5 và phân tích chi tiết.
- [Dashboard hành động v1](v1/dashboard_hanh_dong_v1.xlsx) — bản trước phản biện, được giữ để đối chiếu.

| Tiêu chí | Trạng thái |
|---|---|
| Repo theo cấu trúc §6.2 | Đạt về các artifact bắt buộc; bài nộp cá nhân, giữ nguyên ID thư mục hiện tại. |
| Dashboard theo §6.4 | Đạt có điều kiện: metric, công thức, nguồn thu thập, target thiết kế, vai trò owner và hành động đã điền. Baseline AI/vận hành chưa có vì chưa có log. |
| Memo năm phần theo §6.5 | Đạt có điều kiện: năm phần và hai thay đổi đã ghi; peer review thực tế không có trong hồ sơ, Bước 6 là self-check Codex. |
| Gate 30–60–90 | Đạt theo giả định cho bài tập; chưa xác nhận thực tế, không phải kết quả pilot hay phê duyệt vận hành. |
| Checkpoint phút 80 | Đạt có điều kiện cho bài tập: target thiết kế và owner theo vai trò đã ghi; baseline vận hành chưa có nên chưa đủ điều kiện pilot thực tế. |

### Mặc định đã chốt cho bài tập và giới hạn vận hành

- Phạm vi là bài nộp cá nhân; owner tài liệu là Nguyễn Ngọc Linh. Owner vận hành được ghi theo vai trò (nhân viên Lost&Found, data steward, QA reviewer, process owner), không gán tên người thật.
- Target trong dashboard là target thiết kế cho bài tập; trước pilot với dữ liệu trường cần phê duyệt của đơn vị vận hành.
- Không có log thời gian, AI, QA hay hoàn trả trong repo; baseline các metric đó được ghi “chưa có”, không suy ra từ mẫu 5/8.
- Nguồn dự kiến là sổ vụ việc và log đề xuất có mã vụ việc, mốc thời gian, nguồn, căn cứ, xác minh và kết quả; cần tạo/kiểm tra trước khi pilot.
- Không có bằng chứng trường đã cho phép truy cập dữ liệu hoặc phê duyệt thời hạn lưu; không dùng dữ liệu cá nhân thật cho đến khi được phép.
- Không có góp ý peer review được ghi nhận; không tạo lời góp ý giả. Hai thay đổi v2 đến từ tự kiểm tra của Codex.

Cập nhật tài liệu: 2026-10-14.
