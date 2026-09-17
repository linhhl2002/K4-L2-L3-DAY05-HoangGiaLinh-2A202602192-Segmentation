# Báo cáo Day 5 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên VLearn. Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202602192
- Ngày / CVAT local: 18/09/2026
- Công cụ đã dùng: CVAT, DINOv3

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh VLearn đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | easy_semantic.zip | 3/3 | 20 |
| medium_instance | medium_instance.zip | 3/3 | 32 |
| hard_panoptic | hard_panoptic.zip | 2/2 | 30 |
| cp1_holes | cp1_holes.zip | 1/1 | 3 |
| cp2_slice | cp2_slice.zip | 1/1 | 3 |
| cp5_occlusion | cp5_occlusion.zip | 1/1 | 3 |
| cp3_thin | cp3_thin.zip | 1/1 | 3 |
| cp4_curb | cp4_curb.zip | 1/1 | 3 |
| cp6_coverage | cp6_coverage.zip | 1/1 | 3 |
| **Tổng tối đa** | | | **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: Ảnh 000000181542.jpg, xe máy motorcycle ở giữa đến bên trái, xe bị che khuất bởi người phụ nữ đi bộ 
- Class và quy tắc tôi dùng để chọn biên: Class motorcycle - dùng brush vẽ tất cả các vùng hiển thị nhìn thấy của xe, vì xe bị che khuất, chia thành 3 phần nhỏ
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do:Vùng gợi ý đúng nhưng vật bị tách ra thành 3 object riêng
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng: Task hard_panoptic/ ảnh 000000460147.jpg/vùng building góc trên cùng bên phải
- Lỗi thuộc loại: gộp-tách
- Bằng chứng tôi nhìn thấy: Công cụ có nhận diện được building nhưng không tách các tòa nhà ra thành các object riêng
- Quy tắc và hành động sửa: Vẽ lại và chia thành các object nhỏ cho từng tòa nhà
- Sau sửa đã Save và export lại chưa: Đã save và export lại

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): Sau khi tự chạy script có tìm được lỗi ở task medium_instance, sau khi rà soát và sửa lại thì điểm tăng từ 13.4 lên 16
/ chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 1. Task medium_instance, Ảnh: 000000181542.jpg, trên tường tòa nhà bên trên, giữa có biển quảng cáo | Trên biển quảng cáo có hình ảnh người khá lớn, và rõ về hình dáng thì có phân vào person hay không? | Biển quảng cáo có hình ảnh người nhưng không phải là người thật, chỉ là hình ảnh. | Quyết định: Có phân vào person vì ảnh quảng cáo khá rõ ràng và chiếm 1 diện tích khá lớn, khi máy nhận diện sẽ khó để phân biệt giữa biển quảng cáo và người |
| 2 |Task medium_instance, 000000181542.jpg, Người ngồi trên xe bus | Toàn bộ vùng xe đã được phân vào class bus, trong khi có một người ngồi trên xe bus nên phân vào class person. Tuy nhiên người này ngồi trong xe nên không chắc có thuộc class person hay không. | Quyết định: Không phân vào class person vì người này ngồi trong xe và chỉ có một phần nhỏ cơ thể có thể nhìn thấy|
| 3 | 000000144300.jpg, xe motorcycle  | Xe có một phần chân chống đi kèm, nếu tô cả phần này sẽ bị dính kèm phần mặt đường lớn | Chân chống xe là 1 phần của xe, nhưng phần bánh xe nằm trên chân chống, ảnh hưởng lớn đến độ chính xác khi nhận diện xe | Quyết định: Không tô phần chân chống |
