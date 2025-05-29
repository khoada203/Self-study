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
| Chứa dữ liệu bạn đang báo cáo (ví dụ: giao dịch bán hàng, cuộc hẹn y tế, dữ liệu sản xuất).                  | Mô tả chi tiết hơn các yếu tố của bảng sự kiện.                                                                       |
| Thường ghi lại những sự việc đã xảy ra, hầu như luôn có dấu ngày (và có thể cả thời gian).                   |  Thường có nhiều cột (rất rộng), nhiều cột là "strings" hoặc alphanumeric.                                             |
|  Lý tưởng nhất chỉ chứa các giá trị ở định dạng số (số lượng, ngày, giờ, giá cả, ID duy nhất cho khách hàng...).|  ID trong bảng chiều là khóa chính (primary key).                                                                     |
|  Chứa các ID là khóa ngoại (foreign key) cho phép kết nối với bảng chiều tương ứng.                           |  Chứa thông tin chi tiết về ID đó (ví dụ: tên khách hàng, địa chỉ, ngày sinh, thông tin nhân khẩu học).                |
|  Thường là bảng dài nhất (nhiều hàng nhất) trong mô hình.                                                    |  Chỉ có một hàng cho mỗi yếu tố được mô tả (khách hàng, sản phẩm, cửa hàng, v.v.).                                     |
|  Có thể có nhiều hàng cho mỗi yếu tố như sản phẩm, khách hàng, hoặc cửa hàng.                                |  Mô hình thường có nhiều bảng chiều.                                                                                   |


- Lý tưởng nhất là các bảng chiều kết nối trực tiếp với bảng sự kiện, nhưng chúng cũng có thể liên quan đến các bảng chiều khác.

# 4. Sử dụng Trường trong Trực quan hóa (Visuals)
- Trường từ bảng chiều mang tính mô tả; chúng nên được sử dụng làm nhãn trên biểu đồ (ví dụ: hàng, cột, trục).
- Trường từ bảng sự kiện là các giá trị được phân tích trong trực quan hóa (ví dụ: được tổng hợp, tính trung bình, đếm).

# 5. Relationships (Mối Quan Hệ): Mô tả Kết nối của Mô hình
Mối quan hệ trong Power BI tương tự nhưng không giống với join trong database. Mục đích chính của mối quan hệ trong Power BI là để truyền bộ lọc.
- **One to many:**
  + Loại mối quan hệ phổ biến nhất, được sử dụng để kết nối bảng chiều (một hàng cho mỗi yếu tố) với bảng sự kiện (nhiều hàng cho mỗi yếu tố).
  + Các bảng Dimension có một hàng cho mỗi bản ghi... Các bảng Fact thường có nhiều hàng cho mỗi yếu tố được mô tả trong một bảng Dim cụ thể... Do đó, mối quan hệ được sử dụng để kết nối bảng Dim với bảng Fact là mối quan hệ một-nhiều.
  + Bên "một" được biểu thị bằng số 1 nhỏ, bên "nhiều" được biểu thị bằng dấu sao (*).
  + Cho phép bộ lọc truyền từ bên "một" (thường là bảng chiều) sang bên "nhiều" (bảng sự kiện).
  + Tip: Nếu bạn không chắc bảng nào là bảng sự kiện, hãy tìm bảng có nhiều hàng lặp lại ID khách hàng, sản phẩm, hoặc cửa hàng, và thường có ngày (và có thể cả thời gian) liên quan đến mỗi sự kiện.

- **Many to many:**
  + Xảy ra khi cả hai bảng trong mối quan hệ đều có nhiều hàng cho cùng một yếu tố (ví dụ: khách hàng).
  + Loại mối quan hệ này nên được tránh nếu có thể, vì nó có thể dẫn đến đếm trùng lặp hoặc thiếu bản ghi, làm báo cáo không chính xác và chậm.
  + Nếu bắt buộc phải sử dụng, bạn có thể giảm thiểu tác động tiêu cực bằng cách đặt hướng bộ lọc (filter direction).
  + Cách tốt nhất là thiết kế lại mô hình để đơn giản hóa bảng chiều, đảm bảo mỗi yếu tố có một bản ghi duy nhất, sau đó tạo mối quan hệ một-nhiều.

- One to one:
  + Được tạo giữa hai bảng khi có một hàng duy nhất trong cả hai bảng cho một yếu tố cụ thể.
  + Nếu Power BI gợi ý mối quan hệ một-một, đây là cơ hội để đơn giản hóa mô hình dữ liệu bằng cách kết hợp hai bảng trong Power Query Editor (thường là thao tác merge).
  + Không có nhược điểm đáng kể như mối quan hệ nhiều-nhiều, nhưng việc hợp nhất bảng giúp đơn giản hóa mô hình.

- **Bảng Không Kết Nối (Disconnected Tables):**
  + Bảng không có mối quan hệ với bất kỳ bảng nào khác trong mô hình.
  + Sử dụng trường từ bảng không kết nối trong visual với trường từ bảng khác thường dẫn đến giá trị lặp lại.
  + Có những trường hợp hữu ích cho bảng không kết nối, nhưng không nằm trong phạm vi của nguồn này.
  + Tip: Nếu thấy giá trị lặp lại trong visual, hãy kiểm tra mô hình của bạn trước tiên. Vấn đề nằm ở mối quan hệ bị thiếu hoặc có vấn đề với mối quan hệ hiện có.

- **Mối quan hệ Active và Inactive:**
  + Chỉ có thể có một mối quan hệ active giữa hai bảng, nhưng có thể có nhiều mối quan hệ inactive nếu cần.

