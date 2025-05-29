# Mục Lục

1. [Kết nối dữ liệu](#1-kết-nối-dữ-liệu)
2. [Nhập thông tin đăng nhập](#2-nhập-thông-tin-đăng-nhập)
3. [Thay đổi cài đặt nguồn dữ liệu](#3-thay-đổi-cài-đặt-nguồn-dữ-liệu)  
   3.1 [Mức độ riêng tư (Privacy Levels)](#31-mức-độ-riêng-tư-privacy-levels)
4. [Chọn chế độ lưu trữ (Storage Mode)](#4-chọn-chế-độ-lưu-trữ-storage-mode)
5. [Sử dụng các nguồn dữ liệu khác nhau](#5-sử-dụng-các-nguồn-dữ-liệu-khác-nhau)  
   5.1 [Dataverse](#51-dataverse)  
   5.2 [Dataflows](#52-dataflows)  
   5.3 [Shared Dataset (Bộ dữ liệu được chia sẻ)](#53-shared-dataset-bộ-dữ-liệu-được-chia-sẻ)  
   5.4 [Local Dataset (Bộ dữ liệu cục bộ)](#54-local-dataset-bộ-dữ-liệu-cục-bộ)  
   5.5 [Sử dụng Thư mục và Thư mục SharePoint](#55-sử-dụng-thư-mục-và-thư-mục-sharepoint)
6. [Tham số (Parameters)](#6-tham-số-parameters)


# 1. Kết nối dữ liệu
- Power BI cung cấp nhiều tùy chọn kết nối đến các nguồn dữ liệu khác nhau, được gọi là "connectors".
- Quan trọng là phải biết các trình kết nối được sử dụng phổ biến cho kỳ thi PL-300 và trong thực tế.
- Các trình kết nối phổ biến bao gồm: SQL Server (tất cả các loại), Excel/CSV, Thư mục (SharePoint và File Explorer), Power Platform, Azure, Dataflows và Bộ dữ liệu của Power BI.
- "Xem xét tất cả các trình kết nối có sẵn; bạn có thể sẽ không gặp câu hỏi nào trên PL-300 về một trình kết nối không phổ biến, nhưng bạn nên biết các trình kết nối được sử dụng phổ biến."
# 2. Nhập thông tin đăng nhập
- Các loại trình kết nối khác nhau yêu cầu thông tin đăng nhập khác nhau  
- CSV và Excel không yêu cầu thông tin đăng nhập  
- Ví dụ: SQL Server yêu cầu thông tin đăng nhập Windows/database

# 3. Thay đổi cài đặt nguồn dữ liệu
- Nguồn bước trong Applied Steps của Power Query Editor lưu giữ siêu dữ liệu về đường dẫn tệp nguồn.
- Nếu cần thay đổi đường dẫn nguồn, bạn có thể thực hiện trong menu **Data source settings**.
- Đây là cách phổ biến để sửa lỗi đường dẫn tệp bị hỏng (ví dụ: khi tệp nguồn được di chuyển hoặc báo cáo được chia sẻ).
- Bạn có thể sửa đường dẫn trực tiếp từ màn hình lỗi bằng cách sử dụng nút **Go To Error** và tùy chọn **Edit Settings**.

## 3.1 Mức độ riêng tư (Privacy Levels)
- Để kiểm soát việc rò rỉ dữ liệu tiềm ẩn, bạn có thể kiểm soát mức độ riêng tư của dữ liệu trong Power Query Editor.
- Điều này đặc biệt quan trọng khi làm việc với dữ liệu bên ngoài tổ chức của bạn.
- Các tùy chọn mức độ riêng tư bao gồm:
  + None: Không có hạn chế riêng tư, có thể kết hợp với bất kỳ dữ liệu nào.
  + Public: Có thể kết hợp với các nguồn dữ liệu công khai hoặc tổ chức khác. Dữ liệu hiển thị cho bất kỳ ai. Chỉ các tệp, nguồn Internet và sổ làm việc mới có thể được đánh dấu là công khai.
  + Organizational: Chỉ có thể kết hợp với các nguồn dữ liệu khác được phân loại là "organizational".

- **Private:** Cách ly hoàn toàn dữ liệu, không thể kết hợp với bất kỳ nguồn dữ liệu nào khác, ngay cả các nguồn dữ liệu riêng tư khác.
- "Một nguồn dữ liệu được phân loại là riêng tư sẽ cách ly dữ liệu đó hoàn toàn. Nó không thể được kết hợp với bất kỳ nguồn dữ liệu nào khác, ngay cả các nguồn dữ liệu riêng tư khác."
- Có thể truy cập Mức độ riêng tư trong hộp thoại **Edit Permissions**.
- Việc đặt mức độ riêng tư quá nghiêm ngặt có thể gây ra lỗi Formula.Firewall.
- Mức độ riêng tư có thể làm chậm việc làm mới sau khi báo cáo được xuất bản lên Dịch vụ.
- Có tùy chọn tắt mức độ riêng tư trong **File > Options and settings > Options > Global > Privacy**, nhưng chỉ nên làm vậy khi chỉ làm việc với dữ liệu trong tầm kiểm soát của tổ chức.

# 4. Chọn chế độ lưu trữ (Storage Mode)
- Đối với các nguồn như SQL Server, bạn cần xác định chế độ lưu trữ: Import hoặc Direct Query.
- Việc hiểu sự khác biệt và hạn chế của các chế độ này rất quan trọng cho kỳ thi PL-300.

| **Import**                                                                                                                                     | **Direct Query**                                                                                                                                                   |
|------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Chế độ lưu trữ mặc định trong Power BI                                                                                                        | Kết nối trực tiếp giữa Power BI Desktop và nguồn dữ liệu                                                                     |
| Power BI sao chép dữ liệu và lưu vào bộ nhớ trong của Power BI                                                                                 | Luôn sử dụng dữ liệu mới nhất từ nguồn                                                                                       |
| Không ảnh hưởng đến nguồn gốc dữ liệu (không ghi ngược về nguồn)                                                                               | Phải “trả giá hiệu năng” để có được dữ liệu kịp thời                                                                        |
| Dữ liệu đại diện, không cần cập nhật liên tục                                                                                                   | Báo cáo phụ thuộc vào tốc độ kết nối đến nguồn dữ liệu                                                                      |
| Xử lý nhanh hơn, hiệu quả hơn trong phần phản hồi                                                                                              | Không thể thay đổi hay mô hình hóa dữ liệu trong Power BI Desktop                                                          |
| Kiểm soát toàn bộ mô hình dữ liệu (tạo measure, bảng, quan hệ, v.v.)                                                                           | Có thể ảnh hưởng hiệu năng hệ thống nguồn dữ liệu                                                                           |
|                                                                                                                                                 | Chỉ nên dùng Direct Query nếu có nhu cầu dữ liệu cập nhật tức thời và lý do kinh doanh vượt trội                            |
|                                                                                                                                                 | Nên cân nhắc các yếu tố: tần suất truy cập, dữ liệu cần cập nhật liên tục, ảnh hưởng đến hệ thống khi chọn Direct Query     |

- **Kết nối trực tiếp (Live Connection):**
  + Xảy ra khi kết nối với nguồn Analysis Services.
  + Ba nguồn này là: SQL Server Analysis Services Tabular, SQL Server Analysis Services Multidimensional và Bộ dữ liệu của Power BI Service.
- **Hybrid Tables (Ghi chú nhanh):**
  + Khả năng kết hợp dữ liệu đã nhập và dữ liệu được truy cập qua Direct Query.
  + Được thực hiện bằng cách phân vùng dữ liệu.
  + Lợi ích chính là hiệu năng nhanh của dữ liệu đã nhập và dữ liệu mới nhất qua Direct Query.
  + Không được đề cập trong kỳ thi PL-300 và ngoài phạm vi của sách.

# 5. Sử dụng các nguồn dữ liệu khác nhau
## 5.1 Dataverse
- **Tên mới của "Common Data Service".**
- Cơ sở hạ tầng cơ sở dữ liệu sẵn có với các bảng định sẵn (ví dụ: tài khoản, liên hệ).
- "Đó là một cơ sở dữ liệu đóng hộp."
- Một phần của Open Data Initiative.
- Có thể sử dụng để xây dựng các bảng tùy chỉnh.
- Nền tảng dữ liệu của toàn bộ Power Platform.
- Yêu cầu URL của môi trường Dataverse để kết nối.
## 5.2 Dataflows
- **Một tập hợp dữ liệu đã được biến đổi và lưu lại công việc đó.**
- Được tạo bởi người dùng có kỹ năng Power Query Editor để chia sẻ dữ liệu đã chuẩn bị.
- Hữu ích khi nhiều người tạo báo cáo cần kết nối với cùng một nguồn cơ bản nhưng không nên kết nối trực tiếp.
- Yêu cầu quyền truy cập vào dataflow.
- Việc kết nối tương tự như với bất kỳ nguồn dữ liệu nào khác.
## 5.3 Shared Dataset (Bộ dữ liệu được chia sẻ)
- **Một bộ dữ liệu đã được người khác trong tổ chức chuẩn bị kỹ lưỡng (biến đổi và mô hình hóa).**
- Bất kỳ ai có quyền đều có thể sử dụng nó để tạo báo cáo mới.
- Tiết kiệm thời gian đáng kể.
- Việc sử dụng bộ dữ liệu được chia sẻ tạo ra một Live Connection.
## 5.4 Local Dataset (Bộ dữ liệu cục bộ)
- Bộ dữ liệu nằm trên máy tính của bạn.
- Việc kết nối bình thường, nhưng thiết lập lịch làm mới trong Power BI Service yêu cầu gateway để Dịch vụ "tiếp cận" bộ dữ liệu cục bộ.
## 5.5 Sử dụng Thư mục và Thư mục SharePoint
- Có thể kết nối trực tiếp đến một thư mục (trên ổ đĩa chia sẻ, máy tính xách tay, SharePoint) thay vì từng tệp riêng lẻ.
- Việc trích xuất ban đầu là một danh sách nội dung thư mục (siêu dữ liệu).
- "Điều bạn sẽ trích xuất là một danh sách những gì có trong thư mục (siêu dữ liệu)."
- Có một siêu liên kết để mở rộng tập dữ liệu thực tế cho mỗi mục trong danh sách.
- Hiệu quả hơn khi xử lý các tệp liên quan trong cùng một thư mục (ví dụ: sổ làm việc Excel hàng tháng).
- Có thể kết hợp các tệp riêng lẻ thành một truy vấn duy nhất.
- Nên kết hợp các tệp có cùng cấu trúc (số cột, tên cột).
- Thư mục SharePoint hoạt động tương tự, nhưng cần URL cấp cao nhất của SharePoint.

# 6. Tham số (Parameters)
- Trong Power BI, một tham số là một hằng số tùy ý hoặc một biến độc lập.
- Tham số làm một trong ba việc:
  + Cung cấp giá trị cho một hàm trong Power Query Editor
  + Cho phép người dùng nhập giá trị trong Power BI Desktop
  + Cho phép người dùng nhập giá trị trong Power BI Service.
- Đối với kỳ thi PL-300, bạn sẽ được mong đợi biết cách thay đổi giá trị của tham số.
- **Định nghĩa Tham số:** Tất cả các tham số cần được định nghĩa trong Power Query Editor.
- **Các bước bao gồm:** Chọn Manage Parameters, New Parameter, điền vào hộp thoại New Parameter (tên, mô tả, kiểu dữ liệu, giá trị được đề xuất, giá trị mặc định).
- Truy cập tham số trong Power BI Desktop thông qua Transform data > Edit parameters.
