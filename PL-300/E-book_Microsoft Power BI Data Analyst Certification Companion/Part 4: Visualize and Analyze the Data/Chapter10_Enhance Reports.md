# Mục lục

1. [Chỉ định thứ tự sắp xếp (Specifying a Sort Order)](#1-chỉ-định-thứ-tự-sắp-xếp-specifying-a-sort-order)
2. [Điều khiển mở rộng và truy sâu (Expand Down and Drill Down Controls)](#2-điều-khiển-mở-rộng-và-truy-sâu-expand-down-and-drill-down-controls)
3. [Tương tác giữa các hình ảnh trực quan (Interactions Between Visuals)](#3-tương-tác-giữa-các-hình-ảnh-trực-quan-interactions-between-visuals)
4. [Đánh dấu (Bookmarks)](#4-đánh-dấu-bookmarks)
5. [Chú giải công cụ (Tooltips)](#5-chú-giải-công-cụ-tooltips)
6. [Trang chú giải công cụ (Tooltip Pages)](#6-trang-chú-giải-công-cụ-tooltip-pages)
7. [Thiết kế cho thiết bị di động (Designing for Mobility)](#7-thiết-kế-cho-thiết-bị-di-động-designing-for-mobility)


# 1. Chỉ định thứ tự sắp xếp (Specifying a Sort Order)
- Đôi khi, các cột cần được sắp xếp khác với hành vi sắp xếp mặc định (ví dụ: sắp xếp tháng hoặc ngày trong tuần theo số, không phải theo tên).
- Có thể tạo một cột tính toán chứa thứ tự sắp xếp và sau đó đặt cột liên quan để sắp xếp theo cột thứ tự sắp xếp mới.

# 2. Điều khiển mở rộng và truy sâu (Expand Down and Drill Down Controls)
- Các điều khiển này (biểu tượng "trident" và mũi tên kép) xuất hiện khi dữ liệu được sắp xếp theo thứ bậc (hierarchical arrangement).
- Các điều khiển này chỉ hiển thị nếu có nhiều trường trong cùng một "field well".
- Có thể sử dụng một cấu trúc thứ bậc được thiết lập trong mô hình dữ liệu (đã đề cập trong Chương 6) để kích hoạt các điều khiển này.

# 3. Tương tác giữa các hình ảnh trực quan (Interactions Between Visuals)
- Theo mặc định, các hình ảnh trực quan trên một trang báo cáo tương tác với nhau.
- Tương tác mặc định là Highlight (Làm nổi bật): các phần tử dữ liệu không liên quan sẽ bị làm mờ để làm nổi bật các giá trị liên quan đến lựa chọn trên hình ảnh trực quan khác.
- Có ba chế độ tương tác:
  + Highlight (mặc định)
  + Filter (Lọc)
  + None (Không tương tác)
- Một số loại hình ảnh trực quan (ví dụ: bản đồ) không hỗ trợ làm nổi bật; chúng chỉ có thể được lọc hoặc không tương tác.
- Nhà phát triển báo cáo có thể kiểm soát các loại tương tác này trong Power BI Desktop hoặc trong Service.
- Để kiểm soát tương tác trong Desktop: Chọn hình ảnh trực quan nguồn, đi tới Format > Edit interactions.

# 4. Đánh dấu (Bookmarks)
- Đánh dấu là một "chế độ xem đã lưu" của một trang. Chúng giúp cung cấp các "phím tắt" để xem chi tiết hoặc tổ chức nhiều thông tin trên một trang.
- Mẹo: Nên tạo đánh dấu "Default View" trước và sau đó xây dựng các đánh dấu khác từ đó.
- Cách tạo: Mở ngăn Bookmarks (View > Bookmarks). Thiết lập chế độ xem trên trang (ví dụ: đặt bộ cắt - slicer - đến một lựa chọn cụ thể). Nhấp vào "Add" trong ngăn Bookmarks.
- Nên đổi tên đánh dấu thành tên rõ ràng.
- Nếu bạn thay đổi trang sau khi tạo đánh dấu, bạn cần Update (cập nhật) đánh dấu để phản ánh những thay đổi đó.
- Mẹo: Nên tạo đánh dấu "Default View" trước và sau đó xây dựng các đánh dấu khác từ đó.
- Nút điều hướng đánh dấu (Bookmark Navigator Button): Hiển thị tất cả các đánh dấu một cách trực quan cho người dùng báo cáo, tương tự như nút điều hướng trang (Hình 10-16). Nút này có nhiều tùy chọn định dạng.
- Chế độ xem đánh dấu (Viewing Your Bookmarks): Sử dụng tùy chọn "View" trong ngăn Bookmarks để trình bày báo cáo như một bản trình chiếu.
Mẹo: Trong Power BI Desktop, một số tính năng nút yêu cầu nhấn giữ phím Ctrl. Điều này không cần thiết sau khi báo cáo được xuất bản lên Service.

# 5. Chú giải công cụ (Tooltips)
- Chú giải công cụ xuất hiện khi di chuột qua một điểm dữ liệu trên hình ảnh trực quan.
- Theo mặc định, chú giải công cụ hiển thị các giá trị mặc định cho mỗi trường được sử dụng trong hình ảnh trực quan.
- Có thể nâng cao chú giải công cụ bằng cách thêm các trường hoặc thước đo bổ sung vào "Tooltips field well" cho hình ảnh trực quan.
- Cảnh báo: Thêm quá nhiều thước đo vào Tooltips field có thể ảnh hưởng tiêu cực đến hiệu suất báo cáo, ngay cả khi người dùng không di chuột qua điểm dữ liệu. Có thể đổi tên trường hoặc thước đo chỉ cho hình ảnh trực quan để chú giải công cụ dễ đọc hơn.

# 6. Trang chú giải công cụ (Tooltip Pages)
- Một trang chú giải công cụ là một trang báo cáo đầy đủ hiển thị trong chú giải công cụ.
- Các bước thiết lập:
  + Tạo một trang mới và ẩn trang đó.
  + Trong Format page > Page information, đặt trang là "Tooltip page". Bước này là bắt buộc.
  + (Tùy chọn) Điều chỉnh kích thước canvas cho chú giải công cụ dưới Canvas settings > Custom (Hình 10-36).
  + Thêm các hình ảnh trực quan vào trang chú giải công cụ (Hình 10-37). Nên thêm ít phần tử trực quan để đảm bảo hiệu suất và hiển thị.
  + Điều hướng trở lại trang và hình ảnh trực quan nơi bạn muốn hiển thị trang chú giải công cụ.
- Ưu điểm hiệu suất: Các thước đo trên trang chú giải công cụ chỉ được tính toán khi người dùng di chuột qua điểm dữ liệu, giúp cải thiện hiệu suất so với chú giải công cụ mặc định.

# 7. Thiết kế cho thiết bị di động (Designing for Mobility)
- Power BI cho phép thiết kế bố cục báo cáo riêng cho thiết bị di động (điện thoại, máy tính bảng).
- Truy cập bố cục di động bằng cách đi tới View > Mobile layout.
- Trong bố cục di động, kéo và thả các hình ảnh trực quan hiện có lên canvas di động và sắp xếp chúng. Lưới giúp căn chỉnh các phần tử.
- Chế độ xem di động tự động điều chỉnh cho các kích thước thiết bị khác nhau; bạn không cần tạo bố cục riêng cho từng kích thước.
