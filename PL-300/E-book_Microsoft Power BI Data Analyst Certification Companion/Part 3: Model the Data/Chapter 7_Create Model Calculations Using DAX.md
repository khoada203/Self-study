# MỤC LỤC

1. [Measures (Phép đo)](#1-measures-phép-đo)
2. [IntelliSense](#2-intellisense)
3. [Filter Context (Ngữ cảnh lọc)](#3-filter-context-ngữ-cảnh-lọc)
4. [Hàm CALCULATE](#4-hàm-calculate)
5. [Row Context (Ngữ cảnh hàng)](#5-row-context-ngữ-cảnh-hàng)
6. [Implicit and Explicit Measures (Measures ngầm định và tường minh)](#6-implicit-and-explicit-measures-measures-ngầm-định-và-tường-minh)
7. [Quick Measures (Measures nhanh)](#7-quick-measures-measures-nhanh)
8. [Các loại hàm DAX](#8-các-loại-hàm-dax)
9. [Time Intelligence Functions (Hàm thời gian)](#9-time-intelligence-functions-hàm-thời-gian)
10. [Semi-additive Measures (Measures bán cộng)](#10-semi-additive-measures-measures-bán-cộng)
11. [Statistical Functions (Hàm thống kê)](#11-statistical-functions-hàm-thống-kê)
12. [DAX đơn giản, nhưng không dễ](#12-dax-đơn-giản-nhưng-không-dễ)

# 1. Measures (Phép đo)
- Measures là các phép tính mà dữ liệu của bạn chưa có.
- Chúng có thể từ phép cộng đơn giản đến các cách định dạng trực quan có điều kiện hoặc tạo tiêu đề động.
- Không giống như các cột tính toán (calculated columns) được tính cho từng hàng, measures tổng hợp dữ liệu trên toàn bộ cột hoặc theo ngữ cảnh lọc hiện tại.
- Measures được lưu trữ trong mô hình dữ liệu nhưng không được "materialized" (hiện thực hóa) cho đến khi được sử dụng trong một visual, do đó không đòi hỏi tài nguyên của công cụ cho đến lúc đó.
- Bạn sẽ không thấy measures trong Data view vì chúng không được materialized.
- Ví dụ: All_Sales=SUM('Orders Details'[LineTotal]) - Phép tính này cộng tổng toàn bộ cột LineTotal trong bảng 'Orders Details' và tạo một measure tên là All_Sales.
- Sự khác biệt chính với cột tính toán: Measures yêu cầu một hàm (SUM, AVERAGE, MIN, MAX, v.v.) trong biểu thức của chúng. Cột tính toán cần thiết khi bạn cần sử dụng giá trị tính toán trong slicer hoặc filter, hoặc khi phép tính phải được thực hiện từng hàng (hoặc sử dụng hàm lặp).

# 2. IntelliSense
- Một công cụ hữu ích tích hợp trong Power BI Desktop giúp viết cú pháp DAX đúng.
- IntelliSense gợi ý các hàm khi bạn bắt đầu gõ.
- Sau khi chọn hàm, nó hiển thị giải thích hàm và danh sách các đối số (bắt buộc/tùy chọn).
- Gõ dấu ngoặc đơn ' hiển thị danh sách các bảng (và cột).
- Gõ dấu ngoặc vuông mở [ hiển thị danh sách các measures.

# 3. Filter Context (Ngữ cảnh lọc)
- Ngữ cảnh lọc là cách để "chia nhỏ" dữ liệu thay vì chỉ tổng hợp toàn bộ.
- Ngữ cảnh lọc được giới thiệu thông qua:
  + Visual slicer.
  + Filters pane.
  + Drill-through từ trang khác.
  + Lựa chọn trên visual khác trên cùng trang.
  + Synced slicer.
 
# 4. Hàm CALCULATE
- Là công cụ để "tinh chỉnh và kiểm soát ngữ cảnh lọc".
- Hàm CALCULATE yêu cầu một đối số: biểu thức để tính toán (thường là một measure hoặc một biểu thức tổng hợp).
- Hàm CALCULATE có thể nhận thêm các đối số tùy chọn:
  + Filter context modifiers: Thêm, sửa đổi hoặc loại bỏ các filter. Ví dụ: REMOVEFILTERS, ALL, ALLEXCEPT.
  + Model modifiers: Thay đổi chức năng của mô hình tạm thời. Ví dụ: USERELATIONSHIP, CROSSFILTER.
- CALCULATE không xóa bỏ ngữ cảnh lọc hiện tại, mà "đắp" (superimpose) các điều kiện lọc được bao gồm trong measure lên ngữ cảnh lọc hiện tại.
- **Ví dụ (Loại bỏ filter):**
```
All_Sales_AllCountries=
CALCULATE(
[All_Sales],
REMOVEFILTERS('Customers'[Country]
)
```
--> Measure này loại bỏ bất kỳ filter nào đến từ trường 'Customers'[Country] trước khi tính toán [All_Sales].

- **Ví dụ (Hard-code filter):**
```
All_Sales_GermanyandBeverages=
CALCULATE([All_Sales],
'Customers'[Country]= "Germany",
'Categories'[CategoryName]= "Beverages"
)
```
--> Measure này buộc ngữ cảnh lọc phải là Country="Germany" và Category="Beverages", ghi đè bất kỳ filter bên ngoài nào xung đột với các điều kiện này.

# 5. Row Context (Ngữ cảnh hàng)
- Ngữ cảnh hàng đề cập đến việc thực hiện phép tính từng hàng.
- Cột tính toán hoạt động trong ngữ cảnh hàng mặc định.
- Các hàm lặp (Iterator functions) có chữ 'X' ở cuối (SUMX, AVERAGEX, MAXX, v.v.) cho phép thực hiện phép tính từng hàng trong measure.
- Ví dụ sử dụng SUMX:
```
LineTotalAsMeasure =
SUMX (
'Orders Details',
('Orders Details'[Quantity] * 'Orders Details'[UnitPrice]) - 'Orders Details'[Discountvalue]
)
```
--> SUMX lặp qua từng hàng của bảng 'Orders Details' và tính biểu thức trong ngoặc đơn cho mỗi hàng, sau đó cộng tổng các kết quả.

# 6. Implicit and Explicit Measures (Measures ngầm định và tường minh)
- Implicit measures: Được tạo tự động khi bạn kéo một trường (thường là cột số) vào visual mà không có measure tường minh nào. Chúng tiện lợi nhưng hành vi tổng hợp mặc định có thể dễ dàng thay đổi.
- Explicit measures: Được tạo thủ công bằng DAX (ví dụ: All_Sales=SUM('Orders Details'[LineTotal])). Chúng được "khóa lại" và hành vi tổng hợp không thể sửa đổi bởi người dùng báo cáo.
- Nên tạo measures tường minh cho tất cả các phép tính cần thiết cho người xem báo cáo để kiểm soát hành vi tổng hợp và nhất quán.
- Sau khi tạo measures tường minh, có thể ẩn cột "cơ sở" (ví dụ: LineTotal) để đơn giản hóa mô hình khi báo cáo được xuất bản.

# 7. Quick Measures (Measures nhanh)
- Một tính năng giúp tạo measures tự động dựa trên các mẫu tính toán tích hợp sẵn.
- Bạn kéo các trường vào các vị trí thích hợp trong hộp thoại để wizard viết DAX cho bạn.
- DAX được tạo bởi wizard có thể "clunky" (cồng kềnh) nhưng là một cách tốt để bắt đầu học DAX.
- Nên đổi tên measures được tạo bằng Quick measure wizard.

# 8. Các loại hàm DAX
- DAX cung cấp hàng trăm hàm được phân loại thành các nhóm như: Logic, Tổng hợp (Aggregation), Thống kê, Văn bản, Thời gian (Time intelligence), Toán học/Lượng giác, Ngày/Giờ, Lọc, Thao tác bảng (Table manipulation), Tài chính.

# 9. Time Intelligence Functions (Hàm thời gian)
- Cho phép thực hiện các phép tính liên quan đến thời gian phổ biến (Year-to-date, Same period last year, v.v.).
- Yêu cầu: Cần một bảng ngày được đánh dấu (marked date table).
- Mẹo: Nên bao gồm một trường từ bảng ngày trong visual khi sử dụng hàm thời gian để kết quả rõ ràng.
- Có thể sử dụng các hàm thời gian để sửa đổi ngữ cảnh lọc.
- Ví dụ:
```
Sales_Last_Year = CALCULATE([All Sales], PARALLELPERIOD('DateDim'[Date],-12,MONTH))
```
--> Sử dụng PARALLELPERIOD để dịch chuyển ngữ cảnh lọc về 12 tháng trước.

# 10. Semi-additive Measures (Measures bán cộng)
- Các phép tính không nên được tổng hợp theo cách thông thường, thường là "point-in-time" (tại một điểm thời gian) (ví dụ: số dư ngân hàng, tồn kho).
- DAX cung cấp các hàm cho các phép tính này (ví dụ: OPENINGBALANCEYEAR, CLOSINGBALANCEYEAR, ENDOFMONTH, STARTOFMONTH).
- Đối với các phép tính bán cộng không có hàm chuyên dụng (ví dụ: tổng doanh số theo danh mục khi tổng cộng không có ý nghĩa), có thể sử dụng các hàm như HASONEVALUE, HASONEFILTER, ISINSCOPE kết hợp với IF để chỉ trả về giá trị khi ngữ cảnh lọc có một giá trị cụ thể.

# 11. Statistical Functions (Hàm thống kê)
- Được đề cập cụ thể trong các mục chuẩn bị cho kỳ thi PL-300.
- Hoạt động tương tự các hàm DAX khác.
- Quan trọng là phải làm quen với các nguyên tắc thống kê cơ bản (median, average, standard deviation).

# 12. DAX đơn giản, nhưng không dễ
- Đây là một câu nói phổ biến trong cộng đồng Power BI.
- Để thành thạo DAX, hãy tập trung vào việc hiểu Filter Context và Row Context. Chúng là hai khái niệm khó nhất để làm chủ, nhưng khi bạn hiểu chúng, kỹ năng DAX của bạn sẽ cải thiện đáng kể.
