# MỤC LỤC

1. [Mô hình Dữ liệu là gì và tại sao cần thiết?](#1-mô-hình-dữ-liệu-là-gì-và-tại-sao-cần-thiết)
2. [Định nghĩa các Bảng](#2-định-nghĩa-các-bảng)
3. [Dim và Fact Tables (Bảng Chiều và Bảng Sự kiện)](#3-dim-và-fact-tables-bảng-chiều-và-bảng-sự-kiện)
4. [Sử dụng Trường trong Trực quan hóa (Visuals)](#4-sử-dụng-trường-trong-trực-quan-hóa-visuals)
5. [Relationships (Mối Quan Hệ): Mô tả Kết nối của Mô hình](#5-relationships-mối-quan-hệ-mô-tả-kết-nối-của-mô-hình)
6. [Star Schema (Lược đồ Hình sao)](#6-star-schema-lược-đồ-hình-sao)
7. [Hướng của Mối Quan Hệ (Relationships and Directions)](#7-hướng-của-mối-quan-hệ-relationships-and-directions)
8. [Cardinality (Tính Đa Dạng)](#8-cardinality-tính-đa-dạng)
9. [Thêm Bảng Ngày (Date Table)](#9-thêm-bảng-ngày-date-table)

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

# 6. Star Schema (Lược đồ Hình sao)
- Là "hình dạng" lý tưởng của mô hình dữ liệu.
- Bảng sự kiện (thường chỉ một) nằm ở trung tâm ảo.
- Các bảng chiều được sắp xếp xung quanh bảng sự kiện, mỗi bảng chiều kết nối với bảng sự kiện thông qua một mối quan hệ.
- Không bắt buộc, nhưng là mục tiêu hướng tới.
- Biến thể phổ biến là "snowflake" schema (lược đồ hình bông tuyết), trong đó các bảng chiều được "chuẩn hóa" thêm. Power BI hướng tới sự cân bằng, không chuẩn hóa quá mức như Third Normal Form phổ biến trong mô hình dữ liệu chung.

# 7. Hướng của Mối Quan Hệ (Relationships and Directions)
Mối quan hệ có hướng, dùng để truyền bộ lọc từ bảng này sang bảng khác.
- Mối quan hệ Một Chiều (Single-Direction):
  + Mặc định cho mối quan hệ 1-nhiều, bộ lọc chảy từ bên "một" (dim) sang bên "nhiều" (fact).
  + Cho phép lựa chọn rõ ràng trong bảng chiều (chỉ có một hàng cho mỗi yếu tố), sau đó bộ lọc được truyền sang bảng sự kiện.
- Mối quan hệ Hai Chiều (Bidirectional):
  + Bộ lọc có thể được truyền từ cả hai bảng trong mối quan hệ.
  + Nên tránh nếu có thể, vì có thể gây mơ hồ (hoặc tệ hơn là lỗi) trong báo cáo và làm chậm đáng kể.
  + Xảy ra trong mối quan hệ 1-1 (thường không gây nhiều vấn đề) và mối quan hệ nhiều-nhiều (kịch bản không mong muốn).

# 8. Cardinality (Tính Đa Dạng)
Cardinality của một cột được định nghĩa bởi số lượng giá trị duy nhất (không lặp lại) mà nó có.
Cột "key" có cardinality cao. Cột có giá trị lặp lại có cardinality thấp.
Một trong những nhiệm vụ chính của nhà mô hình dữ liệu là giảm hoặc loại bỏ cardinality cao ở bất cứ đâu có thể, vì cột có cardinality cao "đắt tiền" để lưu trữ (động cơ VertiPaq khó nén hơn).
Nơi tốt nhất để giảm cardinality là trong Power Query Editor:
Đối với các cột có cardinality cao không thể đơn giản hóa (ví dụ: cột key), hãy cố gắng lưu trữ dưới dạng số nguyên (integer), tốt nhất là số nguyên (whole number), vì chúng dễ nén hơn.
Việc chọn kiểu dữ liệu (data type) tốt nhất nên thực hiện trong Power Query Editor, nhưng có thể thay đổi trong Power BI Desktop.

# 9. Thêm Bảng Ngày (Date Table)
- Hầu hết các mô hình dữ liệu đều có các trường ngày tháng. Sử dụng trực tiếp các trường ngày từ bảng sự kiện có vấn đề:
  + Thiếu ngày trong khoảng thời gian (cuối tuần, ngày lễ).
  + Không tính toán chính xác khoảng thời gian (ví dụ: thời gian từ Order Date đến Ship Date).
  + Không hỗ trợ lịch cụ thể của công ty (năm tài chính).
  + Các hàm time intelligence tích hợp sẵn trong DAX sẽ không hoạt động như mong đợi.
- Giải pháp là thêm một bảng chiều riêng cho ngày (date dimension table hoặc date dim).
- **Có ba cách hiệu quả để tạo bảng ngày:**
  + Sử dụng bảng ngày có sẵn trong kho dữ liệu của công ty.
  + Tạo trong Power Query Editor sử dụng mã M (mất ít không gian hơn trong mô hình).
  + Sử dụng DAX để tạo trong Power BI Desktop.
- **Các bước cần thiết sau khi tạo bảng ngày:**
  + Thiết lập cột sắp xếp số cho tháng trong năm để đảm bảo sắp xếp đúng (ví dụ: 202101, 202102).
  + Đánh dấu bảng ngày (Mark your date table)
  + Kết nối bảng chiều ngày với bảng sự kiện thông qua mối quan hệ 1-nhiều.
- **Shadow Date Tables:** Nếu không có bảng ngày riêng, Power BI sẽ tạo các bảng ngày "ẩn" (shadow date tables) đằng sau mỗi trường ngày. Chúng không thể kiểm soát, làm phình to mô hình không cần thiết, và không hoạt động đáng tin cậy với các hàm time intelligence của DAX. Có thể loại bỏ chúng bằng cách tạo và đánh dấu bảng ngày của riêng bạn, hoặc ngăn chúng được tạo trong tùy chọn Power BI.
- Để sử dụng nhiều trường ngày (Order Date, Ship Date, Delivery Date) với cùng một bảng ngày, bạn cần tạo nhiều mối quan hệ inactive giữa bảng sự kiện và bảng ngày, và sử dụng hàm DAX UseRelationship khi cần (sẽ được đề cập sau).
- **Role-Playing Dimensions:** Một kỹ thuật thay thế cho mối quan hệ inactive là tạo bản sao của bảng ngày (một bản sao cho Order Date, một cho Ship Date, v.v.) và mỗi bản sao có mối quan hệ active với trường ngày tương ứng trong bảng sự kiện. Kỹ thuật này làm tăng kích thước mô hình, nên cần cân nhắc dựa trên độ phức tạp của mô hình tổng thể.
