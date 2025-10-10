# Phân Tích Tỷ Lệ Rời Bỏ & Xây Dựng Chiến Lược Giữ Chân Khách Hàng Ngân Hàng

## 1. Tổng quan dự án
Dự án này thực hiện phân tích bộ dữ liệu về khách hàng của một ngân hàng để tìm ra các yếu tố chính ảnh hưởng đến quyết định rời bỏ của họ. Từ những phân tích đó, dự án xây dựng một mô hình học máy để dự đoán khả năng rời bỏ của khách hàng trong tương lai, đồng thời đề xuất các chiến lược kinh doanh cụ thể và khả thi nhằm cải thiện tỷ lệ giữ chân khách hàng.
## 2. Bối cảnh  
NeoBank Europe là một ngân hàng số có trụ sở tại Luxembourg, ra đời với tham vọng chinh phục thị trường châu Âu.  
Trong chiến lược ra mắt, NeoBank đã quyết định tập trung vào ba thị trường kinh tế lớn và năng động nhất khu vực đồng Euro: Pháp, Tây Ban Nha và Đức. Họ tung ra một chiến dịch marketing đồng nhất trên cả ba quốc gia, kỳ vọng vào một mô hình kinh doanh có thể nhân rộng dễ dàng.  
Tuy nhiên, sau hai năm hoạt động, dù tổng số lượng người dùng vẫn tăng, báo cáo kinh doanh gần đây đã chỉ ra một xu hướng đáng lo ngại, phá vỡ kỳ vọng ban đầu của ban lãnh đạo: hiệu suất hoạt động giữa ba thị trường cốt lõi đang có xu hướng giảm, cụ thể là tỷ lệ khách hàng rời bỏ đang khá cao, gây ảnh hưởng lớn đến lợi nhuận chung.
## 3. Nguồn dữ liệu  
https://www.kaggle.com/datasets/radheshyamkollipara/bank-customer-churn/data   
Bộ dữ liệu được sử dụng trong dự án này là Bank Customer Churn Prediction, lấy từ nền tảng Kaggle. Dữ liệu bao gồm 10,000 bản ghi về khách hàng với các thông tin nhân khẩu học và tài chính như:
- CreditScore: Điểm tín dụng
- Geography: Quốc gia (Pháp, Tây Ban Nha, Đức)
- Gender: Giới tính
- Age: Tuổi
- Tenure: Thời gian gắn bó với ngân hàng (năm)
- Balance: Số dư tài khoản
- NumOfProducts: Số lượng sản phẩm ngân hàng đang sử dụng
- HasCrCard: Có sử dụng thẻ tín dụng hay không
- IsActiveMember: Có phải là thành viên hoạt động tích cực hay không
- EstimatedSalary: Lương ước tính
- Complain: khách hàng có khiếu nại hay không
- Satisfaction Score: Điểm đánh giá mức độ hài lòng của khách hàng (sau khi giải quyết khiếu nại)
- Card Type: Loại thẻ tín dụng mà khách hàng đang sở hữu (ví dụ: Gold, Silver, Platinum…).
- Exited: Biến mục tiêu - Khách hàng đã rời bỏ (1) hay chưa (0)
## 4. Công cụ và thư viện
- Ngôn ngữ lập trình: Python
- Môi trường: Google Colab
- Thư viện phân tích & xử lý dữ liệu:
  + Pandas: Đọc, ghi và xử lý dữ liệu dạng bảng.
  + NumPy: Hỗ trợ tính toán toán học và xử lý mảng.
- Thư viện trực quan hóa:
  + Matplotlib: Tạo các biểu đồ tĩnh, cơ bản.
  + Seaborn: Tạo các biểu đồ thống kê đẹp mắt và phức tạp hơn.
- Thư viện Machine Learning:
  + Scikit-learn: Xây dựng, huấn luyện và đánh giá mô hình học máy.
## 5. Quy trình thực hiện
Bước 1. Khám phá dữ liệu (EDA): Kiểm tra cấu trúc, thông tin, và các thống kê mô tả của dữ liệu.  
Bước 2. Làm sạch & Tiền xử lý: Xử lý các giá trị thiếu (nếu có), chuẩn hóa và mã hóa dữ liệu.  
Bước 3. Trực quan hóa & Phân tích chuyên sâu: Sử dụng biểu đồ để tìm ra các mối quan hệ và các yếu tố chính ảnh hưởng đến tỷ lệ churn.  
Bước 4. Xây dựng mô hình: Huấn luyện mô hình hồi quy logistic để dự đoán khả năng rời bỏ của khách hàng.  
Bước 5. Đánh giá mô hình: Đo lường hiệu suất của mô hình bằng các chỉ số như Accuracy, Precision, Recall, F1-score và Ma trận nhầm lẫn.  
Bước 6. Tổng kết & Đề xuất: Tóm tắt các insight quan trọng và đưa ra các chiến lược kinh doanh cụ thể.  
## 6. Các kết quả phân tích chính
- Tỷ lệ rời bỏ: Khoảng 20.4% khách hàng trong bộ dữ liệu đã rời bỏ, đây là một con số đáng kể.
- Nhân khẩu học:
  + Địa lý: Khách hàng tại Đức có tỷ lệ rời bỏ cao vượt trội (32.4%).
  + Giới tính: Tỷ lệ khách hàng nữ rời bỏ (25.1%) cao hơn đáng kể so với nam giới (16.5%).
  + Độ tuổi: Nhóm khách hàng trung niên (41-60 tuổi) có tỷ lệ rời bỏ cao nhất.
- Hành vi & Sản phẩm:
  + Thành viên không hoạt động: Nhóm khách hàng không hoạt động (IsActiveMember = 0) có tỷ lệ churn cao hơn nhiều.
  + Số lượng sản phẩm: Khách hàng sử dụng 3 hoặc 4 sản phẩm có tỷ lệ rời bỏ gần như tuyệt đối. Đây là một phát hiện bất thường và cần được điều tra sâu hơn.
  + Số dư: Khách hàng đã rời đi thường có số dư trung bình trong tài khoản cao hơn.
## 7. Kết quả mô hình dự đoán  
Mô hình hồi quy logistic được xây dựng để dự đoán khả năng churn.
- Độ chính xác (Accuracy): Mô hình đạt độ chính xác ~99.85% trên tập kiểm tra.
- Precision, Recall, F1-Score: Các chỉ số này đều đạt giá trị rất cao, gần như tuyệt đối (1.00).
## 8. Đề xuất chiến lược
1. Tập trung vào nhóm rủi ro cao:
- Khách hàng ở Đức: Triển khai các chiến dịch chăm sóc đặc biệt, khảo sát sự hài lòng để tìm hiểu nguyên nhân gốc rễ.
- Nhóm tuổi 41-60: Giới thiệu các sản phẩm tài chính phù hợp với giai đoạn cuộc đời (hưu trí, đầu tư) và tổ chức hội thảo về quản lý tài chính.
2. Cải thiện trải nghiệm và gắn kết:
- Khách hàng không hoạt động: Chạy các chiến dịch "kích hoạt lại" (re-engagement) với ưu đãi cá nhân hóa.
- Khách hàng dùng nhiều sản phẩm: Điều tra khẩn cấp lý do tỷ lệ churn gần 100% ở nhóm dùng 3-4 sản phẩm. Tạm ngưng bán chéo sản phẩm thứ 3, thứ 4 cho đến khi tìm ra nguyên nhân.
3. Xây dựng hệ thống cảnh báo sớm:
- Áp dụng mô hình dự đoán đã xây dựng để chấm điểm rủi ro churn cho toàn bộ khách hàng hàng tháng.
- Lập danh sách các khách hàng có điểm rủi ro cao nhất để đội ngũ chăm sóc khách hàng chủ động liên hệ, can thiệp trước khi họ quyết định rời đi.
4. Ưu tiên dựa trên giá trị vòng đời (CLTV):
- Trong số các khách hàng có nguy cơ rời bỏ, ưu tiên tập trung nguồn lực giữ chân những người có CLTV cao nhất (ví dụ: số dư lớn, thời gian gắn bó lâu).
