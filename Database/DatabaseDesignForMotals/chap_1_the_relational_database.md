# CHƯƠNG 1: RELATIONAL DATABASE (CƠ SỞ DỮ LIỆU QUAN HỆ)

## Các chủ đề được đề cập trong chương này
- Database là gì?
- Relational Database (Cơ sở dữ liệu quan hệ)
- Truy xuất dữ liệu
- Lợi ích của Relational Database
- Relational Database Management Systems (RDBMS)
- Tương lai của Relational Database

---

## 1. DATABASE LÀ GÌ?

### Định nghĩa
**Database (Cơ sở dữ liệu)** là một tập hợp dữ liệu được tổ chức có mục đích mô hình hóa một tổ chức hoặc quy trình tổ chức nào đó.

- Dù bạn sử dụng spreadsheet hay ứng dụng cơ sở dữ liệu trên máy tính, miễn là bạn thu thập dữ liệu một cách có tổ chức cho một mục đích cụ thể, bạn đã có một database.

### Hai loại Database chính

#### 1.1. Operational Databases (Cơ sở dữ liệu vận hành)
- **Mục đích**: Được sử dụng trong xử lý giao dịch trực tuyến (OLTP - Online Transaction Processing)
- **Đặc điểm**:
    - Dữ liệu **động** (dynamic) - thay đổi liên tục
    - Phản ánh thông tin cập nhật theo thời gian thực
    - Thu thập, sửa đổi và duy trì dữ liệu hàng ngày
- **Ví dụ sử dụng**:
    - Cửa hàng bán lẻ
    - Công ty sản xuất
    - Bệnh viện và phòng khám
    - Nhà xuất bản

#### 1.2. Analytical Databases (Cơ sở dữ liệu phân tích)
- **Mục đích**: Được sử dụng trong xử lý phân tích trực tuyến (OLAP - Online Analytical Processing)
- **Đặc điểm**:
    - Dữ liệu **tĩnh** (static) - không bao giờ hoặc rất hiếm khi được sửa đổi
    - Lưu trữ và theo dõi dữ liệu lịch sử và phụ thuộc thời gian
    - Phản ánh snapshot của dữ liệu tại một thời điểm cụ thể
- **Ứng dụng**:
    - Theo dõi xu hướng
    - Xem dữ liệu thống kê trong thời gian dài
    - Dự báo kinh doanh chiến lược hoặc chiến thuật
- **Ví dụ sử dụng**:
    - Phòng thí nghiệm hóa học
    - Công ty địa chất
    - Công ty phân tích marketing

**Lưu ý**: Cuốn sách này tập trung vào thiết kế **Operational Database** vì đây vẫn là loại cơ sở dữ liệu được sử dụng phổ biến nhất trên thế giới.

---

## 2. RELATIONAL DATABASE (CƠ SỞ DỮ LIỆU QUAN HỆ)

### Lịch sử và nguồn gốc

#### 2.1. Người sáng lập
- **Cha đẻ của mô hình quan hệ**: Tiến sĩ Edgar F. Codd
- **Thời gian**: Được hình thành vào năm 1969
- **Bối cảnh**:
    - Codd là nhà nghiên cứu của IBM vào cuối những năm 1960
    - Không hài lòng với các mô hình và sản phẩm cơ sở dữ liệu thời bấy giờ
    - Muốn áp dụng toán học để giải quyết các vấn đề về dữ liệu

#### 2.2. Công trình nổi tiếng
- **Tên bài báo**: "A Relational Model of Data for Large Shared Databanks"
- **Thời gian xuất bản**: Tháng 6 năm 1970
- **Nền tảng toán học**:
    - Set Theory (Lý thuyết tập hợp)
    - First-order Predicate Logic (Logic vị từ bậc nhất)

#### 2.3. Nguồn gốc tên gọi
- Tên "relational" xuất phát từ thuật ngữ **"relation"** trong lý thuyết tập hợp
- **Quan niệm sai lầm phổ biến**: Nhiều người nghĩ tên gọi xuất phát từ việc các bảng có thể "liên quan" (related) với nhau

### Cấu trúc của Relational Database

#### 2.4. Các thành phần chính
1. **Relations (Quan hệ)** - người dùng nhìn thấy dưới dạng **Tables (Bảng)**
2. **Tuples (Bộ)** - người dùng gọi là **Records (Bản ghi)**
3. **Attributes (Thuộc tính)** - người dùng gọi là **Fields (Trường)**

#### 2.5. Đặc điểm quan trọng
- Thứ tự vật lý của records hoặc fields trong bảng **hoàn toàn không quan trọng**
- Mỗi record trong bảng được xác định bằng một field chứa **giá trị duy nhất** (unique value)

---

## 3. TRUY XUẤT DỮ LIỆU (RETRIEVING DATA)

### 3.1. Structured Query Language (SQL)
- Ngôn ngữ chuẩn để truy vấn và thao tác dữ liệu trong relational database
- Cho phép người dùng truy xuất dữ liệu từ một hoặc nhiều bảng

### 3.2. Ví dụ câu lệnh SQL cơ bản
```sql
SELECT field_name(s)
FROM table_name(s)
WHERE condition(s)
```

---

## 4. LỢI ÍCH CỦA RELATIONAL DATABASE

### 4.1. Multilevel Data Integrity (Tính toàn vẹn dữ liệu đa cấp)
Relational database cung cấp nhiều cấp độ bảo vệ tính toàn vẹn dữ liệu:
- **Table-level integrity** (Toàn vẹn cấp bảng)
- **Field-level integrity** (Toàn vẹn cấp trường)
- **Relationship-level integrity** (Toàn vẹn cấp mối quan hệ)
- **Business rules** (Quy tắc nghiệp vụ)

### 4.2. Logical and Physical Data Independence
- **Physical Data Independence**: Các thay đổi trong cách triển khai vật lý của database không ảnh hưởng đến ứng dụng
- Người dùng làm việc với cấu trúc logic, không cần quan tâm đến cách dữ liệu được lưu trữ vật lý

### 4.3. Guaranteed Data Consistency and Accuracy
- Dữ liệu nhất quán và chính xác trên toàn bộ database
- Tránh redundant data (dữ liệu dư thừa) và duplicate data (dữ liệu trùng lặp)

### 4.4. Easy Data Retrieval
- Dễ dàng truy xuất dữ liệu bằng SQL
- Có thể kết hợp dữ liệu từ nhiều bảng

---

## 5. RELATIONAL DATABASE MANAGEMENT SYSTEMS (RDBMS)

### 5.1. Định nghĩa
**RDBMS** là phần mềm quản lý cơ sở dữ liệu quan hệ, cung cấp:
- Công cụ để tạo, quản lý và bảo trì database
- Giao diện để người dùng tương tác với dữ liệu
- Các tính năng bảo mật và backup

### 5.2. Các RDBMS phổ biến
- **Oracle Database**
- **Microsoft SQL Server**
- **MySQL**
- **PostgreSQL**
- **IBM DB2**
- **Microsoft Access** (cho ứng dụng nhỏ)

---

## 6. TƯƠNG LAI CỦA RELATIONAL DATABASE (WHAT'S NEXT?)

### 6.1. Tình trạng hiện tại (2020 - 2025)
- Relational database đã tồn tại được **50 năm** (kể từ 1970)
- Vẫn là loại database được sử dụng rộng rãi nhất
- Là ngành công nghiệp hàng tỷ đô la
- Là phần thiết yếu trong cuộc sống hàng ngày của chúng ta

### 6.2. Ứng dụng trong thực tế
Chúng ta sử dụng relational database mỗi khi:
- Mua hàng online hoặc tại cửa hàng địa phương
- Lên kế hoạch du lịch online hoặc với đại lý du lịch
- Mượn sách tại thư viện
- Đặt đồ ăn bằng app trên thiết bị di động

### 6.3. Xu hướng mới
- **NoSQL databases** (như MongoDB) đang phát triển cho các ứng dụng đặc biệt
- Tuy nhiên, relational database vẫn đứng vững và tiếp tục phát triển
- Đã "weathered changes" (trải qua nhiều thay đổi) và "stood the test of time" (đứng vững qua thử thách thời gian)

---

## 7. CÁC VẤN ĐỀ CẦN TRÁNH (BAD DESIGN)

### 7.1. Flat-File Design (Thiết kế phẳng)
**Định nghĩa**: Còn gọi là thiết kế "ném mọi thứ vào một bảng lớn"

**Các vấn đề**:
- Multipart fields (trường đa phần)
- Calculated fields (trường tính toán)
- Unnecessary duplicate fields (trường trùng lặp không cần thiết)
- Không có primary key thực sự
- Bảng đại diện nhiều hơn một chủ đề
- Dữ liệu dư thừa và không nhất quán

### 7.2. Spreadsheet Design (Thiết kế kiểu bảng tính)
**Vấn đề**: Nhiều người cố gắng thiết kế database giống như spreadsheet
- Dẫn đến cấu trúc kém hiệu quả
- Vi phạm các nguyên tắc thiết kế database

### 7.3. Design Based on RDBMS Capability
**Vấn đề**: Thiết kế database dựa trên khả năng của phần mềm cụ thể
- Nên thiết kế logic trước, sau đó mới implement trên phần mềm cụ thể

---

## 8. TẦM QUAN TRỌNG CỦA THIẾT KẾ TỐT

### 8.1. Tại sao phải quan tâm đến Database Design?
- **Tránh dữ liệu không nhất quán** (inconsistent data)
- **Tránh thông tin không chính xác** (inaccurate information)
- **Thiết kế kém** là nguyên nhân gốc rễ của các vấn đề về dữ liệu

### 8.2. Quy tắc quan trọng
> **Không áp dụng cấu trúc database hiện tại làm cơ sở cho database mới**

Ngay cả khi database hiện tại có vẻ không tệ, bạn vẫn cần phân tích kỹ và thiết kế lại đúng cách.

---

## 9. CÁC THUẬT NGỮ QUAN TRỌNG CẦN NHỚ

### 9.1. Thuật ngữ cơ bản
- **Table** (Bảng): Relation trong lý thuyết
- **Record** (Bản ghi): Tuple trong lý thuyết
- **Field** (Trường): Attribute trong lý thuyết
- **Primary Key**: Trường hoặc nhóm trường xác định duy nhất mỗi record
- **Foreign Key**: Trường trong một bảng tham chiếu đến primary key của bảng khác

### 9.2. Các loại giá trị
- **Null value**: Giá trị bị thiếu hoặc không xác định (KHÔNG phải zero hoặc chuỗi rỗng)
- **Unique value**: Giá trị duy nhất, không trùng lặp

---

## TÓM TẮT

Chương 1 giới thiệu những kiến thức nền tảng về Relational Database:

1. **Database** là tập hợp dữ liệu có tổ chức, chia thành hai loại chính: Operational (động) và Analytical (tĩnh)

2. **Relational Database** được Tiến sĩ Edgar F. Codd phát minh năm 1969-1970, dựa trên lý thuyết tập hợp và logic toán học

3. Cấu trúc gồm **Tables** (bảng), **Records** (bản ghi), và **Fields** (trường), với thứ tự vật lý không quan trọng

4. **Lợi ích chính**:
    - Tính toàn vẹn dữ liệu đa cấp
    - Độc lập logic và vật lý
    - Dữ liệu nhất quán và chính xác
    - Truy xuất dữ liệu dễ dàng

5. **RDBMS** là phần mềm quản lý relational database (Oracle, MySQL, SQL Server...)

6. Sau 50 năm, relational database vẫn là loại database phổ biến nhất và tiếp tục phát triển

7. **Thiết kế tốt** là then chốt - phải tránh các kiểu thiết kế kém như flat-file, spreadsheet design

---

## CÂU HỎI ÔN TẬP

1. Database là gì? Sự khác biệt giữa Operational và Analytical database?
2. Ai là cha đẻ của relational database model? Nền tảng toán học nào được sử dụng?
3. Các thành phần chính của relational database là gì?
4. Lợi ích chính của relational database là gì?
5. RDBMS là gì? Kể tên một số RDBMS phổ biến?
6. Tại sao thiết kế database quan trọng?
7. Các kiểu thiết kế kém cần tránh là gì?
8. Null value là gì và khi nào nên sử dụng?