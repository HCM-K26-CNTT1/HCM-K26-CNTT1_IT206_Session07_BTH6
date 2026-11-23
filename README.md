# BÀI THỰC HÀNH 6
# XÂY DỰNG BÁO CÁO PHÂN TÍCH KẾT QUẢ HỌC TẬP TỪ NHIỀU TÀI LIỆU

## I. CÁC PROMPT SỬ DỤNG

### 1. Prompt đọc File 1 – Danh sách sinh viên

**Mục đích:** Trích xuất mã sinh viên và họ tên từ danh sách gốc.

**Prompt:**

Bạn là trợ lý đào tạo, hãy đọc tài liệu danh sách sinh viên được cung cấp và trích xuất thông tin thành bảng gồm hai cột: Mã sinh viên và Họ tên.

Yêu cầu:
- Giữ nguyên mã sinh viên và họ tên như trong tài liệu.
- Không tự ý sửa đổi hoặc viết lại tên.
- Không loại bỏ sinh viên có họ tên giống nhau.
- Sử dụng mã sinh viên làm thông tin định danh chính.
- Nếu thông tin không rõ ràng, đánh dấu cần kiểm tra.
- Không tự bổ sung dữ liệu không xuất hiện trong tài liệu.

### 2. Prompt đọc File 2 – Điểm chuyên cần và bài tập

**Mục đích:** Trích xuất điểm chuyên cần và điểm bài tập.

**Prompt:**

Hãy đọc tài liệu kết quả chuyên cần và bài tập của lớp Java cơ bản.

Trích xuất dữ liệu thành bảng gồm:
- Mã sinh viên.
- Điểm chuyên cần.
- Điểm bài tập.

Yêu cầu:
- Điểm phải nằm trong khoảng từ 0 đến 10.
- Giữ nguyên điểm số trong tài liệu.
- Kiểm tra các mã sinh viên xuất hiện nhiều lần.
- Nếu một sinh viên bị thiếu điểm, ghi rõ "Thiếu dữ liệu".
- Nếu có nhiều bản ghi khác nhau cho cùng một mã sinh viên, không tự chọn một kết quả mà phải đánh dấu để kiểm tra.
- Không suy đoán hoặc tự điền điểm còn thiếu.

### 3. Prompt đọc File 3 – Điểm giữa kỳ

**Mục đích:** Trích xuất kết quả kiểm tra giữa kỳ.

**Prompt:**

Hãy phân tích tài liệu điểm kiểm tra giữa kỳ của lớp Java cơ bản và chuyển dữ liệu thành bảng có cấu trúc gồm Mã sinh viên và Điểm giữa kỳ.

Yêu cầu:
- Giữ nguyên mã sinh viên.
- Đảm bảo điểm nằm trong thang 0–10.
- Phát hiện các mã sinh viên bị trùng.
- Đánh dấu những trường hợp không có điểm.
- Không ghép dữ liệu chỉ dựa trên họ tên.
- Không tự tạo hoặc điều chỉnh điểm số.

### 4. Prompt đọc File 4 – Điểm cuối kỳ và nhận xét

**Mục đích:** Trích xuất điểm thi cuối kỳ và nhận xét của giảng viên.

**Prompt:**

Hãy đọc tài liệu điểm thi cuối kỳ và nhận xét của giảng viên.

Trích xuất thành bảng gồm:
- Mã sinh viên.
- Điểm cuối kỳ.
- Nhận xét của giảng viên.

Yêu cầu:
- Giữ nguyên điểm số và nội dung nhận xét.
- Điểm cuối kỳ phải nằm trong khoảng 0–10.
- Phát hiện các bản ghi trùng lặp hoặc thông tin không thống nhất.
- Nếu thiếu điểm hoặc nhận xét, ghi rõ trạng thái tương ứng.
- Không tự suy diễn nguyên nhân sinh viên có điểm thấp.

### 5. Prompt đối chiếu dữ liệu giữa 4 file

**Mục đích:** Kết hợp dữ liệu từ các tài liệu và kiểm tra tính chính xác.

**Prompt:**

Bạn là trợ lý phân tích dữ liệu đào tạo. Hãy đối chiếu 4 bảng dữ liệu đã trích xuất từ 4 tài liệu của lớp Java cơ bản.

Thực hiện theo các yêu cầu sau:

1. Sử dụng mã sinh viên làm khóa định danh chính để kết hợp dữ liệu.
2. Không ghép dữ liệu chỉ dựa vào họ tên.
3. Tổng hợp các trường: Mã SV, Họ tên, Chuyên cần, Bài tập, Giữa kỳ, Cuối kỳ và Nhận xét.
4. Kiểm tra sinh viên bị thiếu điểm ở bất kỳ đầu điểm nào.
5. Phát hiện mã sinh viên xuất hiện nhiều lần hoặc có dữ liệu không thống nhất.
6. Kiểm tra các điểm số có nằm trong khoảng 0–10 hay không.
7. Không tự điền điểm bị thiếu và không tự lựa chọn giữa các bản ghi mâu thuẫn.
8. Giữ nguyên những trường hợp cần xác minh và lập danh sách riêng.

Hãy xuất kết quả thành bảng tổng hợp và bảng các trường hợp bất thường.

### 6. Prompt tính điểm và phân loại kết quả

**Prompt:**

Dựa trên bảng dữ liệu đã được đối chiếu, hãy tính điểm tổng kết theo công thức:

Điểm tổng kết = Chuyên cần × 10% + Bài tập × 20% + Giữa kỳ × 30% + Cuối kỳ × 40%.

Yêu cầu:
- Làm tròn điểm tổng kết đến một chữ số thập phân.
- Chỉ tính điểm khi có đầy đủ 4 đầu điểm hợp lệ.
- Nếu thiếu bất kỳ đầu điểm nào, ghi "Thiếu dữ liệu", không tự tính.
- Điểm tổng kết từ 5,0 trở lên được xếp loại Đạt.
- Điểm tổng kết dưới 5,0 được xếp loại Chưa đạt.
- Không đánh giá nguyên nhân dẫn đến kết quả học tập của từng sinh viên.

### 7. Prompt phân tích và lập báo cáo

**Prompt:**

Dựa trên bảng kết quả học tập đã tổng hợp, hãy lập báo cáo phân tích tình hình học tập của lớp Java cơ bản.

Báo cáo cần có:
- Tổng số sinh viên.
- Số sinh viên đủ dữ liệu và thiếu dữ liệu.
- Số lượng và tỷ lệ sinh viên đạt.
- Số lượng và tỷ lệ sinh viên chưa đạt.
- Những trường hợp có dữ liệu bất thường.
- Nhận xét về tình hình học tập chung.

Yêu cầu:
- Sử dụng số liệu thực tế từ bảng tổng hợp.
- Không tự suy đoán nguyên nhân điểm thấp.
- Phân biệt rõ sinh viên chưa đạt và sinh viên chưa đủ dữ liệu để đánh giá.
- Trình bày khách quan, rõ ràng, dễ hiểu.

## II. BẢNG KẾT QUẢ TỔNG HỢP 30 SINH VIÊN

*Dữ liệu minh họa phục vụ bài thực hành.*

| Mã SV | Họ tên | Chuyên cần | Bài tập | Giữa kỳ | Cuối kỳ | Tổng kết | Kết quả |
|---|---|---:|---:|---:|---:|---:|---|
| SV001 | Nguyễn Minh Anh | 9 | 8 | 7 | 8 | 7,9 | Đạt |
| SV002 | Trần Quốc Bảo | 8 | 7 | 6 | 7 | 6,9 | Đạt |
| SV003 | Lê Hoàng Nam | 7 | 6 | 5 | 5 | 5,3 | Đạt |
| SV004 | Phạm Thu Hà | 10 | 9 | 8 | 9 | 8,8 | Đạt |
| SV005 | Nguyễn Văn An | 8 | 8 | 7 | 6 | 7,0 | Đạt |
| SV006 | Trần Minh Đức | 6 | 5 | 4 | 4 | 4,3 | Chưa đạt |
| SV007 | Lê Thị Mai | 9 | 8 | Thiếu dữ liệu | 7 | Thiếu dữ liệu | Thiếu dữ liệu |
| SV008 | Phạm Quốc Huy | 7 | 7 | 6 | 6 | 6,3 | Đạt |
| SV009 | Nguyễn Thị Lan | 8 | 9 | 8 | 8 | 8,2 | Đạt |
| SV010 | Hoàng Gia Bảo | 6 | 6 | 5 | 4 | 4,5 | Chưa đạt |
| SV011 | Trần Thị Hương | 9 | 8 | 7 | 8 | 7,8 | Đạt |
| SV012 | Đỗ Minh Quân | 7 | 6 | 6 | 5 | 5,6 | Đạt |
| SV013 | Nguyễn Hoàng Phúc | 8 | 7 | 5 | 6 | 6,2 | Đạt |
| SV014 | Lê Quốc Thịnh | 9 | 8 | 7 | Thiếu dữ liệu | Thiếu dữ liệu | Thiếu dữ liệu |
| SV015 | Phạm Minh Tâm | 5 | 6 | 4 | 5 | 4,8 | Chưa đạt |
| SV016 | Nguyễn Ngọc Ánh | 10 | 9 | 9 | 9 | 9,2 | Đạt |
| SV017 | Trần Quốc Việt | 7 | 8 | 6 | 7 | 6,9 | Đạt |
| SV018 | Lê Minh Khang | 8 | 7 | 7 | 8 | 7,5 | Đạt |
| SV019 | Phạm Thu Trang | 6 | 5 | 5 | 6 | 5,5 | Đạt |
| SV020 | Nguyễn Đức Anh | 9 | 8 | 8 | 7 | 7,7 | Đạt |
| SV021 | Hoàng Minh Tuấn | 7 | 6 | 4 | 5 | 5,0 | Đạt |
| SV022 | Trần Ngọc Mai | Thiếu dữ liệu | 8 | 7 | 7 | Thiếu dữ liệu | Thiếu dữ liệu |
| SV023 | Đỗ Quốc Khánh | 8 | 7 | 6 | 5 | 6,0 | Đạt |
| SV024 | Nguyễn Thanh Bình | 6 | 7 | 5 | 4 | 4,7 | Chưa đạt |
| SV025 | Lê Hoàng Long | 9 | 9 | 8 | 9 | 8,8 | Đạt |
| SV026 | Phạm Ngọc Linh | 7 | 8 | 7 | 7 | 7,2 | Đạt |
| SV027 | Trần Minh Khôi | 5 | 5 | 3 | 4 | 3,9 | Chưa đạt |
| SV028 | Nguyễn Khánh Vy | 8 | 9 | 8 | 8 | 8,3 | Đạt |
| SV029 | Hoàng Anh Tuấn | 7 | 6 | 6 | 6 | 6,2 | Đạt |
| SV030 | Lê Thị Hạnh | 9 | 8 | 7 | 7 | 7,4 | Đạt |

## III. BÁO CÁO THỐNG KÊ KẾT QUẢ

### 1. Thống kê chung

| Nội dung | Số lượng | Tỷ lệ |
|---|---:|---:|
| Tổng số sinh viên | 30 | 100% |
| Đủ dữ liệu để tính điểm | 27 | 90% |
| Thiếu dữ liệu | 3 | 10% |
| Đạt học phần | 22 | 73,33% tổng lớp |
| Chưa đạt học phần | 5 | 16,67% tổng lớp |

### 2. Tỷ lệ đạt và chưa đạt

Tính trên 27 sinh viên có đủ dữ liệu:

- Tỷ lệ đạt: 22/27 × 100 = 81,48%.
- Tỷ lệ chưa đạt: 5/27 × 100 = 18,52%.

Như vậy, trong số sinh viên có đủ điểm để đánh giá, tỷ lệ đạt học phần là 81,48%, trong khi tỷ lệ chưa đạt là 18,52%.

Ba sinh viên thiếu dữ liệu được thống kê riêng, không đưa vào nhóm đạt hoặc chưa đạt.

## IV. DANH SÁCH CÁC TRƯỜNG HỢP BẤT THƯỜNG

### 1. Sinh viên thiếu dữ liệu

| Mã SV | Họ tên | Thông tin còn thiếu |
|---|---|---|
| SV007 | Lê Thị Mai | Điểm giữa kỳ |
| SV014 | Lê Quốc Thịnh | Điểm cuối kỳ |
| SV022 | Trần Ngọc Mai | Điểm chuyên cần |

Các trường hợp trên chưa đủ điều kiện tính điểm tổng kết. Cần kiểm tra lại tài liệu gốc hoặc xác nhận với giảng viên.

### 2. Dữ liệu trùng lặp

Trong quá trình đối chiếu, cần kiểm tra các trường hợp:
- Một mã sinh viên xuất hiện nhiều lần trong cùng một tài liệu.
- Một mã sinh viên có hai mức điểm khác nhau ở cùng một đầu điểm.
- Một bản ghi bị lặp lại nhưng không có sự khác biệt về nội dung.

Nguyên tắc xử lý: Không tự động cộng điểm, chọn điểm cao hơn hoặc loại bỏ bản ghi khi chưa xác minh được dữ liệu chính xác.

### 3. Trường hợp cần chú ý về kết quả

Các sinh viên có điểm tổng kết dưới 5,0:

| Mã SV | Họ tên | Tổng kết |
|---|---|---:|
| SV006 | Trần Minh Đức | 4,3 |
| SV010 | Hoàng Gia Bảo | 4,5 |
| SV015 | Phạm Minh Tâm | 4,8 |
| SV024 | Nguyễn Thanh Bình | 4,7 |
| SV027 | Trần Minh Khôi | 3,9 |

Đây là những trường hợp chưa đạt học phần theo quy định. Báo cáo chỉ ghi nhận kết quả điểm số, không kết luận nguyên nhân.

## V. BÁO CÁO NHẬN XÉT TÌNH HÌNH HỌC TẬP

Sau khi tổng hợp kết quả học tập của 30 sinh viên trong học phần Java cơ bản, có thể thấy phần lớn sinh viên đã hoàn thành học phần theo yêu cầu. Tuy nhiên, vẫn còn một số trường hợp chưa đạt và một số trường hợp chưa đủ dữ liệu để đánh giá chính xác.

Trước tiên, về tình hình dữ liệu, lớp có 30 sinh viên nhưng chỉ có 27 sinh viên đầy đủ điểm ở cả bốn đầu điểm. Ba sinh viên còn thiếu thông tin gồm SV007, SV014 và SV022. Những trường hợp này chưa thể tính điểm tổng kết vì thiếu ít nhất một thành phần trong công thức. Do đó, cần kiểm tra lại các tài liệu ban đầu hoặc liên hệ giảng viên để xác nhận trước khi đưa ra kết luận chính thức.

Đối với 27 sinh viên có đầy đủ điểm, có 22 sinh viên đạt học phần và 5 sinh viên chưa đạt. Tỷ lệ đạt là 81,48%, trong khi tỷ lệ chưa đạt là 18,52%. Đây là kết quả cho thấy đa số sinh viên đáp ứng được mức điểm tối thiểu 5,0 theo quy định của học phần.

Trong nhóm sinh viên đạt, một số trường hợp có kết quả khá tốt. Chẳng hạn, SV016 đạt 9,2 điểm và SV004, SV025 cùng đạt 8,8 điểm. Những kết quả này cho thấy các sinh viên trên có điểm tổng kết cao khi xét kết hợp cả bốn thành phần đánh giá. Bên cạnh đó, SV021 đạt đúng 5,0 điểm, vừa đủ điều kiện hoàn thành học phần.

Ngược lại, có 5 sinh viên chưa đạt, trong đó SV027 có điểm tổng kết thấp nhất là 3,9. Các trường hợp còn lại có điểm từ 4,3 đến 4,8. Đây là những sinh viên cần được lưu ý khi tổng hợp kết quả cuối cùng. Tuy nhiên, chỉ dựa trên bảng điểm thì chưa thể xác định nguyên nhân dẫn đến kết quả này. Muốn đánh giá cụ thể hơn cần có thêm thông tin về quá trình học tập hoặc trao đổi trực tiếp với giảng viên.

Từ kết quả trên, trung tâm nên kiểm tra và bổ sung dữ liệu còn thiếu trước khi chốt danh sách kết quả chính thức. Đồng thời, có thể rà soát lại những trường hợp chưa đạt để xác định nhu cầu hỗ trợ học tập phù hợp. Đối với các học phần tiếp theo, việc theo dõi điểm chuyên cần, bài tập và kiểm tra định kỳ cũng cần được thực hiện thường xuyên hơn.

Nhìn chung, kết quả học tập của lớp tương đối tích cực với tỷ lệ đạt trên 80% trong nhóm có đủ dữ liệu. Tuy nhiên, việc xử lý dữ liệu chính xác và xác minh các trường hợp bất thường vẫn rất quan trọng để đảm bảo báo cáo phản ánh đúng tình hình thực tế.
