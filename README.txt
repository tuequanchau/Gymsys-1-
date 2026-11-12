GYMSYS – BẢN TÍCH HỢP MÔ HÌNH TÍNH TOÁN

CÁC FILE
- index.html: dashboard chính (mở file này bằng Live Server hoặc GitHub Pages).
- gymsys_customer_retention.html: dashboard giữ chân hội viên.
- gymsys_customer_data.html: xem dữ liệu đầu vào.
- gymsys_data.json: dữ liệu tổng hợp và các bảng dữ liệu.
- gymsys_checkins.json: dữ liệu check-in chi tiết.

MÔ HÌNH ĐÃ TÍCH HỢP
1. Logistic Regression: tính P(churn) bằng sigmoid từ các biến đặc trưng check-in, mức giảm tần suất, số ngày đến hạn, đánh giá và khiếu nại. Hệ số beta hiện là bộ hệ số khởi tạo cho bản demo, chưa được fit từ nhãn churn thực tế. Khi có nhãn gia hạn đủ tin cậy, cần huấn luyện và đánh giá lại hệ số.
2. CLV: lợi nhuận đóng góp tháng m được ước tính từ doanh thu gói thẻ bình quân tháng nhân biên lợi nhuận giả định 60%. S(t)=(1-P)^t; tỷ lệ chiết khấu tháng d=0,5%; chân trời dự báo T=12 tháng. Gói PT không đưa vào dòng doanh thu định kỳ để tránh coi doanh thu PT một lần là doanh thu thuê bao hàng tháng.
3. Chuẩn hóa CLV: min-max trên tập 900 hội viên trong snapshot hiện tại.
4. Điểm ưu tiên: C=0,4P+0,6F2. Ngưỡng phân nhóm: cao >=0,50; trung bình >=0,30; thấp <0,30.

LƯU Ý PHƯƠNG PHÁP
- Dữ liệu đầu vào là dữ liệu mô phỏng. Kết quả là đầu ra tính toán của bộ tham số demo, không phải kết quả mô hình đã được kiểm định trên dữ liệu vận hành thực tế.
- Biên lợi nhuận 60%, d=0,5%/tháng, T=12 và các hệ số beta là giả định khởi tạo để trình diễn luồng tính toán; cần thay bằng dữ liệu và kết quả hiệu chỉnh thực tế.
- CLV min-max phụ thuộc tập hội viên đang được phân tích; khi thêm/bớt hội viên, F2 và điểm ưu tiên có thể thay đổi.

CÁCH CHẠY
- Giữ nguyên tất cả file trong cùng thư mục.
- Mở thư mục bằng VS Code, cài Live Server và mở index.html.
- Không mở trực tiếp bằng file:// vì website dùng fetch để đọc JSON.
- Khi deploy GitHub Pages, upload toàn bộ file và giữ nguyên tên/cấu trúc.
