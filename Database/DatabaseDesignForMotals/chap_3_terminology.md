# CHƯƠNG 3: TERMINOLOGY (THUẬT NGỮ)

## Tại sao thuật ngữ quan trọng?

Ba lý do chính khiến việc học các thuật ngữ này quan trọng:

1. **Diễn đạt các khái niệm đặc biệt**: Các thuật ngữ được sử dụng để diễn đạt và định nghĩa các ý tưởng và khái niệm đặc biệt của mô hình cơ sở dữ liệu quan hệ (relational database model)
2. **Mô tả quy trình thiết kế**: Được sử dụng để diễn đạt và định nghĩa chính quy trình thiết kế cơ sở dữ liệu
3. **Sử dụng rộng rãi**: Xuất hiện ở bất cứ đâu có thảo luận về cơ sở dữ liệu quan hệ hoặc RDBMS (tài liệu hướng dẫn phần mềm, tài liệu giáo dục, sách về CSDL, website)

---

## 1. VALUE-RELATED TERMS (Thuật ngữ liên quan đến giá trị)

### Data (Dữ liệu)
- Là các giá trị thô, chưa được xử lý
- Ví dụ: tên, số điện thoại, địa chỉ đơn lẻ

### Information (Thông tin)
- Là dữ liệu đã được xử lý và có ý nghĩa
- Dữ liệu trở thành thông tin khi được tổ chức và trình bày theo cách có ý nghĩa
- **Sự khác biệt giữa Data và Information rất quan trọng** để hiểu quy trình thiết kế CSDL

### Null
**Định nghĩa:**
- Đại diện cho giá trị **missing** (thiếu) hoặc **unknown** (không biết)
- KHÔNG phải là số 0 hoặc chuỗi rỗng

**Khi nào sử dụng Null:**
- Giá trị hiện không xác định
- Giá trị chưa có sẵn tại thời điểm nhập liệu
- Trường không áp dụng cho record cụ thể

**Nhược điểm chính của Null:**
- Gây khó khăn trong tính toán và so sánh
- Có thể dẫn đến kết quả không chính xác trong truy vấn
- Ảnh hưởng tiêu cực đến tính toàn vẹn dữ liệu (data integrity)
- Gây ra **undetected error** (lỗi không phát hiện được)

---

## 2. STRUCTURE-RELATED TERMS (Thuật ngữ liên quan đến cấu trúc)

### Table (Bảng)
- Là **cấu trúc chính** trong CSDL
- Luôn đại diện cho một **chủ đề duy nhất và cụ thể**
- Được cấu tạo từ **fields** (trường) và **records** (bản ghi)

**Ba loại bảng:**
1. **Data Table** (Bảng dữ liệu): Lưu trữ dữ liệu để cung cấp thông tin - loại phổ biến nhất
2. **Linking Table** (Bảng liên kết): Thiết lập mối quan hệ many-to-many giữa các bảng
3. **Subset Table** (Bảng con): Đại diện cho chủ đề phụ của một data table cụ thể

### Field (Trường)
- Đại diện cho một **đặc điểm** của chủ đề mà bảng đại diện
- Là cấu trúc nhỏ nhất chứa dữ liệu trong CSDL
- Mỗi field nên lưu trữ **một giá trị duy nhất**

### Record (Bản ghi)
- Là một tập hợp các giá trị field hoàn chỉnh
- Mô tả một **instance** (thực thể) của chủ đề mà bảng đại diện
- Mỗi record trong bảng phải là **duy nhất**

### View (Khung nhìn)
- Là một **virtual table** (bảng ảo)
- Được tạo từ fields và records của một hoặc nhiều base tables
- **Không chứa dữ liệu** - chỉ trình bày dữ liệu từ các base tables
- Sử dụng để:
    - Làm việc với dữ liệu từ nhiều bảng đồng thời
    - Đơn giản hóa truy vấn phức tạp
    - Bảo mật dữ liệu

### Keys (Khóa)

**Candidate Key (Khóa ứng viên):**
- Field hoặc tập hợp fields có thể xác định duy nhất một record
- Phải tuân theo **Elements of a Candidate Key**

**Primary Key (Khóa chính):**
- Là candidate key được chọn để xác định chính thức mỗi record
- **Quan trọng nhất** trong tất cả các loại keys
- Phải tuân theo **Elements of a Primary Key**:
    - Không thể chứa Null
    - Phải duy nhất
    - Không thể thay đổi
    - Xác định độc quyền từng record

**Alternate Key (Khóa thay thế):**
- Là các candidate keys không được chọn làm primary key
- Cung cấp phương thức thay thế để xác định record

**Foreign Key (Khóa ngoại):**
- Field trong một bảng lưu trữ giá trị primary key từ bảng khác
- Được sử dụng để **thiết lập mối quan hệ** giữa hai bảng

### Index (Chỉ mục)
- Là một **software device** (thiết bị phần mềm) được sử dụng để tối ưu hóa xử lý dữ liệu
- **Khác với key**: Key xác định record, Index tối ưu hóa hiệu suất
- Được lưu trữ dưới dạng file trên đĩa

---

## 3. RELATIONSHIP-RELATED TERMS (Thuật ngữ liên quan đến mối quan hệ)

### Relationship (Mối quan hệ)
- Là **connection** (kết nối) giữa một cặp bảng
- Được sử dụng để:
    - Đảm bảo các khía cạnh của data integrity
    - Cho phép view kéo dữ liệu từ nhiều bảng

### Ba loại mối quan hệ:

**1. One-to-One (1:1)**
- Một record trong Table A liên quan đến **chỉ một** record trong Table B
- Và ngược lại
- Ví dụ: Nhân viên - Chỗ đỗ xe (mỗi nhân viên có một chỗ đỗ xe riêng)

**2. One-to-Many (1:M)**
- Một record trong Table A có thể liên quan đến **một hoặc nhiều** records trong Table B
- Nhưng một record trong Table B chỉ liên quan đến **một** record trong Table A
- **Loại phổ biến nhất** trong CSDL quan hệ
- Ví dụ: Khách hàng - Đơn hàng (một khách hàng có nhiều đơn hàng)

**3. Many-to-Many (M:N)**
- Một record trong Table A có thể liên quan đến **một hoặc nhiều** records trong Table B
- Và ngược lại
- **Phải được giải quyết** bằng cách tạo **linking table** (bảng liên kết)
- Ví dụ: Sinh viên - Lớp học (một sinh viên có nhiều lớp, một lớp có nhiều sinh viên)

### Ba đặc điểm của mối quan hệ:

**1. Type of Relationship (Loại mối quan hệ)**
- One-to-One, One-to-Many, hoặc Many-to-Many

**2. Type of Participation (Loại tham gia)**
- **Mandatory (Bắt buộc)**: Bảng PHẢI tham gia vào mối quan hệ
- **Optional (Tùy chọn)**: Bảng CÓ THỂ tham gia vào mối quan hệ

**3. Degree of Participation (Mức độ tham gia)**
- Số lượng **tối thiểu** và **tối đa** records mà một bảng có thể liên kết với một record trong bảng liên quan

### Self-Referencing Relationship
- Mối quan hệ tồn tại giữa các records **trong cùng một bảng**
- Có thể là One-to-One, One-to-Many, hoặc Many-to-Many
- Ví dụ: Bảng Nhân viên (nhân viên - người quản lý cũng là nhân viên)

---

## 4. INTEGRITY-RELATED TERMS (Thuật ngữ liên quan đến tính toàn vẹn)

### Field Specification (Đặc tả trường)
- Thiết lập các đặc điểm **general** (chung), **physical** (vật lý), và **logical** (logic) của field

**Ba loại elements:**

1. **General Elements** (Yếu tố chung):
    - Field Name (tên trường)
    - Description (mô tả)
    - Parent Table (bảng chứa)

2. **Physical Elements** (Yếu tố vật lý):
    - Data Type (kiểu dữ liệu)
    - Length (độ dài)
    - Character Support (hỗ trợ ký tự)

3. **Logical Elements** (Yếu tố logic):
    - Required Value (giá trị bắt buộc)
    - Range of Values (phạm vi giá trị)
    - Null Support (hỗ trợ Null)

### Data Integrity (Tính toàn vẹn dữ liệu)

**Định nghĩa:**
- Đề cập đến **validity** (tính hợp lệ), **consistency** (tính nhất quán), và **accuracy** (tính chính xác) của dữ liệu trong CSDL

**Tầm quan trọng:**
> Mức độ chính xác của thông tin bạn truy xuất từ CSDL tỷ lệ thuận trực tiếp với mức độ data integrity bạn áp dụng lên CSDL

**Bốn loại Data Integrity:**

**1. Table-Level Integrity (Entity Integrity)**
- Đảm bảo:
    - Không có duplicate records (bản ghi trùng lặp)
    - Field xác định mỗi record (primary key) là duy nhất và không bao giờ Null
    - Mỗi record được xác định bởi primary key value

**2. Field-Level Integrity (Domain Integrity)**
- Đảm bảo:
    - Cấu trúc của mỗi field là vững chắc
    - Giá trị trong mỗi field là hợp lệ, nhất quán và chính xác
    - Fields cùng loại được định nghĩa nhất quán trong toàn bộ CSDL

**3. Relationship-Level Integrity (Referential Integrity)**
- Đảm bảo:
    - Mối quan hệ giữa cặp bảng là vững chắc
    - Records trong các bảng được **synchronized** (đồng bộ) khi dữ liệu được nhập, cập nhật hoặc xóa

**4. Business Rules**
- Áp dụng **restrictions** (hạn chế) hoặc **limitations** (giới hạn) dựa trên cách tổ chức nhìn nhận và sử dụng dữ liệu
- Ảnh hưởng đến:
    - Phạm vi và loại giá trị lưu trong field
    - Type of participation và degree of participation
    - Loại đồng bộ hóa cho relationship-level integrity

---

## CÁC ĐIỂM QUAN TRỌNG CẦN NHỚ

### 📌 **Sự khác biệt Data vs Information**
- Data là giá trị thô → Information là data đã được xử lý có ý nghĩa
- Hiểu sự khác biệt này là **cực kỳ quan trọng** cho quy trình thiết kế

### 📌 **Null - Vấn đề cần cẩn trọng**
- Null ≠ 0 và ≠ chuỗi rỗng
- Sử dụng Null có thể gây lỗi không phát hiện được
- Cần hạn chế sử dụng Null khi có thể

### 📌 **Ba cấu trúc chính: Fields, Records, Tables**
- Table là cấu trúc chính
- Field là cấu trúc nhỏ nhất
- Record là tập hợp các field values

### 📌 **Primary Key là quan trọng nhất**
- Xác định duy nhất mỗi record
- Không được chứa Null
- Không thể thay đổi

### 📌 **One-to-Many là loại quan hệ phổ biến nhất**
- Many-to-Many phải được giải quyết bằng linking table

### 📌 **Data Integrity là khía cạnh quan trọng nhất**
- Bốn loại: Table-level, Field-level, Relationship-level, Business Rules
- Đảm bảo tính chính xác của thông tin truy xuất

---

## CÂU HỎI ÔN TẬP VÀ TRẢ LỜI (Review Questions & Answers)

### 1. Why is terminology important? (Tại sao thuật ngữ quan trọng?)

**Trả lời:**
Thuật ngữ quan trọng vì ba lý do chính:
- Chúng được sử dụng để diễn đạt và định nghĩa các ý tưởng và khái niệm đặc biệt của mô hình cơ sở dữ liệu quan hệ (nhiều thuật ngữ bắt nguồn từ toán học: set theory và first-order predicate logic)
- Chúng được sử dụng để diễn đạt và định nghĩa chính quy trình thiết kế cơ sở dữ liệu
- Chúng được sử dụng ở bất cứ đâu có thảo luận về CSDL quan hệ hoặc RDBMS (trong tài liệu hướng dẫn, khóa học, sách, website)

---

### 2. Name the four categories of terms. (Kể tên 4 loại thuật ngữ)

**Trả lời:**
Bốn loại thuật ngữ là:
1. **Value-Related Terms** (Thuật ngữ liên quan đến giá trị)
2. **Structure-Related Terms** (Thuật ngữ liên quan đến cấu trúc)
3. **Relationship-Related Terms** (Thuật ngữ liên quan đến mối quan hệ)
4. **Integrity-Related Terms** (Thuật ngữ liên quan đến tính toàn vẹn)

---

### 3. What is the difference between data and information? (Sự khác biệt giữa data và information?)

**Trả lời:**
- **Data (Dữ liệu)**: Là các giá trị thô, chưa được xử lý mà bạn lưu trữ trong cơ sở dữ liệu
- **Information (Thông tin)**: Là dữ liệu đã được xử lý theo cách làm cho nó có ý nghĩa và hữu ích khi bạn làm việc với nó hoặc xem nó

**Ví dụ:** Các số điện thoại đơn lẻ là data, nhưng khi được tổ chức thành danh bạ điện thoại theo tên và phòng ban thì trở thành information.

---

### 4. What does Null represent? (Null đại diện cho gì?)

**Trả lời:**
Null đại diện cho một giá trị **missing** (thiếu) hoặc **unknown** (không xác định).

**Lưu ý quan trọng:**
- Null ≠ 0 (số không)
- Null ≠ chuỗi rỗng (empty string)
- Null ≠ khoảng trắng (spaces)

---

### 5. What is the major disadvantage of Null? (Nhược điểm chính của Null?)

**Trả lời:**
Nhược điểm chính của Null là nó có **tác động tiêu cực đến các phép toán** (mathematical operations).

**Chi tiết:**
- Bất kỳ phép tính số học nào có chứa Null sẽ cho kết quả là Null
- Điều này có thể dẫn đến **undetected errors** (lỗi không phát hiện được)
- Gây khó khăn trong việc so sánh và tính toán
- Ảnh hưởng đến độ chính xác của thông tin truy xuất từ CSDL

**Ví dụ:** 100 + Null = Null (không phải 100)

---

### 6. What are the chief structures in the database? (Các cấu trúc chính trong CSDL?)

**Trả lời:**
**Tables (Bảng)** là cấu trúc chính trong cơ sở dữ liệu.

**Bổ sung:** Các cấu trúc cốt lõi khác bao gồm:
- **Fields** (Trường): Cấu trúc nhỏ nhất chứa dữ liệu
- **Records** (Bản ghi): Tập hợp các field values
- **Views** (Khung nhìn): Virtual tables được tạo từ base tables

---

### 7. Name the three types of tables. (Ba loại bảng?)

**Trả lời:**
Ba loại bảng là:

1. **Data Tables** (Bảng dữ liệu): Lưu trữ dữ liệu để cung cấp thông tin - loại phổ biến nhất
2. **Linking Tables** (Bảng liên kết): Thiết lập mối quan hệ many-to-many giữa các bảng
3. **Validation Tables** (Bảng kiểm tra): Chứa dữ liệu dùng để xác thực giá trị trong các bảng khác

**Lưu ý:** Subset Tables (Bảng con) là loại bảng đặc biệt đại diện cho chủ đề phụ của một data table.

---

### 8. What is a view? (View là gì?)

**Trả lời:**
View là một **virtual table** (bảng ảo) được tạo thành từ các fields và records của một hoặc nhiều base tables trong cơ sở dữ liệu.

**Đặc điểm quan trọng:**
- View **không chứa dữ liệu** của riêng nó
- Chỉ trình bày dữ liệu từ các base tables
- Được sử dụng để làm việc với dữ liệu từ nhiều bảng đồng thời
- Giúp đơn giản hóa truy vấn phức tạp

---

### 9. State the difference between a key and an index. (Sự khác biệt giữa key và index?)

**Trả lời:**
- **Key (Khóa)**: Là một **logical structure** (cấu trúc logic) mà bạn sử dụng để xác định các records trong một bảng
- **Index (Chỉ mục)**: Là một **physical structure** (cấu trúc vật lý) mà bạn sử dụng để tối ưu hóa việc xử lý dữ liệu

**Khác biệt chính:**
- Key: Phục vụ mục đích **identification** (xác định)
- Index: Phục vụ mục đích **optimization** (tối ưu hóa)
- Index là một software device được lưu trữ dưới dạng file trên đĩa

---

### 10. What are the three types of relationships that can exist between a pair of tables? (Ba loại mối quan hệ?)

**Trả lời:**
Ba loại mối quan hệ có thể tồn tại giữa một cặp bảng là:

1. **One-to-One (1:1)**: Một record trong bảng A liên quan đến chỉ một record trong bảng B và ngược lại
2. **One-to-Many (1:M)**: Một record trong bảng A có thể liên quan đến một hoặc nhiều records trong bảng B, nhưng một record trong bảng B chỉ liên quan đến một record trong bảng A (loại phổ biến nhất)
3. **Many-to-Many (M:N)**: Một record trong bảng A có thể liên quan đến một hoặc nhiều records trong bảng B và ngược lại

---

### 11. What are the three ways in which you can characterize a relationship? (Ba cách đặc trưng hóa mối quan hệ?)

**Trả lời:**
Bạn có thể đặc trưng hóa mỗi mối quan hệ theo ba cách:

1. **Type of Relationship** (Loại mối quan hệ): Loại mối quan hệ tồn tại giữa các bảng (One-to-One, One-to-Many, hoặc Many-to-Many)

2. **Type of Participation** (Loại tham gia): Cách thức mà mỗi bảng tham gia vào mối quan hệ
    - **Mandatory** (Bắt buộc): Bảng phải tham gia
    - **Optional** (Tùy chọn): Bảng có thể tham gia

3. **Degree of Participation** (Mức độ tham gia): Số lượng tối thiểu và tối đa records mà một bảng có thể liên kết với một record trong bảng liên quan

---

### 12. What is a field specification? (Field specification là gì?)

**Trả lời:**
Field specification đại diện cho **tất cả các elements** (yếu tố) của một field. Nó thiết lập các đặc điểm general (chung), physical (vật lý), và logical (logic) của field - những đặc điểm này là một phần không thể thiếu của mỗi field trong cơ sở dữ liệu.

**Mục đích:**
- Xác định cấu trúc của field
- Định nghĩa loại dữ liệu và giới hạn
- Đảm bảo tính toàn vẹn dữ liệu cấp field

---

### 13. What three types of elements does a field specification incorporate? (Ba loại elements trong field specification?)

**Trả lời:**
Field specification bao gồm ba loại elements sau:

1. **General Elements** (Yếu tố chung):
    - Thông tin cơ bản nhất về field
    - Bao gồm: Field Name, Description, Parent Table

2. **Physical Elements** (Yếu tố vật lý):
    - Xác định cách field được xây dựng và cách nó được biểu diễn
    - Bao gồm: Data Type, Length, Character Support

3. **Logical Elements** (Yếu tố logic):
    - Mô tả các giá trị được lưu trữ trong field
    - Bao gồm: Required Value, Range of Values, Null Support

---

### 14. What is data integrity? (Data integrity là gì?)

**Trả lời:**
Data integrity đề cập đến **validity** (tính hợp lệ), **consistency** (tính nhất quán), và **accuracy** (tính chính xác) của dữ liệu trong cơ sở dữ liệu.

**Tầm quan trọng:**
> Mức độ chính xác của thông tin bạn truy xuất từ CSDL tỷ lệ thuận trực tiếp với mức độ data integrity bạn áp dụng lên CSDL.

Data integrity là một trong những khía cạnh **quan trọng nhất** của quy trình thiết kế cơ sở dữ liệu và không thể bị đánh giá thấp, bỏ qua hoặc xem nhẹ.

---

### 15. Name the four types of data integrity. (Bốn loại data integrity?)

**Trả lời:**
Bốn loại data integrity là:

1. **Table-Level Integrity** (Entity Integrity):
    - Đảm bảo không có duplicate records
    - Primary key xác định độc quyền mỗi record
    - Primary key values là duy nhất và không bao giờ Null

2. **Field-Level Integrity** (Domain Integrity):
    - Đảm bảo cấu trúc của mỗi field là vững chắc
    - Giá trị trong mỗi field là hợp lệ, nhất quán và chính xác
    - Fields cùng loại được định nghĩa nhất quán trong toàn bộ CSDL

3. **Relationship-Level Integrity** (Referential Integrity):
    - Đảm bảo mối quan hệ giữa các bảng là vững chắc
    - Records được đồng bộ khi dữ liệu được thêm, cập nhật hoặc xóa

4. **Business Rules**:
    - Áp dụng các hạn chế hoặc giới hạn dựa trên cách tổ chức nhìn nhận và sử dụng dữ liệu
    - Ảnh hưởng đến phạm vi giá trị, participation, và các quy tắc đồng bộ hóa

---

**Lưu ý:** Chương 3 cung cấp nền tảng thuật ngữ cần thiết trước khi bắt đầu quy trình thiết kế CSDL. Việc nắm vững các thuật ngữ này sẽ giúp hiểu rõ hơn các chương tiếp theo trong quy trình thiết kế.