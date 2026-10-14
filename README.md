# Day26_Track01 — Bộ bàn giao

## Phạm vi vấn đề AI

- **Product:** Lost&Found AI Agent
- **User:** Nhân viên phụ trách đồ thất lạc tại trường học
- **Workflow:** Tiếp nhận báo cáo mất/nhặt được → phân loại đồ vật → đối chiếu báo cáo → liên hệ người báo khi có kết quả phù hợp
- **Problem:** Nhân viên mất nhiều thời gian tìm chủ sở hữu đồ vật được nhặt thấy; thời gian xử lý chưa được đo bằng mốc bắt đầu/kết thúc.

**Một dòng phạm vi:** “Nhân viên phụ trách đồ thất lạc tại trường học dùng Lost&Found AI Agent để tiếp nhận và phân loại báo cáo, đối chiếu đồ vật mất/nhặt được rồi liên hệ người báo, nhưng mất nhiều thời gian tìm chủ sở hữu.”

## Chẩn đoán Bước 2

Theo xác nhận của người dùng ngày 2026-10-14, trong một tuần có 8 báo cáo được xem xét và 5 báo cáo thiếu ít nhất một chi tiết nhận diện/đối chiếu; báo cáo đến từ biểu mẫu, tin nhắn và ghi nhận trực tiếp nên nhân viên phải tìm lần lượt qua các kênh. Biểu mẫu và sổ theo dõi không ghi thời điểm bắt đầu tìm và xác nhận được chủ.

Hai nguyên nhân gốc được xác định ở mức tin cậy vừa: (1) thông tin báo cáo thiếu nhất quán; (2) báo cáo phân tán qua nhiều kênh, dẫn đến đối chiếu thủ công. Chưa có hồ sơ gốc được đính kèm hoặc kiểm tra độc lập. Chi tiết framework, bằng chứng và giới hạn nằm trong [`memo/memo_quyet_dinh.md`](memo/memo_quyet_dinh.md).

## Thành phần

- `dashboard/dashboard_hanh_dong_v2.xlsx`: bản v2 để cập nhật sau kiểm tra chéo.
- `memo/memo_quyet_dinh.md`: phạm vi và chẩn đoán theo framework; phần nội dung §6.4 còn chờ hướng dẫn.
- `v1/dashboard_hanh_dong_v1.xlsx`: bản v1 lưu để đối chiếu với v2.

## Thông tin bàn giao

- Tên nhóm: TODO
- Nguồn dữ liệu gốc: TODO
- Người kiểm tra chéo: TODO
- Ngày cập nhật: 2026-10-14

## Thiết kế Bước 3

TO-BE: nhân viên nhập báo cáo vào sổ vụ việc tập trung theo trường thống nhất; Lost&Found AI Agent phân loại và đề xuất ứng viên có mã nguồn; nhân viên kiểm tra, xác minh và quyết định liên hệ. Khi thiếu dữ liệu, nguồn mâu thuẫn hoặc có nhiều ứng viên, agent dừng và chuyển cho người. Owner, quyền truy cập, chi phí, ngưỡng QA và mốc đo còn cần xác định. Chi tiết AS-IS/TO-BE, luồng tin cậy và điều kiện sẵn sàng nằm trong [`memo/memo_quyet_dinh.md`](memo/memo_quyet_dinh.md).

## Lộ trình Bước 4

Người dùng đã chấp thuận lộ trình ở mức thiết kế ngày 2026-10-14. Memo có ba decision gate 0–30, 31–60 và 61–90 ngày; chưa gate nào được đánh giá là đạt. Mốc thời gian không tự xác nhận gate; tiêu chí chất lượng, hành vi, giá trị, owner và ngưỡng số liệu còn cần nhóm xác nhận trước pilot. Xem bảng gate và điều kiện dừng/thử lại trong [`memo/memo_quyet_dinh.md`](memo/memo_quyet_dinh.md).
