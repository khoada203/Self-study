## Mục Lục

1. [Mục tiêu PL-300](#1-mục-tiêu-pl-300)
2. [Các công cụ Power BI](#2-các-công-cụ-power-bi)
3. [Phân biệt](#3-phân-biệt)  
   3.1 [Report và Dashboard](#31-report-và-dashboard)  
   3.2 [Workspaces, My workspace, và Apps](#32-workspaces-my-workspace-và-apps)
4. [Cấp phép (Licensing)](#4-cấp-phép-licensing)
5. [Ngôn ngữ Power BI](#5-ngôn-ngữ-power-bi)
6. [Luyện tập trước PL-300](#6-luyện-tập-trước-pl-300)
7. [Nội dung sách (Cách tiếp cận)](#7-nội-dung-sách-cách-tiếp-cận)


# 1. Mục tiêu PL-300
- **PL-300 là kỳ thi "phổ rộng":** Kỳ thi PL-300 bao gồm các lĩnh vực toàn diện từ Power Query Editor (PQE) đến Power BI Desktop và Power BI Service.
- **Hệ sinh thái Power BI và Thuật ngữ Cơ sở dữ liệu:** Power BI có nguồn gốc sâu sắc từ công nghệ cơ sở dữ liệu, do đó có nhiều thuật ngữ liên quan đến cơ sở dữ liệu.

# 2. Các công cụ Power BI
| **Power BI Desktop** | **Power Query Editor (PQE)** | **Power BI Service** |
|----------------------|-------------------------------|-----------------------|
| Dành cho phát triển mô hình dữ liệu và báo cáo | Dùng để trích xuất, biến đổi và tải (ETL) dữ liệu | Nơi xuất bản và phân phối báo cáo/dashboards |
| Miễn phí, tải từ Microsoft Store hoặc website | Dùng trong Power BI Desktop, Excel 2016+, và Service | Tích hợp với Office 365 |
| Có thể dùng không cần đăng nhập Power BI Service | Áp dụng ETL: Trích xuất, Biến đổi, Tải dữ liệu | Truy cập qua [app.powerbi.com](https://app.powerbi.com) |
| Không đăng nhập thì không xuất bản được báo cáo | Các kỹ năng trong PQE dùng được ở cả Excel & Service | Đăng nhập bằng Office 365 để dùng bản miễn phí/thử |
| Là môi trường phát triển, cần tư duy của nhà phát triển | Tính năng mới được phát hành theo thứ tự: PQE Service → PQE Desktop → PQE Excel | Từ Desktop có thể xuất bản trực tiếp lên Service |
| Không chia sẻ PBIX cho người khác cùng chỉnh sửa được |   | Các khu vực chính: My Workspace, Workspaces, Apps |
| Không có phiên bản cho Mac |   | Tài khoản Power BI miễn phí chỉ dùng được My Workspace |
| Cần máy cấu hình tối thiểu 8GB RAM (tốt nhất 16–32GB) |   | Dùng Power BI Pro miễn phí 60 ngày để dùng đầy đủ Service |
| Không chia sẻ trực tiếp, không dùng online |   | Có thể nhúng dashboard vào sản phẩm khác |
| Có cập nhật 10 lần/tháng nếu cài từ Store |   |   |

# 3. Phân biệt
## 3.1 Report và Dashboard
| **Reports**                                                                                      | **Dashboards**                                                                                           |
|--------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| Một tài liệu gồm một hoặc nhiều trang, mỗi trang có một hoặc nhiều hình ảnh                    | Một tài liệu một trang với nhiều hình ảnh lấy từ một hoặc nhiều báo cáo                                 |
| Thường được tạo trong Power BI Desktop, nhưng cũng có thể tạo trong Power BI Service           | Chỉ tạo được trong Power BI Service                                                                      |
| Luôn được hỗ trợ bởi mô hình dữ liệu                                                            | Hình ảnh "gắn" vào dashboard không tương tác với nhau như trên báo cáo (trừ 1 ngoại lệ)                  |
| Thường bao gồm một chủ đề cụ thể                                                                 | Có thể chứa nội dung truyền trực tuyến (ví dụ: dữ liệu IoT)                                              |
| Cho phép người dùng lọc báo cáo theo hình ảnh một cách chủ động                                 | Tốt nhất cho việc cung cấp thông tin nhanh chóng ("information at a glance")                            |

- **Lựa chọn Báo cáo hay Bảng điều khiển:** Phụ thuộc vào nhu cầu. Nếu cần khả năng lọc và tương tác chủ động, chọn báo cáo. Nếu cần cái nhìn tổng quan nhanh chóng và không cần tương tác, chọn bảng điều khiển.

## 3.2 Workspaces, My workspace, và Apps
| **Workspace**                                                                                                                   | **My Workspace**                                                                                             | **App**                                                                                                                           |
|----------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Khu vực cộng tác giữa các thành viên trong Power BI Service                                                                     | Khu vực thử nghiệm cá nhân để xuất bản và thử tính năng Service                                              | Phương tiện để phân phối báo cáo và dashboard trong Power BI Service                                                              |
| Được tạo bởi Admin (doanh nghiệp hoặc IT)                                                                                        | Không nên xuất bản nội dung muốn chia sẻ tại đây                                                              | Không giống app di động – là một "tạp chí" nội dung được chọn lọc và phân phối định kỳ                                            |
| Chỉ hiển thị khi được thêm vào với tư cách thành viên                                                                            | Dùng để cá nhân test các tính năng Power BI                                                                   | Gắn một-một với một workspace cụ thể                                                                                                |
| Có 4 cấp thành viên: Admin, Member, Contributor, Viewer                                                                          | Không dùng để chia sẻ nội dung với người khác                                                                 | Cần quyền đặc biệt trong workspace để tạo và cập nhật app                                                                          |
| - Admin: kiểm soát hoàn toàn                                                                                                     |                                                                                                               | Có thể chứa: báo cáo, bảng điều khiển, nội dung Excel                                                                              |
| - Member: tạo, sửa, xóa, thêm thành viên, quyết định nội dung App                                                               |                                                                                                               |                                                                                                                                    |
| - Contributor: tạo, sửa, xóa nội dung                                                                                            |                                                                                                               |                                                                                                                                    |
| - Viewer: chỉ được xem nội dung                                                                                                  |                                                                                                               |                                                                                                                                    |


# 4. Cấp phép (Licensing)
- Có thể sử dụng bộ công cụ với giấy phép miễn phí, nhưng bị hạn chế khả năng (đặc biệt là không có quyền truy cập vào Workspaces).
- Để sử dụng Power BI trong môi trường làm việc, cần giấy phép Pro (hoặc dùng thử).
- Cần đăng ký giấy phép Power BI Pro dùng thử 60 ngày để truy cập toàn bộ hệ sinh thái Power BI.
**Lưu ý:** Không thể đăng ký giấy phép dùng thử bằng địa chỉ email tiêu dùng (Gmail, Yahoo, AOL). Cần sử dụng email liên quan đến công việc.
  
# 5. Ngôn ngữ Power BI
- Có hai ngôn ngữ được sử dụng trong hệ sinh thái Power BI: M và DAX (Data Analysis Expressions).
- Không cần phải là chuyên gia về cả hai cho kỳ thi, nhưng cần làm quen với các hàm và cú pháp cơ bản của cả DAX và M.
- Sách sẽ đề cập đến các kiến thức cơ bản về M trong Chương 4 và DAX trong Chương 6 và 7.
# 6. Luyện tập trước PL-300
- Nếu chưa quen với các kỹ thuật hoặc tính năng được đề cập, cách tốt nhất là luyện tập.
- Thách thức lớn nhất là tìm bộ dữ liệu dễ sử dụng. Microsoft cung cấp một số bộ dữ liệu mẫu.
  + Tệp Excel và CSV Northwind:Dễ sử dụng, quen thuộc với hầu hết người dùng doanh nghiệp.
  + Dữ liệu giả lập, an toàn để sử dụng.
  + Có thể xem trước dữ liệu và tính toán kết quả bằng công thức Excel để kiểm tra mã DAX.
  + Nhược điểm: bộ dữ liệu nhỏ với số lượng trường hạn chế.
- Có sẵn trên GitHub: https://github.com/graphql-compose/graphql-compose-examples/tree/master/examples/northwind/data/csv
  + **Cơ sở dữ liệu AdventureWorks:** Bộ dữ liệu mạnh mẽ (và thực tế) hơn.
  + AdventureWorks DW là phổ biến nhất, ngoài ra còn có Tailwind Toys.
  + Có sẵn dưới dạng tệp BAK, có thể được sử dụng để khôi phục cơ sở dữ liệu trên thiết bị cục bộ.
- Quy trình sử dụng AdventureWorks DW (đối với người không có kiến thức về cơ sở dữ liệu):
  + Bước 1: Tải tệp BAK.
  + Bước 2: Cài đặt SQL Server Management Studio (SSMS) (miễn phí).
  + Bước 3: Cài đặt Microsoft SQL Server trên thiết bị cục bộ để lưu trữ cơ sở dữ liệu, HOẶC thiết lập tài khoản Azure AD và sử dụng tùy chọn Azure SQL Server (cần kết nối Internet và lưu ý chi phí).
  + Bước 4: Sử dụng SSMS để khôi phục cơ sở dữ liệu từ tệp BAK (cần tham khảo hướng dẫn chi tiết của Microsoft).
  + Bước 5: Sử dụng thông tin đăng nhập đã thiết lập cho cơ sở dữ liệu để kết nối từ Power BI Desktop.
# 7. Nội dung sách (Cách tiếp cận)
- Sách giải thích một tính năng ("what is") và tại sao lại quan trọng để hiểu nó ("why").
- Bao gồm các tính năng và khái niệm được coi là quan trọng cho một người thực hành Power BI toàn diện, ngay cả khi chúng không xuất hiện trực tiếp trong kỳ thi PL-300.
- Không đi sâu vào chi tiết "how-to" vì tính năng trong Power BI thay đổi liên tục.
- Cung cấp lộ trình để biết "what to study and why".
