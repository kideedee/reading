# 📚 CHƯƠNG 4: TỔNG QUAN QUY TRÌNH THIẾT KẾ DATABASE

> "I don't pretend to understand the Universe—it's a great deal bigger than I am." — Thomas Carlyle

## 🎯 MỤC TIÊU CHƯƠNG

Chương này cung cấp cái nhìn tổng quan về toàn bộ quy trình thiết kế database, giúp bạn hiểu được:
- Tầm quan trọng của việc hoàn thành đầy đủ design process
- 7 giai đoạn chính trong quy trình thiết kế database
- Mối liên kết giữa các giai đoạn với nhau

---

## 💡 TẦM QUAN TRỌNG CỦA VIỆC HOÀN THÀNH DESIGN PROCESS

### ⚠️ Tại sao phải hoàn thành đầy đủ quy trình?

**Câu trả lời ngắn gọn: LUÔN LUÔN CẦN THIẾT!** ✅

#### Các điểm quan trọng cần nhớ:

1. **Áp dụng cho mọi loại database**
   - Không phụ thuộc vào loại, kích thước hay mục đích của database
   - "Simple database" KHÔNG có nghĩa là có thể bỏ qua design process
   - Từ "simple" là một trong những từ nguy hiểm nhất trong database design

2. **Hậu quả của việc bỏ qua design process**
   - ❌ Poor database design
   - ❌ Improper design
   - ❌ Incomplete design = Poor design
   - ❌ Structural integrity và data integrity thấp

3. **Nguyên tắc quan trọng**
   > **Mức độ structural integrity và data integrity TỈ LỆ THUẬN với việc bạn tuân thủ design process nghiêm ngặt đến mức nào**

   ```
   Ít thời gian design = Nhiều rủi ro và vấn đề
   Đầy đủ design process = Database structure vững chắc + Data integrity tốt
   ```

4. **Lợi ích của việc theo đúng quy trình**
   - ✅ Đảm bảo sound structure
   - ✅ Đảm bảo data integrity
   - ✅ Dễ dàng implement trong RDBMS
   - ✅ Giảm thiểu vấn đề trong tương lai

> 💬 **Câu nói khôn ngoan**: "There's never time to do it right, but there's always time to do it over!"

---

## 🔄 7 GIAI ĐOẠN QUY TRÌNH THIẾT KẾ DATABASE

### **GIAI ĐOẠN 1: Định nghĩa Mission Statement và Mission Objectives**

#### 📝 Mission Statement (Tuyên bố sứ mệnh)

**Định nghĩa**: Xác định mục đích (purpose) của database

**Vai trò**:
- Cung cấp focus rõ ràng cho công việc thiết kế
- Đảm bảo database structure phù hợp với mục đích sử dụng
- Hướng dẫn việc thu thập dữ liệu cần thiết

**Người tham gia định nghĩa Mission Statement**:
1. Database developer (bạn)
2. Database owner (người sở hữu database)
3. Management personnel (người chịu trách nhiệm cuối cùng)

#### 🎯 Mission Objectives (Mục tiêu sứ mệnh)

**Định nghĩa**: Các statements đại diện cho general tasks mà users có thể thực hiện với dữ liệu trong database

**Vai trò**:
- Hỗ trợ mission statement
- Giúp xác định các khía cạnh khác nhau của database structure

**Người tham gia định nghĩa Mission Objectives**:
1. Database developer (bạn)
2. Management personnel
3. End users (người dùng cuối)

---

### **GIAI ĐOẠN 2: Phân tích Current Database**

#### 🔍 Mục đích

Xác định **data requirements** của tổ chức thông qua:
1. Review cách tổ chức thu thập và trình bày dữ liệu hiện tại
2. Conduct interviews với users và management

#### 📊 Các hoạt động chính

**1. Review cách thu thập dữ liệu (How data is collected)**
- Xem xét forms, documents hiện có
- Phân tích data entry methods

**2. Review cách trình bày thông tin (How information is presented)**
- Xem xét reports, displays hiện có
- Phân tích information output

**3. Conduct interviews**
- Với users: Hiểu cách họ sử dụng database hàng ngày
- Với management: Hiểu yêu cầu chiến lược

**4. Compile initial field list**
- Thu thập tất cả fields cần thiết
- Loại bỏ calculated fields → đặt vào list riêng (sẽ dùng sau)
- **Refined field list** = Fundamental data requirements của tổ chức

#### ✅ Kết thúc giai đoạn

- Gửi field list cho users và management review
- Khuyến khích feedback
- Xem xét modifications hợp lý
- Record list trong trạng thái hiện tại
- Chuyển sang giai đoạn tiếp theo

---

### **GIAI ĐOẠN 3: Tạo Data Structures**

#### 📋 Các hoạt động chính

**1. Define Tables (Định nghĩa bảng)**

**Nguồn xác định subjects cho tables**:
- Mission objectives (từ giai đoạn 1)
- Data requirements (từ giai đoạn 2)

**Quy trình**:
- Xác định subjects cần track
- Thiết lập subjects thành tables
- Associate tables với fields từ field list

**Review tables**:
- ✅ Mỗi table chỉ represent 1 subject duy nhất
- ✅ Không chứa duplicate fields

**2. Refine Fields (Tinh chỉnh fields)**

**Xử lý multipart/multivalued fields**:
- Đảm bảo mỗi field chỉ store 1 giá trị duy nhất
- Split fields nếu cần

**Clean up fields**:
- Move fields không represent distinct characteristics
- Delete fields không phù hợp

**3. Review và Refine Table Structures**

**Checklist**:
- [ ] Kiểm tra lại công việc trên fields
- [ ] Đảm bảo không bỏ sót gì
- [ ] Verify mỗi table structure được define properly

**4. Establish Keys (Thiết lập khóa)**

**Primary Key** (quan trọng nhất):
- Mỗi table phải có properly defined primary key
- **Vai trò**: Uniquely identifies mỗi record trong table

**5. Establish Field Specifications**

**Quy trình**:
- Conduct interviews với users và management
- Identify field characteristics quan trọng với họ
- Review và discuss các characteristics chưa quen thuộc
- Define và document specifications cho mỗi field

#### ✅ Kết thúc giai đoạn

Table structures đã sẵn sàng cho giai đoạn tiếp theo sau khi hoàn thành refinements.

---

### **GIAI ĐOẠN 4: Xác định và Thiết lập Table Relationships**

#### 🔗 Các hoạt động chính

**1. Identify Relationships**

**Phương pháp**:
- Conduct interviews với users và management
- Leverage knowledge của họ về data
- Identify relationships giữa các tables

**2. Establish Logical Connection**

**Phương thức kết nối** (tùy loại relationship):
- Sử dụng **Primary Key**
- Sử dụng **Foreign Key**
- Sử dụng **Linking Table**

**3. Determine Participation Characteristics**

**Type of Participation**:
- Optional participation
- Mandatory participation

**Degree of Participation**:
- Minimum number of related records
- Maximum number of related records

**Cơ sở xác định**:
- Nature của data trong tables
- Specific business rules

**4. Establish Relationship-level Integrity**
- Đảm bảo data integrity ở mức relationship
- Verify matching values giữa shared fields
- Check insert/update/delete operations

---

### **GIAI ĐOẠN 5: Xác định và Định nghĩa Business Rules**

#### 📜 Định nghĩa

**Business Rules**: Các limitations và requirements mà tổ chức áp đặt lên database, dựa trên cách tổ chức views và uses data của mình.

#### 🎯 Các hoạt động chính

**1. Conduct Interviews**
- Với users: Identify specific constraints
- Với management: Understand business requirements

**2. Identify Limitations**

**Các khía cạnh có thể bị giới hạn**:
- Data (dữ liệu)
- Data structures (cấu trúc dữ liệu)
- Relationships (quan hệ)

**3. Establish Business Rules**
- Document specifications thành business rules
- Define constraints rõ ràng

**4. Implement Validation Tables**
- Define validation tables khi cần thiết
- Support cho business rules cụ thể
- Enforce data integrity

#### 💡 Ý nghĩa

Business rules giúp:
- ✅ Establish various levels of data integrity
- ✅ Ensure data consistency
- ✅ Reflect business logic trong database design

---

### **GIAI ĐOẠN 6: Xác định và Định nghĩa Views**

#### 👁️ Định nghĩa Views

**View**: Virtual table cho phép users làm việc với data theo các cách khác nhau.

#### 🎯 Các hoạt động chính

**1. Conduct Interviews**

**Mục đích**: Identify various ways users work với data

**Các trường hợp phổ biến**:
- Users cần detailed information cho công việc hàng ngày
- Management cần summary information cho strategic decisions
- Các nhóm users khác nhau cần access information theo specific ways

**2. Define Views**

**Quy trình**:
- Sử dụng appropriate tables và fields
- Establish criteria cho views cần retrieve specific information

**Ví dụ criteria**:
- List customers ở Texas
- Display total number of authorized vendors by city ở Washington
- Show sales summary by quarter

**3. Establish View Characteristics**
- Xác định fields nào được include
- Define filtering criteria
- Set sorting order nếu cần

---

### **GIAI ĐOẠN 7: Review Data Integrity**

#### 🔍 Mục đích

Review final database structure để đảm bảo data integrity hoàn chỉnh.

#### 📊 4 Bước Review

**BƯỚC 1: Review Tables (Table-level Integrity)**

**Checklist**:
- [ ] Mỗi table meets criteria của properly designed table
- [ ] Fields trong mỗi table có proper structure
- [ ] Resolve inconsistencies và problems
- [ ] Verify tables có table-level integrity

**BƯỚC 2: Review Field Specifications (Field-level Integrity)**

**Checklist**:
- [ ] Review specifications của mỗi field
- [ ] Make necessary refinements
- [ ] Check field-level integrity
- [ ] Reaffirm field-level integrity đã establish trước đó

**BƯỚC 3: Review Relationships (Relationship-level Integrity)**

**Checklist**:
- [ ] Review validity của mỗi relationship
- [ ] Confirm relationship type
- [ ] Confirm participation characteristics
- [ ] Review relationship integrity:
   - Matching values giữa shared fields
   - No problems khi insert data
   - No problems khi update data
   - No problems khi delete data

**BƯỚC 4: Review Business Rules**

**Checklist**:
- [ ] Review business rules identified trước đó
- [ ] Confirm constraints đã áp dặt
- [ ] Identify new limitations (nếu có)
- [ ] Establish new business rules (nếu cần)
- [ ] Add vào existing set of business rules

#### ✅ Kết thúc quá trình

- Logical database structure sẵn sàng implement trong RDBMS
- Tuy nhiên, process không bao giờ thực sự "complete"
- Database structure sẽ luôn cần refinement khi organization evolves

---

## 🎨 TỔNG KẾT QUY TRÌNH

### 📊 Sơ đồ tóm tắt 7 giai đoạn

```
┌─────────────────────────────────────────────────────────┐
│  GIAI ĐOẠN 1: Mission Statement & Objectives           │
│  → Xác định purpose và general tasks                   │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│  GIAI ĐOẠN 2: Analyze Current Database                 │
│  → Identify data requirements                          │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│  GIAI ĐOẠN 3: Create Data Structures                   │
│  → Tables, Fields, Keys, Specifications                │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│  GIAI ĐOẠN 4: Table Relationships                      │
│  → Identify, establish connections, set characteristics│
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│  GIAI ĐOẠN 5: Business Rules                           │
│  → Identify constraints, establish rules               │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│  GIAI ĐOẠN 6: Views                                    │
│  → Define virtual tables for different user needs      │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│  GIAI ĐOẠN 7: Review Data Integrity                    │
│  → Final quality control, verify all integrity levels  │
└─────────────────────────────────────────────────────────┘
```

### 🔑 Các điểm then chốt

1. **Completeness is Critical** ⚠️
   - Không được skip bất kỳ giai đoạn nào
   - Incomplete design = Poor design

2. **Integrity is Proportional** 📈
   - Mức độ tuân thủ quy trình = Mức độ integrity

3. **Process is Iterative** 🔄
   - Database evolves với organization
   - Continuous refinement là cần thiết

4. **Documentation is Essential** 📚
   - Document mỗi giai đoạn
   - Maintain comprehensive records

---

## ❓ CÂU HỎI ÔN TẬP VÀ ĐÁP ÁN

### Câu 1: Tại sao việc hoàn thành design process là quan trọng?

**Đáp án**:
Việc hoàn thành design process là quan trọng vì nó giúp đảm bảo:
- **Sound structure**: Cấu trúc database vững chắc, đúng đắn
- **Data integrity**: Tính toàn vẹn dữ liệu được đảm bảo

Nếu không hoàn thành đầy đủ quy trình, database sẽ có:
- Poor design (thiết kế kém)
- Improper design (thiết kế không phù hợp)
- Structural và data integrity thấp
- Nhiều vấn đề khi sử dụng trong tương lai

---

### Câu 2: Đúng hay sai: "Mức độ structural integrity tỉ lệ thuận với việc bạn tuân thủ design process nghiêm ngặt đến mức nào"

**Đáp án**: **ĐÚNG** ✅

Giải thích:
- Càng follow design process đầy đủ → Structural integrity càng cao
- Càng bỏ qua nhiều bước → Structural integrity càng thấp
- Đây là một nguyên tắc cơ bản và quan trọng trong database design

Công thức đơn giản:
```
Mức độ tuân thủ design process ↑ = Structural integrity ↑
Mức độ tuân thủ design process ↓ = Structural integrity ↓
```

---

### Câu 3: Mission statement xác định điều gì?

**Đáp án**:
Mission statement xác định **purpose (mục đích)** của database.

**Chi tiết**:
- Định nghĩa tại sao database được tạo ra
- Cung cấp focus rõ ràng cho design work
- Đảm bảo database structure phù hợp với intended purpose
- Hướng dẫn việc collect data cần thiết

**Ví dụ mission statement**:
- "Database này để quản lý thông tin sinh viên và khóa học"
- "Database này để track inventory và sales của công ty"
- "Database này để hỗ trợ quy trình tuyển dụng nhân sự"

---

### Câu 4: Mission objectives đại diện cho điều gì?

**Đáp án**:
Mission objectives là các **statements đại diện cho general tasks** mà users có thể thực hiện với dữ liệu trong database.

**Vai trò**:
1. **Support mission statement**: Hỗ trợ và cụ thể hóa mission statement
2. **Help determine database structure**: Giúp xác định các khía cạnh của database structure

**Ví dụ mission objectives**:
- "Maintain complete student records"
- "Track course enrollments"
- "Generate transcripts and reports"
- "Manage faculty assignments"
- "Monitor student academic progress"

**Đặc điểm**:
- Là general tasks (không phải specific technical operations)
- User-oriented (hướng vào người dùng)
- Support việc thiết kế database structure

---

### Câu 5: Danh sách các fields và calculations mà bạn compile trong giai đoạn thứ hai của design process tạo nên điều gì của tổ chức bạn?

**Đáp án**:
Danh sách này tạo nên **fundamental data requirements** (yêu cầu dữ liệu cơ bản) của tổ chức.

**Giải thích chi tiết**:

**Initial field list** bao gồm:
- Tất cả fields cần thiết để support business operations
- Calculated fields (được tách riêng ra)

**Refined field list** (sau khi xử lý):
- Loại bỏ calculated fields
- Giữ lại pure data fields
- → Đây chính là **fundamental data requirements**

**Ý nghĩa**:
- Đại diện cho dữ liệu cốt lõi mà organization cần
- Là starting point cho việc design database structure
- Sẽ được extend và refine thêm trong các giai đoạn sau

**Lưu ý**:
- Calculated fields KHÔNG bị loại bỏ hoàn toàn
- Chúng được đặt vào separate list
- Sẽ được sử dụng lại sau trong design process (ví dụ trong views)

---

### Câu 6: Bạn xác định các subjects khác nhau mà tables sẽ represent từ đâu?

**Đáp án**:
Bạn xác định subjects từ **HAI nguồn**:

1. **Mission objectives**
   - Được compile trong giai đoạn 1 của design process
   - Cho biết general tasks users cần thực hiện

2. **Data requirements**
   - Được gather trong giai đoạn 2 của design process
   - Từ analysis của current database
   - Từ interviews với users và management

**Quy trình cụ thể**:

```
Mission Objectives + Data Requirements
           ↓
    Identify Subjects
           ↓
   Establish as Tables
           ↓
Associate with Fields
```

**Ví dụ**:
- Mission objective: "Track student information" → Subject: STUDENTS
- Mission objective: "Manage course catalog" → Subject: COURSES
- Data requirement: Need to store instructor info → Subject: INSTRUCTORS

**Lưu ý quan trọng**:
- Mỗi subject sẽ trở thành một table
- Mỗi table chỉ represent 1 subject duy nhất
- Subjects thường là nouns (danh từ): người, nơi chốn, sự vật, sự kiện

---

### Câu 7: Đúng hay sai: "Bạn thiết lập field specifications cho mỗi field trong database trong giai đoạn thứ ba của database design process"

**Đáp án**: **ĐÚNG** ✅

**Giải thích chi tiết**:

Field specifications được establish trong **Giai đoạn 3: Create Data Structures**, cụ thể là bước cuối cùng của giai đoạn này.

**Thứ tự trong Giai đoạn 3**:
1. Define tables
2. Refine fields
3. Review và refine table structures
4. Establish keys
5. **Establish field specifications** ← Bước cuối cùng

**Field specifications bao gồm**:
- **General elements**: Tên field, description, parent table
- **Physical elements**: Data type, length, default value
- **Logical elements**: Required value, range of values, input mask

**Quy trình thiết lập**:
1. Conduct interviews với users và management
2. Identify field characteristics quan trọng
3. Review và discuss các characteristics
4. Define và document specifications cho mỗi field

**Tại sao trong giai đoạn 3?**:
- Sau khi đã có tables và fields clearly defined
- Trước khi establish relationships (giai đoạn 4)
- Đảm bảo mỗi field có đầy đủ thông tin cần thiết

---

### Câu 8: Bạn thiết lập logical connection giữa các tables trong một relationship bằng cách nào?

**Đáp án**:
Bạn thiết lập logical connection bằng **HAI phương thức**:

**Phương thức 1: Sử dụng Primary Keys và Foreign Keys**
- Áp dụng cho: One-to-One và One-to-Many relationships
- Cách thức:
   - Primary key của parent table
   - Trở thành Foreign key trong related table
   - Tạo logical link giữa hai tables

**Phương thức 2: Sử dụng Linking Table**
- Áp dụng cho: Many-to-Many relationships
- Cách thức:
   - Tạo table mới (linking table)
   - Chứa foreign keys từ cả hai tables
   - Kết nối gián tiếp hai tables thông qua linking table

**Ví dụ minh họa**:

**Ví dụ 1: One-to-Many với Primary/Foreign Key**
```
CUSTOMERS                ORDERS
-----------             -----------
CustomerID (PK) ----→   CustomerID (FK)
Name                    OrderID (PK)
Email                   OrderDate
```

**Ví dụ 2: Many-to-Many với Linking Table**
```
STUDENTS              STUDENT_COURSES           COURSES
---------             ----------------          ---------
StudentID (PK) ----→  StudentID (FK)           CourseID (PK)
Name                  CourseID (FK)       ←--- CourseName
Email                 EnrollmentDate            Credits
```

**Lưu ý**:
- Phương thức sử dụng phụ thuộc vào **type of relationship**
- Cả hai phương thức đều establish logical connection
- Logical connection khác với physical storage

---

### Câu 9: Cách mà tổ chức của bạn views và uses data sẽ xác định điều gì?

**Đáp án**:
Cách tổ chức views và uses data sẽ xác định **một tập hợp limitations và requirements** mà bạn phải build vào database.

**Giải thích chi tiết**:

**Limitations và Requirements này bao gồm**:
- Constraints trên data values (ví dụ: tuổi phải >= 18)
- Constraints trên data structures (ví dụ: field không được null)
- Constraints trên relationships (ví dụ: một order phải có customer)
- Business logic rules (ví dụ: discount rules, approval workflows)

**Cách xác định**:
1. Conduct interviews với users và management
2. Understand cách họ view data (góc nhìn về dữ liệu)
3. Understand cách họ use data (sử dụng dữ liệu ra sao)
4. Identify specific constraints và requirements
5. Document chúng thành **business rules**

**Ví dụ thực tế**:

**Scenario 1: E-commerce company**
- View: "Customer phải đủ 18 tuổi để mua sản phẩm"
- → Requirement: Age >= 18 constraint

**Scenario 2: University**
- Use: "Sinh viên chỉ được enroll tối đa 5 courses mỗi semester"
- → Limitation: Maximum 5 enrollments constraint

**Scenario 3: Hospital**
- View: "Patient records phải luôn có contact information"
- → Requirement: Phone/Email không được null

**Tại sao quan trọng?**
- Reflect business logic vào database
- Ensure data integrity và consistency
- Prevent invalid data entry
- Support business operations correctly

**Liên hệ với Business Rules**:
- Những limitations và requirements này chính là foundation cho business rules
- Business rules được establish trong Giai đoạn 5
- Chúng provide một distinct level of data integrity

---

### Câu 10: Bạn có thể define và implement validation tables khi nào?

**Đáp án**:
Bạn có thể define và implement validation tables **khi cần thiết để support certain business rules** (as necessary to support certain business rules).

**Giải thích chi tiết**:

**Validation Tables (còn gọi là Lookup Tables)**:
- Là loại table đặc biệt store data dùng để implement data integrity
- Chứa data tĩnh (static data), ít khi thay đổi
- Được dùng để validate values trong data tables

**Khi nào cần Validation Tables?**

**1. Khi có business rule về valid values**
```
Business rule: "Status field chỉ được nhận một trong các giá trị: 
Active, Inactive, Pending, Suspended"

→ Tạo STATUS_TYPES validation table:
StatusID | StatusName
---------|------------
1        | Active
2        | Inactive
3        | Pending
4        | Suspended
```

**2. Khi cần standardize data entry**
```
Business rule: "Chỉ chấp nhận các state codes của USA"

→ Tạo STATES validation table:
StateCode | StateName
----------|------------
CA        | California
NY        | New York
TX        | Texas
...       | ...
```

**3. Khi có category hoặc classification system**
```
Business rule: "Products phải thuộc một category hợp lệ"

→ Tạo CATEGORIES validation table:
CategoryID | CategoryName
-----------|-------------
10000      | Accessories
20000      | Bikes
30000      | Clothing
40000      | Components
```

**Đặc điểm của Validation Tables**:
- ✅ Static data (dữ liệu tĩnh)
- ✅ Ít interactions trực tiếp
- ✅ Used indirectly để validate values
- ✅ Support data integrity
- ✅ Prevent invalid data entry

**Vị trí trong Design Process**:
- Được discuss chi tiết trong **Chapter 11: Business Rules**
- Thường được identify trong **Giai đoạn 5** (Business Rules phase)
- Có thể được implement trong **Giai đoạn 3** hoặc **Giai đoạn 5**

**Lợi ích**:
- Ensure data consistency
- Easy to maintain valid values
- Centralized control
- Support referential integrity

---

### Câu 11: Trong quá trình review data integrity, bạn review những gì đầu tiên?

**Đáp án**:
Bạn review **tables** đầu tiên (review each table).

**Giải thích chi tiết**:

**Thứ tự review trong Giai đoạn 7** (4 bước):

**BƯỚC 1: Review Tables** ← ĐÂY LÀ BƯỚC ĐẦU TIÊN
- Review each table
- Ensure mỗi table meets criteria của properly designed table
- Check fields trong table cho proper structure
- Resolve inconsistencies và problems
- Verify table-level integrity

**BƯỚC 2: Review Field Specifications**
- Review specifications của mỗi field
- Make necessary refinements
- Check field-level integrity

**BƯỚC 3: Review Relationships**
- Review validity của relationships
- Confirm relationship type và participation
- Review relationship integrity

**BƯỚC 4: Review Business Rules**
- Review business rules identified
- Confirm constraints
- Add new rules nếu cần

**Tại sao review Tables trước?**

**1. Foundation First**
- Tables là foundation của database
- Phải đảm bảo foundation vững chắc trước

**2. Hierarchical Structure**
```
Tables (nền tảng)
  ↓
Fields (thành phần của tables)
  ↓
Relationships (kết nối giữa tables)
  ↓
Business Rules (ràng buộc toàn bộ)
```

**3. Logical Progression**
- Từ general → specific
- Từ structure → constraints
- Từ physical → logical

**Checklist cho việc review Tables**:
- [ ] Table represents duy nhất 1 subject
- [ ] Không có unnecessary duplicate fields
- [ ] Không có multipart/multivalued fields
- [ ] Có properly defined primary key
- [ ] Fields đều represent characteristics của table's subject
- [ ] Table structure meets normalization requirements

**Kết quả mong đợi**:
- Verification of table-level integrity
- Tables properly designed
- Ready cho remaining reviews

---

## 🎓 TIPS HỌC TẬP

### ✅ Cách học hiệu quả Chương 4

1. **Hiểu Big Picture trước**
   - Nắm được 7 giai đoạn và thứ tự của chúng
   - Hiểu mục đích của từng giai đoạn

2. **Tập trung vào liên kết**
   - Hiểu output của giai đoạn này là input của giai đoạn sau
   - Visualize flow của toàn bộ process

3. **Nhớ các con số quan trọng**
   - 7 giai đoạn (phases)
   - 4 bước review data integrity
   - 2 phương thức establish connections

4. **Practice với ví dụ thực tế**
   - Áp dụng từng giai đoạn vào database project của bạn
   - Document mỗi bước theo đúng process

### 📝 Điểm cần ghi nhớ đặc biệt

- ⭐ **Completeness is non-negotiable**: KHÔNG được skip bất kỳ giai đoạn nào
- ⭐ **Integrity ∝ Thoroughness**: Tỉ lệ thuận trực tiếp
- ⭐ **Mission → Objectives → Requirements → Structure**: Logic flow
- ⭐ **Tables → Fields → Keys → Specs**: Thứ tự trong giai đoạn 3
- ⭐ **4 levels of integrity**: Table, Field, Relationship, Business Rules

---

## 📚 KẾT LUẬN

Chương 4 cung cấp **roadmap hoàn chỉnh** cho toàn bộ database design process. Đây là chương nền tảng giúp bạn:

1. **Hiểu tổng quan**: Big picture của design process
2. **Thấy logic**: Mối liên hệ giữa các giai đoạn
3. **Chuẩn bị tốt**: Cho các chương chi tiết sau này

**Remember**:
> "Databases không khó để thiết kế; chỉ cần một chút thời gian để design properly. Đừng take shortcuts!"

**Next Steps**:
- Các chương tiếp theo (5-13) sẽ đi sâu vào chi tiết từng giai đoạn
- Mỗi giai đoạn sẽ có techniques và best practices cụ thể
- Practice makes perfect - áp dụng vào projects thực tế!

---

**📖 Related Chapters**:
- Chapter 5: Starting the Process (Mission Statement & Objectives)
- Chapter 6: Analyzing the Current Database
- Chapter 7-12: Detailed phases
- Chapter 13: Final Data Integrity Review

---

*Tài liệu này được tổng hợp từ "Database Design for Mere Mortals, 25th Anniversary Edition" by Michael J. Hernandez*