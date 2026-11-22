# Danh sách lớp v0 — Lương Quốc Việt · G07

## DMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | eye_state | open / closed / unknown | Phát hiện tài xế chớp/ngậm mí và can thiệp khi buồn ngủ | Có, trừ khi bị che hoặc phản xạ |
| 2 | gaze_zone | road / mirror_l / mirror_r / mirror_c / cluster / center / lap / other | Ước định hướng nhìn để phát hiện lái xe mất tập trung | Có; vùng nhìn vẫn có thể mơ hồ |
| 3 | glasses | none / clear / sun / unknown | Điều chỉnh nhận diện khuôn mặt và trạng thái mắt theo kính | Có, kính râm có thể trông trong suốt trên NIR |
| 4 | hand | driver / passenger; left / right; on_wheel yes/no/unknown | Giám sát tay tác động vô lăng hoặc làm việc khác | Có |
| 5 | phone | held / mounted / lap | Phát hiện tài xế sử dụng điện thoại để cảnh báo | Có khi nhìn thấy hình dạng máy |
| 6 | face13 | 13 điểm + occluded/outside | Ước lượng tư thế và hướng mặt của tài xế | Có với điều kiện mặt đủ rộng |

## OMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person | box người lớn; `seat`, `seatbelt` là thuộc tính | Đếm người và xác định ghế có người | Có, nhưng độ tương phản có thể giảm |
| 2 | face | box mặt; chỉ cần box trong OMS | Xác nhận người ngồi và hỗ trợ định vị vùng mặt | Có nếu mặt đủ rõ |
| 3 | child_seat | `occupied`: no / unknown; `seat` theo xe | Nhận diện ghế trẻ em và hỗ trợ quản lý vùng ghế | Có nếu hình dạng ghế rõ |
| 4 | infant_seat | `facing`: rear / front; `seat` theo xe | Nhận nôi em bé và hỗ trợ quy tắc ghế hướng theo vị trí | Có hình dạng và hướng |
| 5 | object | `type`: bag / box / cup / other; `seat` theo xe | Phát hiện vật để quản lý hành lý và vật trên ghế | Có; nhận dạng theo hình dạng, không theo màu |
| 6 | seat / seatbelt (thuộc tính của `person`) | ghế: rear_left / rear_middle / rear_right; dây: worn_correct / worn_incorrect / not_worn / unknown | Xác định đúng vị trí người và trạng thái dây an toàn | Dây có thể khó thấy; SVIRO chỉ dùng not_worn hoặc unknown |

> Đây là danh sách lớp/thuộc tính theo schema Cabin v1.0; `seat` và `seatbelt` là thuộc tính, không phải nhãn CVAT độc lập.

## 2 câu hỏi leo thang

Câu hỏi bạn muốn hỏi người viết guideline (hoặc khách hàng) vì guideline v1.0 chưa trả lời. Mỗi câu kèm **tên khung** làm ví dụ.

1. Câu hỏi: Khi mắt chỉ che một phần bởi phản xạ mà vẫn đoán được khe mắt, nên dùng closed/open hay unknown?
   Khung ví dụ: D01 — mặt tài xế có đốm phản xạ
   Bạn tạm gán thế nào và vì sao: Gán từng mắt bằng unknown khi không phân biệt rõ khe mở/mí khép.
2. Câu hỏi: Một vật lớn nằm trong ghế trẻ em mà không chắc là đồ vật mang theo hay phần ghế, có phân biệt bằng hai box không?
   Khung ví dụ: S08_rgb
   Bạn tạm gán thế nào và vì sao: Tách child_seat và object riêng nếu vật có ranh giới hình dạng rõ, ghi unknown/no theo guideline.
