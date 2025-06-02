# MỤC LỤC
1. [Vai trò của DAX trong Mô hình Dữ liệu](#1-vai-trò-của-dax-trong-mô-hình-dữ-liệu)
2. [Bảng tính toán (Calculated Tables)](#2-bảng-tính-toán-calculated-tables)
3. [Cột tính toán (Calculated Columns)](#3-cột-tính-toán-calculated-columns)
4. [Tinh chỉnh Mô hình (Refining Your Model)](#4-tinh-chỉnh-mô-hình-refining-your-model)
5. [Thiết lập Chức năng Q&A](#5-thiết-lập-chức-năng-qa)
6. [Bảo mật (Security)](#6-bảo-mật-security)

# 1. Vai trò của DAX trong Mô hình Dữ liệu
- DAX là ngôn ngữ được sử dụng để thực hiện bốn loại nội dung trong Power BI Desktop: Bảng tính toán (Calculated tables), Cột tính toán (Calculated columns), Biện pháp đo lường (Measures) và Vai trò bảo mật (Security roles).
- Nguồn tài liệu khuyến cáo thêm dữ liệu "càng sớm càng tốt" (upstream) ở nguồn dữ liệu gốc hoặc Power Query Editor.

# 2. Bảng tính toán (Calculated Tables)
- Có thể tạo bảng tính toán bằng cách sao chép bảng hiện có với cú pháp DAX đơn giản (ví dụ: NewTableName='Existing Table Name') hoặc sử dụng các biểu thức phức tạp hơn.
- Hai điểm cần lưu ý cho kỳ thi PL-300:
  + Việc tạo bảng tính toán có thể ảnh hưởng đáng kể đến hiệu suất báo cáo vì nó không được nén hiệu quả bởi công cụ VertiPaq.
  + Bảng tính toán (và cột tính toán) được khởi tạo khi báo cáo mở. Giá trị của chúng sẽ không được tính toán lại trừ khi mô hình được khởi tạo lại.
- Nguồn tài liệu khuyên nên tránh tạo bảng tính toán nếu có thể.

# 3. Cột tính toán (Calculated Columns)
- Cột tính toán hữu ích khi cần thực hiện tính toán không có sẵn trong dữ liệu hiện có, đặc biệt cho các phép tính hàng theo hàng (row-by-row).
- Tuy nhiên, chúng cũng ảnh hưởng đến hiệu suất và có tính chất tĩnh (không được tính toán lại tự động).
- Nên tạo cột tính toán trong Power Query Editor hoặc tốt hơn nữa là ở nguồn dữ liệu nếu có thể.
- Sử dụng cột tính toán trong hai trường hợp cụ thể:
  + Khi muốn sử dụng giá trị kết quả trong cột đó làm bộ lọc hoặc lát cắt (slicer).
  + Khi phép tính phải được thực hiện hàng theo hàng để đảm bảo độ chính xác.
- Cột tính toán thực hiện một phép tính cụ thể hàng theo hàng, hành vi này được gọi là "lặp" (iterating).

# 4. Tinh chỉnh Mô hình (Refining Your Model)
- **Phân cấp (Hierarchies):** Tổ chức các trường liên quan theo cấu trúc phân cấp (ví dụ: Ngày: Năm, Quý, Tháng; Sản phẩm: Danh mục, Danh mục phụ, Sản phẩm). Điều này giúp người dùng hiểu mối quan hệ giữa các trường, dễ dàng thêm các trường liên quan vào trực quan hóa cùng lúc và tạo ra "đường dẫn" rõ ràng để phân tích chi tiết (drilling down). Phân cấp có thể được tạo trong cả chế độ Báo cáo (Report view) và Mô hình (Model view).
- **Ẩn trường (Hiding Fields):** Nên ẩn các trường trong bảng dữ kiện (fact table) mà có trường tương ứng trong bảng chiều (dimension table) để giảm nhầm lẫn cho người dùng báo cáo.
- **Tổng kết (Summarization):** Là phép tính mặc định (SUM, AVERAGE, COUNT, v.v.) được áp dụng cho một cột khi nó được sử dụng trong trực quan hóa. Sự hiện diện của biểu tượng sigma (Σ) bên cạnh trường cho biết có hành vi tổng kết mặc định. Có thể thay đổi hoặc xóa hành vi này trong các chế độ xem khác nhau của Power BI Desktop.
- **Phân loại (Categorization):** Giúp Power BI hiểu loại dữ liệu trong một trường, cho phép sử dụng thêm các chức năng đặc biệt. Phân loại địa lý (Thành phố, Quận, Quốc gia, v.v.) đặc biệt quan trọng để hiển thị chính xác trên bản đồ và loại bỏ sự mơ hồ (ví dụ: CA có thể là California hoặc Canada). Phân loại URL (Image URL, Web URL) cho phép Power BI hiển thị hình ảnh hoặc trang web thay vì chỉ hiển thị văn bản URL.

# 5. Thiết lập Chức năng Q&A
- Chức năng Q&A cho phép người dùng đặt câu hỏi về dữ liệu bằng ngôn ngữ tự nhiên.
- Chuẩn bị mô hình tốt là chìa khóa để tối ưu hóa Q&A. Các bước chuẩn bị trong Desktop bao gồm:
  + Đặt loại dữ liệu phù hợp (ví dụ: Date cho các cột ngày).
  + Chuẩn hóa các bảng (chia nhỏ thông tin phức tạp thành các cột riêng biệt).
  + Phân loại dữ liệu (đặc biệt là dữ liệu địa lý).

- Các bước nâng cao trong thiết lập Q&A bao gồm:
  + Thiết lập từ đồng nghĩa cho các thuật ngữ chính.
  + "Gợi ý" một số câu hỏi được đề xuất (seed with suggested questions).
  + Xem lại các câu hỏi đã được hỏi và sửa lỗi khi cần thiết.

# 6. Bảo mật (Security)
- Bảo mật trong Power BI có nhiều lớp.
- Thông tin xác thực truy cập (Access Credentials): Được sử dụng khi kết nối với nguồn dữ liệu và kiểm soát những gì bạn (người tạo mô hình) có thể truy cập, không phải những gì người xem báo cáo có thể thấy.
- Bảo mật cấp hàng (Row-Level Security - RLS): Kiểm soát các hàng dữ liệu mà người xem báo cáo có thể thấy.
- Có thể kiểm tra vai trò đã thiết lập bằng chức năng "View as".
- Bảo mật cấp đối tượng (Object-Level Security - OLS): (Không được đề cập trong kỳ thi PL-300 nhưng được giới thiệu để tham khảo trong tương lai). OLS kiểm soát quyền truy cập vào toàn bộ đối tượng hoặc thực thể (ví dụ: bảng, trường) sao cho chúng không hiển thị hoặc không thể sử dụng bởi người xem báo cáo. OLS phải được triển khai bằng các công cụ bên ngoài như Tabular Editor.
