# Khai báo dùng AI — Lương Quốc Việt

| # | Công cụ | Bạn hỏi gì (tóm tắt) | Bạn dùng kết quả thế nào | Bạn có kiểm lại không? Bằng gì? |
|---|---|---|---|---|
| 1 | Copilot SDK/Codex | Chạy cabin_check, so annotations XML và tóm tắt review chéo; không tải ảnh ra công cụ ngoài | Dùng kết quả để tạo báo cáo/check_final và danh sách bất đồng | Có; kiểm lại zip, số ảnh, lỗi và nội dung bằng script |
| 2 | Copilot SDK trong VS Code | Đọc hướng dẫn và hồ sơ nộp, kiểm tra trạng thái validator và rà phần văn bản; không đưa ảnh cabin/tài xế cho AI và không nhờ AI gán nhãn | Sửa thông tin hồ sơ và đánh dấu rõ các bất đồng cần xem trên CVAT | Có; chạy lại cabin_check và kiểm tra zip chỉ chứa annotations.xml |
