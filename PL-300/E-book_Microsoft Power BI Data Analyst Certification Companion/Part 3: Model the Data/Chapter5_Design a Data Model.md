# MỤC LỤC

# 1. Mô hình Dữ liệu là gì và tại sao cần thiết?
- Mô hình dữ liệu cho phép kết hợp logic các nhóm dữ liệu khác nhau (được sắp xếp trong các bảng) mà không cần kết hợp vật lý chúng.
- Mô hình là cấu trúc để định nghĩa các kết nối (mối quan hệ) giữa các bảng.
- Thiết kế mô hình dữ liệu là kỹ năng quan trọng nhất trong Power BI, ảnh hưởng lớn đến hiệu suất của báo cáo.
# 2. Định nghĩa các Bảng
- Dữ liệu được trích xuất (dưới dạng query trong Power Query Editor) sau khi áp dụng các chuyển đổi sẽ trở thành các bảng trong Power BI Desktop.
- Mô hình dữ liệu thường bao gồm nhiều bảng từ các nguồn khác nhau.

# 3. Dim và Fact Tables (Bảng Chiều và Bảng Sự kiện)
Có hai loại bảng chính trong mô hình dữ liệu: bảng sự kiện (fact table) và (thường) nhiều bảng chiều (dimension - dim table).

| **Fact Table (Bảng Sự kiện)**                                                                                 | **Dimension Table (Bảng Chiều)**                                                                                       |
|---------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| - Chứa dữ liệu bạn đang báo cáo (ví dụ: giao dịch bán hàng, cuộc hẹn y tế, dữ liệu sản xuất).                  | - Mô tả chi tiết hơn các yếu tố của bảng sự kiện.                                                                       |
| - Thường ghi lại những sự việc đã xảy ra, hầu như luôn có dấu ngày (và có thể cả thời gian).                   | - Thường có nhiều cột (rất rộng), nhiều cột là "strings" hoặc alphanumeric.                                             |
| - Lý tưởng nhất chỉ chứa các giá trị ở định dạng số (số lượng, ngày, giờ, giá cả, ID duy nhất cho khách hàng...).| - ID trong bảng chiều là khóa chính (primary key).                                                                     |
| - Chứa các ID là khóa ngoại (foreign key) cho phép kết nối với bảng chiều tương ứng.                           | - Chứa thông tin chi tiết về ID đó (ví dụ: tên khách hàng, địa chỉ, ngày sinh, thông tin nhân khẩu học).                |
| - Thường là bảng dài nhất (nhiều hàng nhất) trong mô hình.                                                    | - Chỉ có một hàng cho mỗi yếu tố được mô tả (khách hàng, sản phẩm, cửa hàng, v.v.).                                     |
| - Có thể có nhiều hàng cho mỗi yếu tố như sản phẩm, khách hàng, hoặc cửa hàng.                                | - Mô hình thường có nhiều bảng chiều.                                                                                   |


- Lý tưởng nhất là các bảng chiều kết nối trực tiếp với bảng sự kiện, nhưng chúng cũng có thể liên quan đến các bảng chiều khác.

