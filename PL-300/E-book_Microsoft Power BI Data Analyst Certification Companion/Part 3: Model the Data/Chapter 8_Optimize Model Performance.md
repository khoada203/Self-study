- Mọi visual tạo ra truy vấn DAX: Một điểm cốt lõi được nhấn mạnh là ngay cả khi người dùng không viết một dòng DAX nào, mọi visual trong báo cáo Power BI vẫn tạo ra một truy vấn DAX. Điều này có nghĩa là hiểu và phân tích các truy vấn này là rất quan trọng để tối ưu hóa hiệu suất.
- Công cụ Performance Analyzer: Tài liệu giới thiệu Performance Analyzer là công cụ chính được tích hợp trong Power BI Desktop để đo lường và phân tích hiệu suất báo cáo. Công cụ này cho phép người dùng ghi lại và xem thời gian cần thiết để làm mới các visual và trang báo cáo.
- Kiểm tra hiệu suất truy vấn DAX: Performance Analyzer cho phép người dùng xem và sao chép truy vấn DAX được tạo ra bởi mỗi visual. Việc phân tích các truy vấn này giúp xác định các yếu tố gây chậm trễ. Mặc dù không thể sửa đổi truy vấn DAX cơ bản của visual, người dùng có thể tối ưu hóa các measures hoặc calculated columns được sử dụng trong visual đó.
- Số lượng visual trên mỗi trang: Mặc dù không có giới hạn cố định, tài liệu khuyến nghị nên đặt mục tiêu từ năm đến bảy visual trên mỗi trang báo cáo. Tuy nhiên, hiệu suất tổng thể phụ thuộc vào tác động tích lũy của tất cả các yếu tố trên trang.
- Các yếu tố hiệu suất khác và cách khắc phục: Tài liệu liệt kê một loạt các yếu tố khác có thể ảnh hưởng đến hiệu suất báo cáo và đề xuất các biện pháp khắc phục cụ thể:
  + Cột không cần thiết (chưa sử dụng): Nên xóa bỏ trong Power Query Editor.
  + Các cột có cardinality cao: Xóa bỏ hoặc giảm cardinality (ví dụ: tách cột ngày và giờ).
  + Quan hệ nhiều-nhiều (many-to-many relationships): Xây dựng các bảng cầu nối (bridge tables).
  + Quan hệ hai chiều (bidirectional relationships): Sử dụng DAX để đảo ngược quan hệ (ví dụ: sử dụng CROSSFILTER).
  + Sử dụng DAX không tối ưu: Thử nghiệm các phiên bản khác nhau của một measure bằng cách sử dụng các hàm DAX nhanh hơn.
  + Calculated columns: Thay thế bằng measures hoặc thêm cột ở nguồn dữ liệu hoặc trong Power Query Editor.
  + Tổng hợp các bảng lớn: Tạo các bảng tổng hợp trong Power Query Editor hoặc ở nguồn dữ liệu.
  + Các lựa chọn bộ lọc và slicer: Đặt trước bộ lọc và slicer cho các mục được chọn phổ biến nhất và đóng khung bộ lọc.
  + Tooltip quá nhiều: Tránh sử dụng quá nhiều trường trong tooltip và tắt tooltip nếu không cần thiết.
  + Giảm tương tác: Tắt tương tác giữa các visual nếu chúng không cần tương tác với nhau.
