# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` |xe con chở người dưới 9 chỗ, gầm thấp hoặc vừa |Thân xe liền khối, không có thùng chở hàng riêng |
| `truck` |Xe chuyên chở hàng hóa, vật liệu. |Có cabin tách biệt với thùng chở hàng phía sau. |
| `bus` |Xe chở khách cỡ lớn | Dạng khối hộp dài, nhiều cửa sổ và ghế ngồi dọc theo lối đi|
| `van` | Xe khối hộp trần cao phẳng để chở đồ hoặc 9–16 người.|Thùng và cabin liền một khối, có cửa trượt hông hoặc mở đôi phía sau |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: ôm vừa khít mép ngoài đối tượng, không thừa nền và không cắt chi tiết
- Vật thể bị che khuất: che bởi vật cản tíc occluded
- Vật thể bị cắt bởi rìa ảnh: chỉ vẽ phần sát mép tíc truncated
- Vật thể rất nhỏ/mơ hồ: bỏ qua nếu ko nhận diện dc bằng mắt thường

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_005 |xe sát nhau không phân biệt được loại xe | gán nhãn từng bounding box riêng | tránh bỏ sót vật cản ảnh hưởng đến an toàn |
| `drive_026 |xe bị cắt khỏi khung hình |chỉ bao bounding box phần thấy được |không được vẽ vượt ra ngoài |
| `drive_041 |ảnh mờ |không gán nhãn cho các dồi tượng quá xa |  có kích thước tối thiểu cho nhãn   dưới <15 pixel sẽ ko gán |
