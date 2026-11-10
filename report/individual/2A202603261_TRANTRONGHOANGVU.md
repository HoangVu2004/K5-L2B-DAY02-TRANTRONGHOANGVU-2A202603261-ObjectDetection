# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên:TRẦN TRỌNG HOÀNG VŨ    
- MSSV:2A202603261
- Email:REALHOANGVU2004@GMAIL.COM
- Lớp:2B
- Link repo bài làm:https://github.com/HoangVu2004/K5-L2B-DAY02-TRANTRONGHOANGVU-2A202603261-ObjectDetection
- Link Colab đã chạy:https://colab.research.google.com/github/HoangVu2004/K5-L2B-DAY02-TRANTRONGHOANGVU-2A202603261-ObjectDetection/blob/main/notebooks/day2_annotation_to_yolo.ipynb#scrollTo=3e0508d8

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train:
- Kết quả checker và lỗi đã xử lý:
- Danh sách ít nhất 10 ảnh đã rà bằng mắt:
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa:
- Commit khóa nhãn ban đầu:

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP | |391 |
| FP | |229 |
| FN | |262 |
| Precision | |0.63 |
| Recall | |0.59 |
| F1 | |0.61 |
| mean_iou_of_matches | | 0.78|
| passed | |FALSE |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch: 8.4.208
- Các tham số thay đổi so với notebook nếu có và lý do:
- Đường dẫn best checkpoint trong phiên chạy:

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision |0.4105453698519763 |
| Recall |0.23026854853628678 |
| mAP50 |0.27225886498171903 |
| mAP50–95 |0.20168300309748077 |

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa?
BUS, drive 057
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box?
mAP50 chỉ yêu cầu IoU đạt 0.5, trong khi mAP50–95 đánh giá ở nhiều ngưỡng IoU từ 0.5 đến 0.95. Vì vậy, mAP50 cao nhưng mAP50–95 thấp thường cho thấy model nhận diện được đối tượng nhưng định vị Bounding Box chưa đủ chính xác.
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?
Lỗi phân loại class có thể xuất phát từ guideline chưa rõ ràng, đặc biệt khi hai lớp có đặc điểm ngoại hình tương tự nhau
Dữ kiện cần kiểm tra:
- Confusion Matrix: hai class có thường xuyên nhầm lẫn với nhau không.
- Ảnh annotation: cùng một đối tượng nhưng được gán class khác nhau.
- Quy tắc phân loại trong guideline: có tiêu chí phân biệt rõ ràng hay không.
Không nên kết luận guideline sai nếu chưa có các dữ kiện trên.
4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì?
ko có 10 ảnh để train vì gây data leak khiến model học thuộc

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
| | | | |

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.
