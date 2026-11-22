# Tự đánh giá — Lương Quốc Việt · G07

## 1. Bốn cảnh cần tự rà soát trên CVAT

Các dòng dưới đây là những cảnh được ưu tiên từ kết quả diff; chúng chưa được xác nhận bằng quan sát ảnh. Cần mở lại CVAT và cập nhật trạng thái sau khi tự rà.

Loại lỗi: `seat_flip`, `wrong_class`, `guess`, `box`, `missing`, `extra`, `lr_flip` (trái/phải mặt), `flag` (thiếu cờ điểm), `ok`.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S01_rgb / S01_ir | Ghế trẻ em và vật | thuộc tính / loại vật | Kiểm tra trạng thái occupied và phân loại vật riêng trên từng ảnh | Chưa rà CVAT |
| S08_rgb / S08_ir | Ghế trẻ em | box / thuộc tính | Kiểm tra sự hiện diện, ranh giới và trạng thái ghế | Chưa rà CVAT |
| D01/D02 | Mắt và face13 | trái/phải / cờ điểm | Rà từng mắt, từng cờ và tay theo người; ảnh D## xoay 90° | Chưa rà CVAT |
| D04/D06 | Kính, dây an toàn, điểm mặt | thuộc tính / cờ điểm | Chỉ chốt từ quan sát ảnh; D06 cần xác định lại tên mắt theo trục y | Chưa rà CVAT |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: Dễ nhầm dấu hoặc gán giá trị đoán thay cho unknown.

Vì sao mình mắc: Ảnh NIR/dữ liệu xoay có thể làm lệch trái-phải và che chi tiết.

Lần sau tránh bằng cách: Làm checklist từng mắt/tay và dùng unknown/occluded/outside đúng khi không thấy.

## 3. Ghi chú về disagreement_log

Điều peer phát hiện đúng theo schema: `occupied=yes` không hợp lệ; `child_seat.occupied` chỉ được `no` hoặc `unknown`. Giá trị quan sát cuối cùng (`no` hay `unknown`) vẫn cần xác nhận trên ảnh.
