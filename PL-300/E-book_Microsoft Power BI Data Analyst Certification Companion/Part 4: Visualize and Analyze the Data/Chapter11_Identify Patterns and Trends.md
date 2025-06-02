# 1. Ngăn Phân tích (The Analytics Pane)
- Ngăn Phân tích cung cấp các tùy chọn phân tích bổ sung cho một số loại trực quan hóa nhất định trong Power BI.
- "Một số loại trực quan hóa này có một tính năng bổ sung: Analytics."
- Tính năng này được hiển thị đầy đủ nhất trong trực quan hóa dạng đường (line visualization).
- Các tính năng phổ biến bao gồm:
  + **Đường Xu hướng (Trend line):** Giúp hình dung xu hướng chung của dữ liệu theo thời gian hoặc qua các điểm dữ liệu khác.
  + **Đường Trung bình (Average line):** Hiển thị giá trị trung bình của dữ liệu, hữu ích trong việc xác định các điểm bất thường (outliers).
  + **Dự báo (Forecasting):** Nếu loại dữ liệu hỗ trợ, ngăn Phân tích sẽ hiển thị tùy chọn Dự báo. Việc hiểu các thành phần để tạo đường dự báo là quan trọng cho kỳ thi PL-300.

# 2. Sử dụng Tính năng Phân tích (Using the Analyze Feature)
- Tính năng "Analyze" cho phép người dùng tìm hiểu lý do đằng sau những biến động đáng kể (tăng hoặc giảm đột ngột) trong dữ liệu.
- "Khi nhìn vào dữ liệu, có thể có những sự tăng hoặc giảm đáng kể. Power BI có tính năng Analyze có thể được kích hoạt để giải thích sự thay đổi này."
- Khi được kích hoạt (bằng cách click chuột phải vào một điểm dữ liệu và chọn Analyze ➤ Explain the increase (or decrease)), tính năng này xử lý toàn bộ mô hình dữ liệu, tìm kiếm mối quan hệ giữa các điểm dữ liệu khác nhau.
- Nó có thể đưa ra những thông tin chi tiết hữu ích. Nếu người dùng thấy hữu ích, trực quan hóa được tạo ra bởi tính năng Analyze có thể được thêm vào trang báo cáo.

# 3. Nhận diện Điểm bất thường (Identifying Outliers)
- Việc tìm kiếm các điểm dữ liệu không phù hợp với mô hình chung là quan trọng vì chúng có thể tiết lộ thông tin chi tiết.
- "Khi phân tích dữ liệu, chúng ta thường muốn tìm các điểm dữ liệu không phù hợp với mô hình chủ đạo bởi vì dữ liệu đó có thể tiết lộ thông tin chi tiết về phần còn lại của dữ liệu."
- Trực quan hóa dạng biểu đồ phân tán (scatter plot) là một công cụ rất hữu ích để khám phá các điểm bất thường.
- Việc thêm các đường trung bình (average), trung vị (median) hoặc xu hướng (trend lines) từ ngăn Phân tích vào biểu đồ phân tán giúp làm rõ các mô hình và cụm dữ liệu.

# 4. Trục Phân loại so với Trục Liên tục (Categorical vs. Continuous Axes)
- Dữ liệu được chia thành hai loại chính: phân loại (categorical) và liên tục (continuous).
- Dữ liệu phân loại: Có các điểm rời rạc (ví dụ: danh mục sản phẩm, trình độ học vấn). "Dữ liệu phân loại là dữ liệu có các điểm rời rạc." Loại dữ liệu này thường được hiển thị tốt nhất bằng biểu đồ cột hoặc thanh.
- Dữ liệu liên tục: Không dễ dàng chia thành nhóm (ví dụ: thời gian). "Dữ liệu liên tục là dữ liệu không dễ dàng chia thành nhóm. Thời gian là ví dụ kinh điển về dữ liệu liên tục..."
- Thời gian thường được hiển thị trên trục liên tục một cách tự nhiên.
- Tuy nhiên, Power BI cho phép thay đổi loại trục (Categorical hoặc Continuous) thông qua tùy chọn Format visual ➤ X-axis.
- Thay đổi trục sang Categorical có thể cho phép sắp xếp dữ liệu trên trục X dựa trên các trường khác trong trực quan hóa, điều này không thể làm được với trục liên tục.

# 5. Nhóm, Phân nhóm (Bins), và Phân cụm (Clustering)
- Power BI cung cấp nhiều công cụ để tổ chức dữ liệu có nhiều giá trị thành các nhóm lớn hơn.
- Tạo Nhóm (Creating Groups):Có thể tạo nhóm bằng cách chọn các điểm dữ liệu cụ thể trong trực quan hóa (ví dụ: biểu đồ cột/thanh), giữ phím Shift và click chuột phải.
- Nhóm đã tạo sẽ xuất hiện trong Ngăn Trường (Fields pane) trong cùng bảng với trường gốc.
- Nhóm có thể dễ dàng chỉnh sửa (thêm/xóa thành viên, đổi tên) từ Ngăn Trường.
- Việc đổi tên nhóm giúp tăng tính rõ ràng của trực quan hóa và chú thích.
