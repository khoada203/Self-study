# MỤC LỤC

1. [Truy cập Power Query Editor (PQE)](#1-truy-cập-power-query-editor-pqe)
2. [Power Query Editor là gì?](#2-power-query-editor-là-gì)
3. [Các loại chuyển đổi (Transformations)](#3-các-loại-chuyển-đổi-transformations)
4. [Ngôn ngữ M và các Bước Áp dụng (Applied Steps)](#4-ngôn-ngữ-m-và-các-bước-áp-dụng-applied-steps)
5. [Hoàn tác và Làm lại một Bước (Undoing and Redoing a Step)](#5-hoàn-tác-và-làm-lại-một-bước-undoing-and-redoing-a-step)
6. [Đặt tên và Ghi chú (Naming and Documenting)](#6-đặt-tên-và-ghi-chú-naming-and-documenting)
7. [Chất lượng và Phân phối dữ liệu (Data Quality and Distribution)](#7-chất-lượng-và-phân-phối-dữ-liệu-data-quality-and-distribution)
8. [Khóa và ID (Keys and IDs)](#8-khóa-và-id-keys-and-ids)
9. [Kiểu dữ liệu rất quan trọng (Data Types Matter!)](#9-kiểu-dữ-liệu-rất-quan-trọng-data-types-matter)
10. [Query Folding](#10-query-folding)
11. [Thay thế dữ liệu (Replacing Data)](#11-thay-thế-dữ-liệu-replacing-data)
12. [Thêm dữ liệu mới (Adding New Data)](#12-thêm-dữ-liệu-mới-adding-new-data)
13. [Chỉ giữ lại những gì bạn cần (Keep Only What You Need)](#13-chỉ-giữ-lại-những-gì-bạn-cần-keep-only-what-you-need)
14. [Kết hợp truy vấn (Combining Queries)](#14-kết-hợp-truy-vấn-combining-queries)
15. [Sao chép và Tham chiếu truy vấn (Duplicating and Referencing a Query)](#15-sao-chép-và-tham-chiếu-truy-vấn-duplicating-and-referencing-a-query)
16. [Xóa truy vấn (Deleting a Query)](#16-xóa-truy-vấn-deleting-a-query)
17. [Làm việc với một phần dữ liệu (Working with Some Data)](#17-làm-việc-với-một-phần-dữ-liệu-working-with-some-data)
18. [Tương lai hóa công việc của bạn (Future-Proofing Your Work)](#18-tương-lai-hóa-công-việc-của-bạn-future-proofing-your-work)
19. [Giải quyết lỗi trong truy vấn của bạn (Resolving Errors in Your Query)](#19-giải-quyết-lỗi-trong-truy-vấn-của-bạn-resolving-errors-in-your-query)
20. [Tái sử dụng công việc của bạn (Reusing Your Work)](#20-tái-sử-dụng-công-việc-của-bạn-reusing-your-work)
21. [Tải truy vấn của bạn (hoặc không) (Loading Your Queries (or Not))](#21-tải-truy-vấn-của-bạn-hoặc-không-loading-your-queries-or-not)
22. [Một vài Mẹo và Thủ thuật](#22-một-vài-mẹo-và-thủ-thuật)

# 1. Truy cập Power Query Editor (PQE)
- PQE là một cửa sổ riêng biệt mở ra sau khi bắt đầu quy trình "Get data" trong Power BI Desktop.
- Nó không phải là ứng dụng độc lập; cần được truy cập thông qua Power BI Desktop, Power BI Service hoặc Excel.
- Có thể truy cập bằng cách chọn "Get data" hoặc "Transform data" trên tab Home.

# 2. Power Query Editor là gì?
- PQE là công cụ chính để định hình và làm sạch dữ liệu nguồn trước khi sử dụng.
- Dữ liệu nguồn thường không hoàn hảo, có thể thiếu cột, có cột không cần thiết, sai định dạng, chứa lỗi chính tả, viết tắt không nhất quán, hàng trống hoặc giá trị null.
- PQE giúp giải quyết những vấn đề này mà không cần thay đổi dữ liệu gốc.
- 💬 **Trích dẫn:** "Tôi nghĩ Power Query Editor là công cụ tốt nhất mà Microsoft từng tạo ra!"

# 3. Các loại chuyển đổi (Transformations)
**PQE cho phép thực hiện nhiều loại thay đổi trên dữ liệu, bao gồm nhưng không giới hạn:**
- Xóa, gộp, kết hợp và tách cột.
- Xóa hàng trên cùng, dưới cùng và xen kẽ.
- Thay đổi kiểu dữ liệu của cột.
- Kết hợp các truy vấn lại với nhau (gộp - merging, nối thêm - appending).
- Sao chép (duplicating) hoặc tham chiếu (referencing) một truy vấn.
- Đổi tên và ghi chú (documenting) cột, truy vấn và các bước.
- Thay thế giá trị, ô trống và lỗi.
- Thêm cột mới.
- Thêm phép tính mới.
💬 **Trích dẫn:** "Đây không phải là danh sách đầy đủ tất cả các loại thay đổi (được gọi là các chuyển đổi) mà bạn có thể thực hiện, nhưng để vượt qua kỳ thi PL-300, bạn nên thành thạo tất cả các chuyển đổi đã nói ở trên."

# 4. Ngôn ngữ M và các Bước Áp dụng (Applied Steps)
- Các hành động chuyển đổi trong PQE được ghi lại dưới dạng các bước riêng lẻ, gọi là "Applied Steps".
- Mỗi bước được "dịch" sang ngôn ngữ M và hiển thị trong Formula Bar.
- 💬 **Trích dẫn:** "Các nhấp chuột chuột của bạn được ghi lại và ghi lại trong các bước riêng lẻ, được gọi là Applied Steps."
- Không cần phải viết M từ đầu, nhưng hiểu cơ bản về M rất hữu ích cho kỳ thi và thực tế.
- 💬 **Trích dẫn:** "Để trở thành một 'người chuyển đổi' rất thành thạo, bạn cần phải rất quen thuộc với các lệnh mở rộng có sẵn."
- Formula Bar: Nên bật Formula Bar (trong tab View) để dễ dàng xem mã M cho từng bước.
  + Ngôn ngữ M:M là ngôn ngữ riêng biệt với DAX.
  + M phân biệt chữ hoa chữ thường (case sensitive).
  + M là ngôn ngữ chức năng (functional language).
  + Hàm M có đối số phân tách bằng dấu phẩy.
  + Dấu ngoặc nhọn "{}" trong M biểu thị danh sách.
  + Advanced Editor (trong tab Home) hiển thị toàn bộ kịch bản M của truy vấn.

# 5. Hoàn tác và Làm lại một Bước (Undoing and Redoing a Step)
- PQE không có nút "Undo" trên ribbon.
- Để sửa lỗi, làm việc trực tiếp với các "Applied Step" liên quan.
- Có thể xóa một bước bằng cách di chuột qua nó và nhấp vào dấu X màu đỏ.
- Có thể "Redo" một bước có biểu tượng bánh răng bên cạnh.
- Có thể sắp xếp lại các bước bằng cách kéo chúng lên hoặc xuống danh sách.

# 6. Đặt tên và Ghi chú (Naming and Documenting)
- Nên đổi tên cột và truy vấn sao cho dễ hiểu đối với người đọc báo cáo.
- 💬 **Trích dẫn:** "Bạn nên đổi tên cột và truy vấn bằng những tên có ý nghĩa đối với người đọc báo cáo của bạn."
- Hai cột trong cùng một truy vấn không thể có cùng tên, nhưng các cột trong các truy vấn khác nhau có thể.
- Các cột khóa (key columns) dùng để liên kết các bảng nên có cùng tên trong các truy vấn khác nhau.
- Cân nhắc việc sử dụng khoảng trắng trong tên cột/truy vấn (yêu cầu sử dụng dấu ngoặc đơn ' ' khi tham chiếu trong M nếu có khoảng trắng).
- Nên tuân thủ hoặc thiết lập một quy ước đặt tên.
- Nên đổi tên tất cả các cột trong một bước "Applied Step" duy nhất.
- Nên đổi tên các bước, đặc biệt là các bước lọc dữ liệu, để dễ dàng tìm kiếm và sửa lỗi.
- Ghi chú Truy vấn: Sử dụng "All Properties" trên bảng Applied Steps để thêm mô tả cho toàn bộ truy vấn. Mô tả này sẽ xuất hiện trong chú giải công cụ (tooltip) trong Power BI Desktop.
- Ghi chú Bước: Chuột phải vào một bước và chọn "Properties" để thêm mô tả. Mô tả này sẽ xuất hiện dưới dạng biểu tượng "i" bên cạnh bước.
- 💬 **Trích dẫn:** "Việc ghi chú là một 'mũi khâu kịp thời cứu được chín mũi khác'-hãy làm nó trong khi bạn đang làm việc. Bạn (hoặc đồng nghiệp của bạn) sẽ biết ơn sau này!"

# 7. Chất lượng và Phân phối dữ liệu (Data Quality and Distribution)
- Nên bật các công cụ Data Preview (Column quality, Column distribution, Column profile) trên tab View khi lần đầu kết nối với nguồn dữ liệu không quen thuộc.
  + **Những điều cần tìm kiếm:Giá trị trống/null:** Xác định chiến lược xử lý (thay thế bằng "0", "N/A", hoặc để trống). PQE xử lý Blank và Null khác nhau.
  + **Tỷ lệ Distinct/Unique:** Distinct là số lượng giá trị khác nhau; Unique là số lượng giá trị không lặp lại. Tỷ lệ gần 1/1 chỉ ra tính cardinality cao (mỗi giá trị gần như là duy nhất). Tỷ lệ gần 1/0 chỉ ra tính cardinality thấp (các giá trị lặp lại).
  + **Phân phối giá trị:** Kiểm tra xem có các loại dữ liệu khác nhau trong cùng một cột không (ví dụ: văn bản và số). Mục tiêu là làm cho kiểu dữ liệu nhất quán.

# 8. Khóa và ID (Keys and IDs)
- Mỗi hàng dữ liệu nên có một giá trị định danh duy nhất, gọi là "key".
- Khóa có thể là "native key" (được doanh nghiệp sử dụng, ví dụ: ID nhân viên) hoặc "surrogate key" (được quản trị viên cơ sở dữ liệu thêm vào để định danh duy nhất, không phụ thuộc vào logic nghiệp vụ).
- Trong dữ liệu cơ sở dữ liệu/kho dữ liệu, cột khóa thường có từ "key" trong tên.
- Nếu không, tìm cột có tỷ lệ Distinct/Unique là 1/1 trong Data Preview; đó có khả năng là cột khóa.
- Primary Key: Cột khóa trong bảng "nhà" của nó.
- Foreign Key: Cột khóa khi nó xuất hiện trong bảng khác.
- Quan hệ (relationships) giữa các bảng trong Power BI được tạo bằng cách kết nối cột primary key và foreign key.
- Đảm bảo mỗi truy vấn có một cột đóng vai trò là "key" và đơn giản hóa cột này nếu có thể.

# 9. Kiểu dữ liệu rất quan trọng (Data Types Matter!)
**Việc gán kiểu dữ liệu sai có thể ảnh hưởng đến hiệu suất và độ chính xác.**
- **Các quy tắc quan trọng:** Tiền tệ nên lưu trữ dưới dạng Fixed Decimal (độ chính xác 4 chữ số sau dấu phẩy).
- **Fixed Decimal khác với Decimal.** Decimal lưu trữ tối đa 15 chữ số, bao gồm cả phần nguyên và phần thập phân, có thể dẫn đến mất độ chính xác.
- Ngày nên lưu trữ dưới dạng Date. Thời gian (nếu cần) nên lưu trữ ở cột riêng.
- Sử dụng tùy chọn "Using Locale" (trong menu Data Type) cho Date, Fixed Decimal, Decimal nếu báo cáo được sử dụng ở các khu vực có định dạng khác nhau (ví dụ: US vs. rest-of-world).
- 💬 **Trích dẫn:** "Nếu bạn biết tệp PBIX của mình sẽ được sử dụng bởi ai đó ở một khu vực khác trên thế giới, bạn nên gán Date, Fixed Decimal và Decimal bằng tùy chọn Locale..."
- Nếu có thể, lưu trữ giá trị dưới dạng Whole Number. Đây là cách "rẻ nhất" để lưu trữ giá trị.
- Tránh lưu trữ giá trị dưới dạng Text nếu có thể. Giá trị Text là cách "đắt nhất" để lưu trữ.
- Các cột dùng để liên kết các bảng (primary/foreign keys) phải có cùng kiểu dữ liệu (và nên có cùng tên).

💬 **Trích dẫn:** "Một đồng nghiệp nói với tôi rằng anh ấy đã tiết kiệm được 30% tổng kích thước mô hình dữ liệu bằng cách thay đổi một cột từ kiểu dữ liệu văn bản sang kiểu dữ liệu số nguyên."
📝 Kiểm tra kiểu dữ liệu nên là bước cuối cùng trước khi hoàn thành chuyển đổi truy vấn.
📝 Cẩn thận với các bước "Changed Type" thừa do PQE tạo ra, có thể xóa chúng trừ khi chúng cần thiết cho các bước sau.

# 10. Query Folding
- Query folding là khả năng đẩy các chuyển đổi về phía nguồn dữ liệu (nếu nguồn dữ liệu có "engine" mạnh mẽ như SQL Server) để thực hiện chúng, giúp tăng tốc độ.
- Một số chuyển đổi có thể phá vỡ query folding (ví dụ: thay đổi kiểu dữ liệu).
- Trích dẫn: "Đây là tính năng mà bạn không biết mình cần cho đến khi bạn làm vỡ nó."
- Nên thay đổi kiểu dữ liệu ở bước cuối cùng để các bước trước đó có thể được gập lại.
- Các nguồn dữ liệu không có "engine" (Excel, CSV, PDF) không hỗ trợ query folding.
- Kiểm tra Query Folding: Chuột phải vào một bước trong Applied Steps. Nếu "View Native Query" bị mờ đi (grayed out), query folding không xảy ra. Nếu nó hoạt động, nhấp vào đó để xem mã M được dịch sang ngôn ngữ gốc của nguồn.
- Mặc dù query folding có thể không xuất hiện trực tiếp trên kỳ thi PL-300, nhưng đây là kỹ năng quan trọng để trở thành một người thực hành Power BI giỏi.
- 💬 Trích dẫn: "Hãy thực hành những thói quen tốt tương tự bất kể loại truy vấn có hỗ trợ folding hay không. Sau đó, bạn sẽ không vô tình làm vỡ folding khi nó có sẵn vì thói quen cẩu thả."

# 11. Thay thế dữ liệu (Replacing Data)
**Blanks và Nulls:** PQE xử lý Blank và Null khác nhau. Sử dụng tính năng "Replace Values". Để thay thế Null, nhập "null" vào ô "Value To Find". Để thay thế Blank, để trống ô "Value To Find".
- **Errors:** Các lỗi trong 1000 hàng đầu tiên có thể được xem chi tiết bằng cách nhấp vào ô chứa lỗi.
- Menu ngữ cảnh trên thanh Data Quality peek cung cấp các tùy chọn xử lý lỗi (remove errors, replace errors).
- Để xem lỗi ngoài 1000 hàng đầu tiên, thay đổi hành vi profiling ở góc dưới bên trái sang "Profile entire data set".
- Sử dụng tùy chọn "Keep Errors" từ menu ngữ cảnh Data Quality peek để tạo một truy vấn chỉ chứa các hàng có lỗi. Điều này hữu ích cho việc chẩn đoán. Nên sao chép truy vấn gốc trước khi thực hiện bước này.

# 12. Thêm dữ liệu mới (Adding New Data)
- **PQE cho phép tạo dữ liệu mới dưới dạng cột hoặc bảng (truy vấn mới).**
- **Thêm Cột Mới:** Có nhiều cách để tạo cột mới: Column from Examples, Custom Column, Conditional Column, Index Column, Duplicate Column. Chọn phương pháp hiệu quả nhất cho tác vụ.
- **Thêm Truy vấn Mới:** Có thể tạo một truy vấn trống hoặc sao chép/tham chiếu một truy vấn hiện có.

# 13. Chỉ giữ lại những gì bạn cần (Keep Only What You Need)
- PQE rất linh hoạt và ít quyết định là không thể đảo ngược.
- Nên loại bỏ các cột hoặc truy vấn không cần thiết để đơn giản hóa dữ liệu trước khi tải vào Power BI Desktop.
- 💬 **Trích dẫn:** "Đừng đưa một truy vấn hoặc một cột nào đó vào 'chỉ trong trường hợp'." Bạn luôn có thể quay lại để lấy nó.

# 14. Kết hợp truy vấn (Combining Queries)
- **Append:** Kết hợp các hàng từ nhiều truy vấn vào một truy vấn duy nhất. Hữu ích khi có nhiều tệp có cấu trúc tương tự (ví dụ: dữ liệu hàng tháng). Nên đảm bảo cấu trúc cột (số lượng, tên, kiểu dữ liệu) giống nhau khi nối thêm. Có thể nối thêm vào truy vấn hiện có hoặc tạo truy vấn mới.
- **Merge:** Kết hợp các cột từ hai truy vấn dựa trên một hoặc nhiều cột chung. Quan trọng là hiểu cách bạn muốn gộp hai truy vấn.
- Có bảy loại join patterns:
  + **Left outer join:** Tất cả các hàng từ truy vấn bên trái, các hàng khớp từ truy vấn bên phải.
  + **Right outer join:** Tất cả các hàng từ truy vấn bên phải, các hàng khớp từ truy vấn bên trái.
  + **Full outer join:** Tất cả các hàng từ cả hai truy vấn.
  + **Inner join:** Chỉ các hàng có mặt trong cả hai truy vấn (khớp).
  + **Left anti join:** Chỉ các hàng trong truy vấn A không có hàng khớp trong truy vấn B.
  + **Right anti join:** Chỉ các hàng trong truy vấn B không có hàng khớp trong truy vấn A.
  + **Full anti join:** Chỉ các hàng trong cả hai truy vấn không có hàng khớp trong truy vấn còn lại.
- Full outer join hữu ích để xác định nơi hai truy vấn không khớp.

# 15. Sao chép và Tham chiếu truy vấn (Duplicating and Referencing a Query)
- **Duplicating:** Tạo một bản sao chính xác của truy vấn. Hữu ích để bảo toàn truy vấn gốc hoặc sử dụng làm cơ sở cho việc nối thêm.
- **Referencing:** Tạo một phiên bản thứ hai của truy vấn. Bất kỳ thay đổi nào trong truy vấn gốc sẽ được áp dụng cho truy vấn tham chiếu. Hữu ích khi bạn vẫn đang làm việc trên truy vấn gốc nhưng cần một bản sao phản ánh các thay đổi liên tục.
- 💬 **Trích dẫn (Vấn đề về phong cách):** "Rất nhiều lựa chọn bạn đưa ra trong Power Query Editor là vấn đề về phong cách. Khi nối các tệp, tôi thích nối (hoặc gộp) tất cả chúng vào một truy vấn mới, giữ nguyên bản gốc."

# 16. Xóa truy vấn (Deleting a Query)
- Có thể xóa truy vấn nếu không cần thiết.
- Không thể xóa truy vấn đang được sử dụng trong một truy vấn khác (ví dụ: đã được nối thêm hoặc gộp).

# 17. Làm việc với một phần dữ liệu (Working with Some Data)
- PQE hiển thị bản xem trước (preview) lên đến 1000 hàng.
- Bạn không thực sự chuyển đổi dữ liệu ngay lập tức; bạn đang viết một kịch bản chuyển đổi sẽ được áp dụng khi tải dữ liệu vào Desktop.
- 1000 hàng thường đủ để hiểu cấu trúc và bố cục dữ liệu.
- Lọc dữ liệu: Lọc loại trừ các hàng không đáp ứng điều kiện. Các hàng bị lọc sẽ không xuất hiện trong báo cáo cuối cùng.
- Sử dụng Filters ➤ Load more để xem tối đa 1000 giá trị duy nhất trong mỗi cột.
- Nếu có hơn 1000 giá trị duy nhất và cần lọc, sử dụng bộ lọc thủ công (manual filters).
- Có thể cuộn qua dữ liệu trong cửa sổ Preview, nhưng việc này tẻ nhạt với tập dữ liệu lớn.

# 18. Tương lai hóa công việc của bạn (Future-Proofing Your Work)
- Giả định rằng dữ liệu nguồn có thể thay đổi (cột được đổi tên, thêm, xóa; tệp bị di chuyển, thêm, xóa).
- Cần xây dựng kịch bản chuyển đổi để xử lý các thay đổi này mà không bị lỗi. Đây gọi là tương lai hóa (future-proofing).
- Bước đầu tiên là giữ Formula Bar hiển thị và đọc mã M cho mỗi bước.
- Loại trừ và Bao gồm cột:Remove Columns loại trừ các cột được chỉ định. Nếu cột mới được thêm vào nguồn, nó sẽ xuất hiện trong kết quả.
- Select Columns chỉ giữ lại các cột được chỉ định. Nếu cột mới được thêm vào nguồn, nó sẽ KHÔNG xuất hiện trong kết quả.
- Việc tương lai hóa các truy vấn nâng cao hơn có thể nằm ngoài phạm vi của kỳ thi PL-300, nhưng rất quan trọng trong thực tế.

# 19. Giải quyết lỗi trong truy vấn của bạn (Resolving Errors in Your Query)
- Khi thấy biểu tượng lỗi màu vàng, bắt đầu khắc phục sự cố từ bước bị lỗi và làm ngược lên các bước trước đó cho đến khi tìm thấy bước không bị lỗi.
- Xác định điều gì đã xảy ra giữa bước cuối cùng hoạt động và bước đầu tiên bị lỗi.
- Các lỗi phổ biến:
  + **Incorrect Data Type:** Cần thay đổi kiểu dữ liệu trước khi thực hiện phép toán không tương thích. Thêm bước Changed Type trước bước gây lỗi.
  + **Missing or Renamed Column:** Nếu một bước phụ thuộc vào một cột đã bị đổi tên hoặc xóa ở bước trước đó, lỗi sẽ xảy ra. Sửa lỗi bằng cách đổi tên lại cột, xóa bước đổi tên/xóa sai vị trí hoặc sắp xếp lại các bước.

# 20. Tái sử dụng công việc của bạn (Reusing Your Work)
- Có thể tái sử dụng kịch bản M đã viết để tiết kiệm thời gian.
- **Advanced Editor:** Hiển thị toàn bộ mã M cho một truy vấn. Có thể chỉnh sửa trực tiếp mã M (nếu tự tin) hoặc sao chép mã M dưới dạng văn bản thuần túy.
  + ⚠️ Lưu ý khi chỉnh sửa M: Dấu phẩy sau mỗi bước trừ bước cuối cùng; bắt đầu bằng let, kết thúc bằng in; câu lệnh in thường tham chiếu đến tên bước cuối cùng; nguồn (Source) phải trỏ đúng vị trí; kiểm tra các giá trị được mã hóa cứng (trong dấu ngoặc kép) và tham chiếu bước khi sao chép.
- Sao chép Truy vấn: Cách dễ nhất để tái sử dụng kịch bản M là sao chép toàn bộ truy vấn trong bảng Queries (Ctrl+C/Ctrl+V giữa các tệp PBIX).
- Sao chép các phần của kịch bản M: Có thể sao chép các phần của mã M từ Formula Bar hoặc Advanced Editor vào trình soạn thảo văn bản và dán vào truy vấn khác.
  + ⚠️ Lưu ý khi sao chép từng phần: Tên bước, tên cột và tham chiếu nguồn có thể khác nhau; cẩn thận với dấu phẩy ở cuối mỗi bước.

# 21. Tải truy vấn của bạn (hoặc không) (Loading Your Queries (or Not))
- Sau khi hoàn thành chuyển đổi, các thay đổi sẽ được áp dụng cho toàn bộ dữ liệu khi tải vào mô hình dữ liệu.
- Đôi khi bạn không muốn tải một truy vấn cụ thể (ví dụ: truy vấn "helper" đã được nối thêm hoặc gộp vào truy vấn khác).
- Để tắt tải một truy vấn, chuột phải vào tên truy vấn và bỏ chọn hộp kiểm **"Enable Load"**.
- Truy vấn bị tắt tải sẽ xuất hiện với tên in nghiêng trong PQE nhưng sẽ không hiển thị trong Power BI Desktop.

# 22. Một vài Mẹo và Thủ thuật
- Ghi chú truy vấn và các bước.
- Giữ các bước tương tự nhau ở gần nhau.
- Đặt tên cho các bước.
- Kiểu dữ liệu rất quan trọng – chọn chúng một cách có chủ đích.
- Giữ Formula Bar mở và đọc mã M cho mỗi bước.
- Tương lai hóa truy vấn của bạn hết sức có thể.
- Tái sử dụng kịch bản M khi thích hợp.
- Thay đổi kiểu dữ liệu càng gần bước cuối cùng càng tốt.
