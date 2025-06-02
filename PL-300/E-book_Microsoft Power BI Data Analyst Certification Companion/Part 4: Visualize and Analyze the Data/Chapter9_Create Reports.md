# 1. Phân biệt Báo cáo và Bảng điều khiển
- Mặc dù người dùng thường dùng các thuật ngữ này thay thế cho nhau, trong Power BI, chúng là hai yếu tố riêng biệt.
- **Báo cáo:** Được tạo trong Power BI Desktop hoặc Power BI Service, có nhiều trang, phải dựa trên mô hình dữ liệu, có thể chia sẻ qua ứng dụng, và không thể chứa nội dung streaming.
- **Bảng điều khiển:** Chỉ được tạo trong Power BI Service, chỉ có một trang ảo, sử dụng hình ảnh từ các báo cáo đã xuất bản.

# 2. Canvas (Vùng làm việc)
- Khi mở Power BI Desktop, bạn sẽ thấy chế độ xem Báo cáo với canvas là vùng làm việc chính.
- Có nhiều tùy chọn định dạng cho báo cáo và trang trên canvas, bao gồm thông tin trang, cài đặt canvas (kích thước), nền canvas (trong vùng làm việc), và hình nền (trên toàn bộ khu vực báo cáo).

# 3. Tiêu chuẩn hóa Thiết kế và Giao diện
- Tài liệu cảnh báo về việc "lạc vào ma trận thiết kế" và khuyến khích tiêu chuẩn hóa màu sắc, phông chữ, kích thước trang và hình ảnh.
- Điểm khởi đầu tốt là sử dụng mẫu PowerPoint của công ty để đảm bảo tính nhất quán về mặt hình ảnh và "thương hiệu".
- Có thể xây dựng chủ đề bằng JSON và nhúng vào tệp PBIT (mẫu) để làm điểm khởi đầu cho các tệp PBIX mới.

# 4. Chủ đề Tích hợp và Tùy chỉnh
- Power BI Desktop cung cấp các chủ đề tích hợp sẵn (trong menu View) để bắt đầu.
- Chủ đề đã chọn sẽ quyết định bảng màu được sử dụng trong các hình ảnh trực quan.
- Có thể tùy chỉnh chủ đề ở mức độ chi tiết sau khi chọn.

# 5. Khả năng Tiếp cận (Accessibility)
- Tạo báo cáo dễ đọc cho mọi người là một ưu tiên quan trọng trong thiết kế báo cáo.
- Các kỹ thuật chính bao gồm: đảm bảo độ tương phản màu sắc đủ, sử dụng cỡ chữ tối thiểu 15 điểm, chọn phông chữ được ưu tiên về khả năng tiếp cận, cung cấp văn bản thay thế cho tất cả các hình ảnh trực quan, và kiểm thử báo cáo bằng trình đọc màn hình.
- Lý tưởng nhất là chủ đề Power BI của công ty tuân thủ tất cả các nguyên tắc thiết kế về khả năng tiếp cận.

# 6. Trực quan hóa (Visualizations)
- Hình ảnh trực quan là trung tâm của mỗi báo cáo, thể hiện kết quả của quá trình biến đổi và mô hình hóa dữ liệu.
- **Hình ảnh trực quan chuẩn:** Power BI cung cấp danh sách các loại hình ảnh trực quan chuẩn (37 loại tính đến thời điểm viết), có thể mở rộng định kỳ.
- Có thể chọn hình ảnh trực quan bằng cách nhấp vào biểu tượng hoặc kéo trường dữ liệu trực tiếp lên canvas.
- Mỗi hình ảnh trực quan có các "field wells" (vùng trường dữ liệu) duy nhất để đặt các trường.
- **Hình ảnh trực quan tùy chỉnh:** Nếu các hình ảnh trực quan chuẩn không đáp ứng yêu cầu, có một "thị trường" lớn các hình ảnh trực quan tùy chỉnh do nhà phát triển tạo ra, có thể truy cập qua menu dấu ba chấm.
- Nhiều công ty giới hạn quyền truy cập hình ảnh trực quan tùy chỉnh do lo ngại về bảo mật; tuy nhiên, có các hình ảnh trực quan được Microsoft chứng nhận.
- **Chọn loại hình ảnh trực quan phù hợp:** Loại dữ liệu nên quyết định loại hình ảnh trực quan được sử dụng (Ví dụ: so sánh - biểu đồ cột/thanh, thay đổi theo thời gian - biểu đồ đường/diện tích, v.v.).
- **Định dạng hình ảnh trực quan:** Mỗi loại hình ảnh trực quan có các tính năng định dạng chung và riêng, có thể truy cập qua menu Format visual.

# 7. Cấu hình Hình ảnh trực quan
- Mọi hình ảnh trực quan đều có các điều khiển chung trong tiêu đề trực quan: Chế độ tiêu điểm (Focus mode), Bộ lọc (Filter), và Dấu ba chấm (Ellipsis).
- Menu dấu ba chấm cung cấp các tùy chọn như Xuất dữ liệu (Export data), Hiển thị dưới dạng bảng (Show as a table), Xóa (Remove), Tiêu điểm (Spotlight), và Sắp xếp (Sort).

# 8. Cắt lát (Slicing) và Lọc (Filtering)
- Có nhiều cách để lọc hình ảnh trực quan, bao gồm sử dụng slicers và/hoặc Filters panel.
- Slicers: Là một dạng hình ảnh trực quan, dễ cài đặt và người dùng dễ hiểu. Có thể có nhiều slicers trên một trang hoặc điều khiển nhiều trang.
- Slicers có các tùy chọn cấu hình khác nhau dựa trên loại dữ liệu của trường được sử dụng (text, number, date).
- Một trong những cài đặt quan trọng nhất là Slicer settings, cho phép bật tùy chọn "Select all".
- Có thể sao chép slicers (Ctrl+C, Ctrl+V) và đồng bộ hóa chúng. Khi hai slicers được đồng bộ hóa, lựa chọn trên một slicer sẽ được phản ánh trên các slicers được đồng bộ, ngay cả khi trên các trang khác nhau.
- Panel Sync slicers (View ➤ Sync slicers) cho phép tinh chỉnh cài đặt đồng bộ hóa hoặc bắt đầu đồng bộ hóa mà không cần sao chép.
- Filters Pane: Là một tùy chọn khác để lọc, không chiếm không gian trên trang báo cáo như slicers.
- Lọc và Hiệu suất: Mỗi lựa chọn trên Filters pane tạo ra một truy vấn. Để cải thiện hiệu suất, có thể chọn trước dữ liệu quan tâm trên Filters pane và đóng nó trước khi xuất bản báo cáo.

# 9. Drill-Through
- Tính năng drill-through cho phép truyền bộ lọc từ một trang sang trang khác, cho phép điều hướng trực tiếp đến một trang đích từ một trang khác dựa trên một trường dữ liệu.
- Thiết lập bằng cách kéo trường đã chọn vào vùng Drill through của panel Visualizations trên trang đích.
- Sự xuất hiện của nút quay lại ở góc trên bên trái cho thấy thiết lập drill-through thành công.
- Để sử dụng, chọn một điểm dữ liệu trên hình ảnh trực quan sử dụng trường drill-through trên trang gốc, nhấp chuột phải và chọn Drill through.
- Bất kỳ bộ lọc nào khác trên trang gốc cũng sẽ được "mang theo" đến trang drill-through theo mặc định, trừ khi tùy chọn "Keep All Filters" được tắt.
- Tính năng này cũng cho phép drill-through từ báo cáo này sang báo cáo khác.

# 10. Định dạng có điều kiện (Conditional Formatting)
- Một số hình ảnh trực quan (đặc biệt là bảng và ma trận) có tính năng định dạng có điều kiện tích hợp sẵn, hoạt động tương tự Excel.
- Có thể truy cập menu Định dạng có điều kiện bằng cách nhấp vào mũi tên xuống bên cạnh trường muốn định dạng.
- Các tính năng bao gồm: Màu nền, Màu phông chữ, Biểu tượng, và URL Web.
- **URL Web:** Cho phép liên kết dễ dàng đến các trang web liên quan đến dữ liệu. Cần tạo kết nối giữa trường dữ liệu và địa chỉ URL trong mô hình dữ liệu và sau đó định dạng có điều kiện dựa trên giá trị trong trường URL.
- **Sử dụng DAX để định dạng có điều kiện:** Biểu tượng Fx cho biết cơ hội sử dụng thước đo (measure) để tạo nội dung biến đổi hoặc định dạng nội dung có điều kiện (Ví dụ: tạo tiêu đề động dựa trên lựa chọn).

# 11. Các Yếu tố Trang khác
- Hình ảnh và Hình dạng: Sử dụng hình ảnh JPEG và PNG, cũng như các hình dạng để tạo hiệu ứng chiều sâu hoặc hình dạng phức hợp.
- Hộp văn bản (Text Boxes): Đặt văn bản tĩnh để cung cấp hướng dẫn hoặc chi tiết bổ sung.
- Nút (Buttons): Đã được nâng cấp với nhiều tính năng hơn. Có nhiều loại nút khác nhau (mũi tên, đặt lại, quay lại, thông tin, trợ giúp, Q&A, bookmark, trống, điều hướng).
- Tính năng quan trọng nhất của nút là Action (Hành động). Nếu không có hành động, nút chỉ là một hộp văn bản.
- Các hành động phổ biến: Drill through và Web URL. Có thể sử dụng nút trống để tạo nút drill-through tùy chỉnh với văn bản hướng dẫn.
- Trạng thái nút (Button States): Nút có thể được định dạng khác nhau dựa trên trạng thái của chúng (Default, On hover, On select, Disabled), cho phép thiết kế các lớp chức năng và hướng dẫn trên cùng một trang.
- Nút Điều hướng (Navigation Button): Nút chuyên dụng để tạo điều hướng trang thuận tiện, có thể bao gồm tất cả các trang trong báo cáo và tự động điều chỉnh để làm nổi bật trang hiện tại. Có thể cấu hình để hiển thị hoặc ẩn các trang ẩn hoặc trang công cụ chú giải (tooltip pages).

# 12. Báo cáo Phân trang (Paginated Reports)
- Có những trường hợp báo cáo chuẩn của Power BI Desktop không phù hợp, đặc biệt khi cần tuân thủ kích thước giấy cụ thể (in ấn), bao gồm tất cả các hàng của bảng dài, hoặc căn chỉnh hoàn hảo các yếu tố trên trang in.
- Trong những trường hợp này, báo cáo phân trang là cần thiết. Có thể tải xuống Power BI Report Builder miễn phí để xây dựng báo cáo phân trang.
- Có một hình ảnh trực quan báo cáo phân trang cho phép nhúng báo cáo phân trang vào báo cáo Power BI chuẩn.
- Báo cáo phân trang có thể được xuất bản lên Power BI Service nếu người dùng có quyền Admin, Member, hoặc Contributor trong không gian làm việc Premium.

