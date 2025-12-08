# 📊 CHƯƠNG 6: PHÂN TÍCH CƠ SỞ DỮ LIỆU HIỆN TẠI

> "To see what is in front of one's nose needs a constant struggle." — George Orwell

---

## 📋 MỤC LỤC

1. [Tổng quan về phân tích](#tổng-quan)
2. [Loại cơ sở dữ liệu hiện tại](#loại-csdl)
3. [Quy trình phân tích](#quy-trình)
4. [Kỹ thuật phỏng vấn](#kỹ-thuật-phỏng-vấn)
5. [Phỏng vấn người dùng](#phỏng-vấn-người-dùng)
6. [Phỏng vấn quản lý](#phỏng-vấn-quản-lý)
7. [Biên soạn danh sách fields](#danh-sách-fields)
8. [Câu hỏi ôn tập và đáp án](#câu-hỏi-ôn-tập)

---

## 🎯 TỔNG QUAN VỀ PHÂN TÍCH {#tổng-quan}

### Mục đích phân tích

Phân tích cơ sở dữ liệu hiện tại giúp bạn:

✅ **Xác định** liệu database có hỗ trợ yêu cầu thông tin hiện tại của tổ chức không

✅ **Phát hiện** những thiếu sót về cấu trúc đang tồn tại

✅ **Quyết định** database cần phát triển như thế nào để hỗ trợ yêu cầu thông tin tương lai

### Ba câu hỏi cốt lõi cần trả lời

1. **Tổ chức sử dụng loại dữ liệu gì?**
2. **Tổ chức sử dụng dữ liệu đó như thế nào?**
3. **Tổ chức quản lý và duy trì dữ liệu đó ra sao?**

### ⚠️ Quy tắc quan trọng nhất

> **KHÔNG BAO GIỜ** áp dụng cấu trúc database hiện tại làm nền tảng cho database mới!

**Lý do:**
- Mọi vấn đề ẩn trong cấu trúc cũ sẽ được chuyển sang database mới
- Các vấn đề thường gặp: cấu trúc bảng vụng về, relationships không rõ ràng, field specifications không nhất quán
- Tốt hơn là định nghĩa cấu trúc mới một cách rõ ràng thay vì copy cấu trúc hiện có

---

## 🗂️ LOẠI CƠ SỞ DỮ LIỆU HIỆN TẠI {#loại-csdl}

### 1. Paper-Based Database (Database dạng giấy)

**Đặc điểm:**
- Còn gọi là file system
- Bao gồm: forms, tài liệu viết tay/in, được lưu trong folders hoặc notebooks
- Được nhận diện bằng coding scheme (số duy nhất, tab màu...)
- Lưu trữ trong tủ file

**Vấn đề thường gặp:**
- ❌ Dữ liệu không nhất quán
- ❌ Dữ liệu sai
- ❌ Dữ liệu trùng lặp
- ❌ Dữ liệu dư thừa
- ❌ Mục nhập không đầy đủ
- ❌ Dữ liệu cũ không được xóa

**Thách thức khi phân tích:**
- Tìm người hiểu hoàn toàn cách hoạt động của database
- Dữ liệu không được tổ chức tốt

### 2. Legacy Database (Database thừa kế)

**Đặc điểm:**
- Database đã tồn tại và được sử dụng nhiều năm (5 năm trở lên)
- Có thể nằm trên: mainframe, network server, PC, hoặc cloud
- Thường có application program để tương tác với dữ liệu

**Vấn đề thường gặp:**
- ❌ Duplicate fields (trường trùng lặp)
- ❌ Redundant data (dữ liệu dư thừa)
- ❌ Không tận dụng đầy đủ lợi ích của relational model

**Ưu điểm khi phân tích:**
- ✅ Có tổ chức và cấu trúc rõ ràng hơn paper-based
- ✅ Cấu trúc được định nghĩa rõ ràng
- ✅ Có application program giúp hiểu về data structures và tasks

### 3. Human Knowledge Base

**Đặc điểm:**
- Dựa trên trí nhớ của một hoặc nhiều nhân viên
- Những người này có kiến thức cụ thể về khía cạnh nào đó của tổ chức
- Rất quan trọng cho hoạt động kinh doanh

---

## 🔍 QUY TRÌNH PHÂN TÍCH {#quy-trình}

### Ba bước phân tích chính

```
┌─────────────────────────────────────┐
│  1. Xem xét cách thu thập dữ liệu   │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  2. Xem xét cách trình bày thông tin│
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  3. Phỏng vấn users và management   │
└─────────────────────────────────────┘
```

---

## 📝 BƯỚC 1: XEM XÉT CÁCH THU THẬP DỮ LIỆU

### Các loại tài liệu cần xem xét

**Paper-based items:**
- Index cards
- Handwritten lists
- Printed lists
- Preprinted forms

**Computer-based items:**
- Database application screens
- Spreadsheet programs
- Web browser data entry forms

### Quy trình thu thập mẫu

1. **Xác định** loại tài liệu tổ chức đang dùng
2. **Thu thập** một mẫu của mỗi loại
3. **Lưu trữ** các mẫu trong folder để dùng sau
4. **Chọn** mẫu có đủ thông tin nhất có thể

**Lưu ý quan trọng:**
- ⚠️ Chỉ thu thập một mẫu của mỗi loại tài liệu
- ⚠️ Mẫu phải điền đầy đủ nhất có thể
- ⚠️ Đặt tên folder rõ ràng và ghi ngày

---

## 📊 BƯỚC 2: XEM XÉT CÁCH TRÌNH BÀY THÔNG TIN

### Các loại trình bày cần xem xét

1. **Reports (Báo cáo)**
    - In từ word processor
    - In từ database application
    - In từ spreadsheet

2. **Screen Presentations (Trình chiếu)**
    - PowerPoint slides
    - Slides sử dụng hoặc kết hợp dữ liệu từ database

3. **Web Pages (Trang web)**
    - Pages hiển thị thông tin từ database
    - Không cần xem pages về lịch sử tổ chức

### Quy trình thu thập mẫu reports

**Cho mỗi loại report:**

1. Thu thập một mẫu
2. Xác định mục đích sử dụng
3. Viết mô tả
4. Đính kèm mô tả vào mẫu
5. Lưu trong folder riêng

**Cho presentations:**

1. Chụp screenshot các slides có dữ liệu
2. Copy vào word document
3. In và lưu trong folder
4. Ghi tên presentation, filename, ngày chụp

**Cho web pages:**

1. Chụp screenshot mỗi page liên quan
2. Copy vào word document
3. Ghi URL và ngày hiện tại
4. Lưu trong folder

---

## 🗣️ KỸ THUẬT PHỎNG VẤN {#kỹ-thuật-phỏng-vấn}

### Tại sao phỏng vấn quan trọng?

1. ✅ Cung cấp chi tiết về các mẫu đã thu thập
2. ✅ Cung cấp thông tin về cách tổ chức sử dụng dữ liệu
3. ✅ Giúp định nghĩa preliminary field và table structures
4. ✅ Giúp xác định future information requirements

> ⚠️ **QUAN TRỌNG:** Chỉ phỏng vấn đầy đủ và hoàn chỉnh mới đảm bảo database đáp ứng yêu cầu thông tin của tổ chức!

### Kỹ thuật phỏng vấn cơ bản

#### 1. Open-Ended Questions (Câu hỏi mở)

**Mục đích:** Tập trung vào subjects cụ thể

**Đặc điểm:**
- Không giới hạn câu trả lời
- Cho phép người được hỏi tự do trả lời
- Bắt đầu với: Who, What, Where, When, Why, How

**Ví dụ:**
- "What types of data do you work with on a daily basis?"
- "How do you use the information from this report?"
- "Why do you need to track customer preferences?"

#### 2. Closed Questions (Câu hỏi đóng)

**Mục đích:** Tập trung vào chi tiết cụ thể của một subject

**Đặc điểm:**
- Trả lời bằng Yes/No hoặc giá trị cụ thể
- Làm rõ thông tin đã có

**Ví dụ:**
- "Do you currently track customer email addresses?"
- "Are purchase orders numbered sequentially?"
- "Is this field required?"

#### 3. Subject-Identification Technique

**Mục đích:** Xác định subjects trong câu trả lời của người được phỏng vấn

**Cách thực hiện:**

1. **Lắng nghe** câu trả lời
2. **Xác định** các danh từ (nouns)
3. **Phân loại** danh từ:
    - Person (người)
    - Place (nơi chốn)
    - Thing (vật)
    - Event (sự kiện)
    - Concept (khái niệm)
4. **Thêm** vào danh sách subjects

**Ví dụ:**
> "We keep track of our **customers**, the **products** they buy, and the **orders** they place."

**Subjects được xác định:**
- Customer (person)
- Product (thing)
- Order (event)

#### 4. Characteristic-Identification Technique

**Mục đích:** Xác định characteristics (đặc điểm) của một subject cụ thể

**Cách thực hiện:**

1. **Đặt câu hỏi** về subject đã xác định
2. **Lắng nghe** các chi tiết mô tả
3. **Ghi lại** các characteristics
4. **Thêm** vào danh sách characteristics

**Ví dụ câu hỏi:**
- "What specific details do you keep about each customer?"
- "Can you describe a typical product?"
- "What information does an order contain?"

**Ví dụ:**
> "For each customer, we keep their **name**, **address**, **phone number**, and **email**."

**Characteristics được xác định:**
- Customer Name
- Customer Address
- Customer Phone Number
- Customer Email

---

## 👥 PHỎNG VẤN NGƯỜI DÙNG {#phỏng-vấn-người-dùng}

### Trước khi bắt đầu phỏng vấn

**Chuẩn bị:**
- ✅ Xem xét tất cả samples đã thu thập
- ✅ Chuẩn bị câu hỏi dựa trên samples
- ✅ Tạo danh sách subjects ban đầu
- ✅ Tạo danh sách characteristics ban đầu

### Bốn vấn đề chính cần giải quyết

#### 1. Data Type and Usage (Loại dữ liệu và cách sử dụng)

**Mục tiêu:**
- Xác định loại dữ liệu người dùng làm việc
- Hiểu cách họ sử dụng dữ liệu đó

**Câu hỏi mẫu:**
- "What types of data do you work with every day?"
- "How do you use this data in your daily tasks?"
- "Who else uses this data?"

**Kỹ thuật áp dụng:**
- ✅ Subject-Identification Technique
- ✅ Characteristic-Identification Technique

#### 2. Data Collection Samples Review

**Mục tiêu:** Hiểu rõ cách mỗi sample được sử dụng

**Quy trình:**

1. Lấy một sample từ folder
2. Hỏi người dùng về sample đó:
    - "How do you use this form?"
    - "What is its purpose?"
    - "How often do you use it?"
3. Viết mô tả dựa trên câu trả lời
4. Đính kèm mô tả vào sample
5. Xác định subjects và characteristics mới (nếu có)
6. Thêm vào danh sách tương ứng
7. Lặp lại cho tất cả samples

#### 3. Information Presentation Samples Review

**Mục tiêu:** Hiểu về data được dùng để tạo reports

**Ba phần chính:**

##### A. Current Information Requirements

**Xác định nguồn gốc dữ liệu:**

```
Hỏi: "Do you provide the data used to generate this report?"

├─ YES → Hỏi tiếp: "Do you personally enter and maintain this data?"
│         ├─ YES → Chuyển sang sample tiếp theo
│         └─ NO → Xác định ai tạo/duy trì dữ liệu
│
└─ NO → Xác định nguồn gốc dữ liệu
```

**Ví dụ conversation flow:**
```
Q: "Do you provide the data for this Customer Phone List?"
A: "No, I receive this from the Sales Department."

Q: "Who in Sales Department maintains this data?"
A: "Joan in Marketing enters all customer information."

→ Ghi chú: Customer data được quản lý bởi Joan (Marketing)
```

##### B. Additional Information Requirements

**Mục tiêu:** Xác định thông tin bổ sung cần thiết

**Quy trình:**

1. Xem lại report samples với participants
2. Hỏi có cần thêm thông tin nào không
3. Yêu cầu họ ghi chú trực tiếp lên report:
    - Thông tin muốn thêm
    - Lý do cần thiết
4. Xác định subjects/characteristics mới
5. Thêm vào danh sách

**Ví dụ:**
```
Report: Product Inventory
Note: "Can we include Vendor Name? It would make it easier 
       to identify a specific product."

→ New characteristic: Vendor Name
→ Potentially new subject: Vendor
```

##### C. Future Information Requirements

**Mục tiêu:** Dự đoán nhu cầu thông tin tương lai

**Câu hỏi hướng dẫn:**
- "How will the organization's evolution affect the information you need?"
- "Do you think you'll need additional types of information as the organization grows?"
- "How will your daily tasks change as we expand?"
- "What new information might you need if your duties increase?"

**Lưu ý:**
- ⚠️ Câu trả lời dựa trên speculation (suy đoán)
- ⚠️ Không thể dự đoán chính xác 100%
- ✅ Tốt hơn là chuẩn bị trước bằng cách định nghĩa data structures

**Kỹ thuật hỗ trợ:**
- Vẽ sketches cho reports mới
- Tạo rough drawings của data entry forms
- Giúp participants visualize nhu cầu tương lai
- Lưu sketches trong folder riêng, có mã code để theo dõi revisions

---

## 👔 PHỎNG VẤN QUẢN LÝ {#phỏng-vấn-quản-lý}

### Tại sao phỏng vấn riêng Management?

- ✅ Có góc nhìn tổng thể về tổ chức
- ✅ Hiểu chiến lược phát triển dài hạn
- ✅ Biết thông tin nào quan trọng cho quyết định
- ✅ Có thể xác định priority của thông tin

### Ba vấn đề chính

#### 1. Current Information Review

**Mục tiêu:** Xác định loại thông tin management hiện đang nhận

**Quy trình:**

1. Xem xét reports management nhận
2. Xác định:
    - Tần suất nhận report
    - Cách sử dụng thông tin
    - Tính hữu ích của thông tin
3. Thu thập mẫu của reports chưa có
4. Thêm subjects/characteristics mới vào danh sách

**Câu hỏi mẫu:**
- "What reports do you currently receive?"
- "How do you use these reports to make decisions?"
- "Is this information sufficient for your needs?"

#### 2. Additional Information Requirements

**Mục tiêu:** Xác định thông tin bổ sung management cần

**Quy trình:**

1. Xem lại report samples với management
2. Hỏi về thông tin bổ sung cần thiết
3. Yêu cầu ghi chú lý do cần thiết
4. Xác định subjects/characteristics mới
5. Review và giải quyết concerns

**Điểm khác biệt với user interviews:**
- Management thường cần thông tin tổng hợp (aggregated data)
- Ít quan tâm đến chi tiết vận hành hàng ngày
- Tập trung vào strategic information

#### 3. Future Information Requirements

**Mục tiêu:** Dự đoán nhu cầu thông tin khi tổ chức phát triển

**Câu hỏi mẫu:**
- "How do you see the organization evolving?"
- "What information will you need to guide this evolution?"
- "How will growth affect your decision-making needs?"

**Kỹ thuật hỗ trợ:**
- Thảo luận về hướng phát triển của tổ chức
- Sketch designs cho new reports
- Lưu trong folder riêng, có code

#### 4. Overall Information Requirements Review

**Mục tiêu:** Đảm bảo không bỏ sót thông tin quan trọng

**Quy trình:**

1. Review toàn bộ subjects list với management
2. Xác định subjects bị bỏ sót
3. Review toàn bộ characteristics list
4. Xác định characteristics bị bỏ sót
5. Thêm items mới vào danh sách tương ứng

**Lợi ích:**
- ✅ Double-check công việc đã làm
- ✅ Phát hiện oversights (thiếu sót)
- ✅ Có góc nhìn từ management perspective

---

## 📋 BIÊN SOẠN DANH SÁCH FIELDS {#danh-sách-fields}

### Từ Characteristics sang Fields

**Quy trình chuyển đổi:**

```
Characteristics List
        ↓
    Refine & Review
        ↓
  ┌─────────────────┐
  │  Complete Field │
  │      List       │
  └────────┬────────┘
           │
    ┌──────┴──────┐
    ▼             ▼
Preliminary    Calculated
Field List     Field List
```

### 1. Preliminary Field List

**Định nghĩa:**
- Danh sách liệt kê các data requirements cơ bản của tổ chức
- Thiết lập core set của fields cần định nghĩa trong database

**Đặc điểm:**

✅ **Mỗi field phải có tên duy nhất**
- Tránh nhầm lẫn
- Dễ dàng tham chiếu
- Rõ ràng về mục đích

✅ **Tên field phải mô tả rõ ràng**
- Không dùng từ viết tắt mơ hồ
- Không dùng ký hiệu đặc biệt
- Nên dùng tên đầy đủ, có ý nghĩa

**Ví dụ Preliminary Field List:**
```
□ Customer Name
□ Customer Address
□ Customer City
□ Customer State
□ Customer Zip Code
□ Customer Phone
□ Customer Email
□ Product Name
□ Product Description
□ Product Category
□ Unit Price
□ Quantity On Hand
□ Supplier Name
□ Supplier Contact
□ Invoice Number
□ Invoice Date
□ Employee Name
□ Employee Position
```

### 2. Calculated Field List

**Định nghĩa:**
- Fields chứa giá trị là kết quả của:
    - String concatenations (nối chuỗi)
    - Mathematical expressions (biểu thức toán học)

**Đặc điểm:**

❌ **KHÔNG lưu trữ trong database**
- Giá trị có thể tính toán khi cần
- Tránh data redundancy
- Dễ dàng cập nhật

✅ **Xử lý trong queries/views/reports**

**Ví dụ Calculated Fields:**

**String Concatenation:**
```
Full Address = Street + City + State + Zip
Employee Full Name = First Name + Last Name
Product Code = Category + "-" + ID
```

**Mathematical Expression:**
```
Item Total = Unit Price × Quantity
Subtotal = SUM(Item Total)
Discount Amount = Subtotal × Discount Rate
Grand Total = Subtotal - Discount Amount
Tax Amount = Subtotal × Tax Rate
```

### 3. Value Lists (Enumerated Lists)

**Định nghĩa:**
- Danh sách các giá trị được phép cho một field cụ thể
- Giúp enforce business rules
- Đảm bảo data consistency

**Mục đích:**
- ✅ Giới hạn giá trị hợp lệ
- ✅ Tránh lỗi nhập liệu
- ✅ Maintain data integrity

**Ví dụ Value Lists:**

```
Field: Customer Type
Values: □ Regular
        □ Preferred
        □ Silver
        □ Gold
        □ Platinum

Field: Order Status
Values: □ Pending
        □ Processing
        □ Shipped
        □ Delivered
        □ Cancelled

Field: Product Category
Values: □ Accessories
        □ Components
        □ Bikes
        □ Clothing
        □ Parts
```

**Khi nào tạo Value List:**
- Field có số lượng giá trị hữu hạn
- Giá trị cần consistency
- Business rules yêu cầu giới hạn
- Giúp data entry dễ dàng hơn

### Review với Users và Management

**Mục tiêu:** Xác nhận danh sách fields hoàn chỉnh và chính xác

**Quy trình:**

1. **Present cả hai lists**
    - Preliminary Field List
    - Calculated Field List

2. **Explain phân biệt giữa hai lists**
    - Tại sao tách riêng
    - Cách xử lý khác nhau

3. **Review từng field**
    - Tên có rõ ràng không?
    - Có thiếu fields nào không?
    - Có fields không cần thiết không?

4. **Discuss value lists**
    - Fields nào cần value list?
    - Các giá trị hợp lệ là gì?

5. **Make revisions**
    - Thêm/xóa/đổi tên fields
    - Update value lists
    - Ghi chú changes

6. **Get sign-off**
    - Xác nhận từ users
    - Approval từ management

**Lưu ý quan trọng:**
- 📅 Date mỗi version của danh sách
- 📝 Track changes và revisions
- 💾 Lưu các versions trước đó
- ✅ Document reasons cho changes

---

## ✅ CÂU HỎI ÔN TẬP VÀ ĐÁP ÁN {#câu-hỏi-ôn-tập}

### Câu 1: Nêu hai mục tiêu của việc phân tích cơ sở dữ liệu hiện tại.

**Đáp án:**

Các mục tiêu của việc phân tích cơ sở dữ liệu hiện tại là xác định:

1. **Loại dữ liệu** mà tổ chức sử dụng (What types of data the organization uses)

2. **Cách tổ chức sử dụng dữ liệu đó** (How the organization uses its data)

3. **Cách tổ chức quản lý và duy trì dữ liệu** (How the organization manages and maintains its data)

**Giải thích chi tiết:**

- **Mục tiêu 1** giúp xác định data requirements cơ bản
- **Mục tiêu 2** giúp hiểu business processes và workflows
- **Mục tiêu 3** giúp phát hiện structural deficiencies và opportunities for improvement

---

### Câu 2: Đúng hay Sai: Bạn có thể áp dụng cấu trúc database hiện tại làm nền tảng cho cấu trúc mới.

**Đáp án: SAI (False)**

**Giải thích chi tiết:**

Bạn **KHÔNG NÊN** áp dụng cấu trúc database hiện tại làm nền tảng cho cấu trúc mới vì:

1. **Chuyển giao vấn đề:**
    - Mọi vấn đề ẩn trong cấu trúc cũ sẽ được chuyển sang database mới
    - Các hidden problems sẽ surface later ở thời điểm không mong muốn

2. **Các vấn đề thường gặp:**
    - Awkward table structures (cấu trúc bảng vụng về)
    - Poorly defined relationships (relationships không rõ ràng)
    - Inconsistent field specifications (field specs không nhất quán)

3. **Nguyên tắc tốt hơn:**
    - Luôn định nghĩa database structure mới một cách explicit
    - Better to define explicitly than to copy existing structure
    - If old database didn't have problems, you wouldn't be building a new one!

---

### Câu 3: Legacy database là gì?

**Đáp án:**

**Legacy database** (còn gọi là inherited database) là cơ sở dữ liệu đã tồn tại và được sử dụng trong nhiều năm (thường từ 5 năm trở lên).

**Đặc điểm chi tiết:**

**1. Về tuổi đời:**
- Đã được sử dụng several years (nhiều năm)
- Thường từ 5+ years
- Có historical data quan trọng

**2. Về cấu trúc:**
- Bao gồm các data structures đa dạng
- Có user interfaces
- Nằm trên nhiều nền tảng khác nhau:
    - Mainframe computers
    - Network servers
    - Personal computers
    - Cloud (gần đây)

**3. Về chất lượng:**
- Capability và functionality phụ thuộc vào:
    - Skills của developers
    - Knowledge của team
    - Application development tools được dùng
    - Database management software

**4. Vấn đề thường gặp:**
- Duplicate fields
- Redundant data
- Không tận dụng đầy đủ benefits của relational model
- Developers có thể không biết relational theory

**5. Ưu điểm khi phân tích:**
- Có tổ chức hơn paper-based databases
- Structures được định nghĩa rõ ràng
- Có application program để tham khảo
- Easier to analyze than paper-based systems

---

### Câu 4: Nêu hai bước trong quy trình phân tích.

**Đáp án:**

Ba bước trong quy trình phân tích (analysis process) là:

1. **Reviewing the way data is collected**
    - Xem xét cách dữ liệu được thu thập

2. **Reviewing the manner in which information is presented**
    - Xem xét cách thông tin được trình bày

3. **Conducting interviews with users and management**
    - Tiến hành phỏng vấn với người dùng và quản lý

**Chi tiết mỗi bước:**

**Bước 1 - Reviewing Data Collection:**
- Thu thập samples của paper forms
- Screenshot data entry screens
- Review database application forms
- Identify data collection methods

**Bước 2 - Reviewing Information Presentation:**
- Thu thập report samples
- Screenshot presentation slides
- Capture web pages
- Identify information output methods

**Bước 3 - Conducting Interviews:**
- Interview users về daily work
- Interview management về strategic needs
- Gather detailed requirements
- Identify future needs

---

### Câu 5: Những loại chương trình phần mềm máy tính nào bạn nên xem xét trong quá trình phân tích?

**Đáp án:**

Các loại computer software programs cần xem xét trong quá trình phân tích bao gồm:

**1. Word Processors (Phần mềm xử lý văn bản)**
- Microsoft Word, Google Docs
- Dùng để tạo reports, forms, documents
- Check reports được generate từ word processors

**2. Spreadsheets (Phần mềm bảng tính)**
- Microsoft Excel, Google Sheets
- Dùng để maintain data, create reports
- Check data organization và calculations

**3. Database Programs (Phần mềm cơ sở dữ liệu)**
- Database applications
- Data entry screens
- Existing database structures
- Query results và reports

**4. Web Pages (Trang web)**
- Web-based applications
- Pages hiển thị data từ database
- Online forms và data entry interfaces
- Dynamic content drawing from database

**5. Presentation Software**
- PowerPoint, Google Slides
- Slides sử dụng database data
- Information visualization

**Mục đích xem xét:**
- ✅ Understand current data usage
- ✅ Identify data collection methods
- ✅ Recognize information presentation formats
- ✅ Discover data structures
- ✅ Identify fields và tables
- ✅ Understand business processes

---

### Câu 6: Tại sao bạn nên tiến hành phỏng vấn sau khi thu thập các mẫu thu thập dữ liệu và trình bày thông tin?

**Đáp án:**

Bạn nên tiến hành phỏng vấn sau khi thu thập samples vì những lý do sau:

**1. Cung cấp chi tiết về samples đã thu thập**
- Reviews trước chỉ identify (in general terms) cách organization collects và presents data
- Interviews cho phép ask specific questions về samples
- Có thể clarify aspects that are vague hoặc ambiguous

**2. Cung cấp thông tin về cách tổ chức sử dụng dữ liệu**
- Hiểu how users work với data daily basis
- Hiểu how management uses information để manage organization
- Discover actual usage patterns

**3. Giúp định nghĩa preliminary field và table structures**
- Responses từ interviews help identify initial structures
- Có context để interpret samples correctly
- Can connect data elements to business needs

**4. Giúp xác định future information requirements**
- Discussions về organization's growth
- Reveal new requirements
- Must be supported by database design

**5. Preparation benefits:**
- Samples provide concrete talking points
- Help formulate relevant questions
- Make interviews more focused và productive
- Avoid wasting participants' time
- Enable more meaningful discussions

**Thứ tự quan trọng:**
```
1. Gather samples FIRST
   ↓
2. Review và understand samples
   ↓
3. Prepare targeted questions
   ↓
4. THEN conduct interviews
   ↓
5. Get detailed clarifications
```

**Kết quả:**
- ✅ More efficient interviews
- ✅ Better understanding of data
- ✅ More accurate requirements
- ✅ Stronger database design

---

### Câu 7: Bạn sử dụng "open-ended" và "closed" questions như thế nào?

**Đáp án:**

**OPEN-ENDED QUESTIONS** và **CLOSED QUESTIONS** có mục đích và cách sử dụng khác nhau:

### Open-Ended Questions (Câu hỏi mở)

**Định nghĩa:**
- Câu hỏi không giới hạn câu trả lời
- Cho phép người được hỏi elaborate (giải thích chi tiết)

**Mục đích sử dụng:**
✅ Focus on **specific subjects** (chủ đề cụ thể)
✅ Khám phá general information
✅ Discover unknowns
✅ Encourage detailed responses

**Đặc điểm:**
- Bắt đầu với: Who, What, Where, When, Why, How
- Không thể trả lời Yes/No
- Requires explanation

**Ví dụ:**
```
❓ "What types of data do you work with daily?"
❓ "How do you use this information?"
❓ "Why is this report important to you?"
❓ "Where does this data come from?"
❓ "When do you need this information?"
❓ "Who uses this data besides you?"
```

**Kết quả mong đợi:**
- Detailed descriptions
- Multiple subjects identified
- New characteristics discovered
- Comprehensive understanding

---

### Closed Questions (Câu hỏi đóng)

**Định nghĩa:**
- Câu hỏi có giới hạn câu trả lời
- Typically Yes/No hoặc specific value

**Mục đích sử dụng:**
✅ Focus on **specific details** of a subject
✅ Clarify information
✅ Confirm understanding
✅ Get precise answers

**Đặc điểm:**
- Trả lời ngắn gọn
- Specific và definite
- Used for verification

**Ví dụ:**
```
❓ "Do you track customer email addresses?" → Yes/No
❓ "Are invoices numbered sequentially?" → Yes/No
❓ "How many employees do you have?" → Number
❓ "Is this field required?" → Yes/No
❓ "Does this report include tax?" → Yes/No
```

**Kết quả mong đợi:**
- Precise information
- Confirmation
- Specific values
- Clear yes/no answers

---

### Cách sử dụng kết hợp

**Strategy:**

```
START with Open-Ended
        ↓
    Get overview
        ↓
FOLLOW with Closed
        ↓
    Clarify details
```

**Ví dụ thực tế:**

**Conversation Flow 1:**
```
Open: "What information do you track about customers?"
→ Answer: "Name, address, phone, purchases..."

Closed: "Do you track email addresses?"
→ Answer: "No"

Closed: "Do you track customer preferences?"
→ Answer: "Yes"
```

**Conversation Flow 2:**
```
Open: "How do you use this sales report?"
→ Answer: "To analyze trends and forecast inventory..."

Closed: "Do you run this weekly or monthly?"
→ Answer: "Monthly"

Closed: "Does it include returns?"
→ Answer: "No"
```

**Best Practices:**
- 🎯 Use open-ended để explore
- 🎯 Use closed để verify
- 🎯 Balance cả hai types
- 🎯 Adapt based on responses
- 🎯 Don't rely solely on one type

---

### Câu 8: Subject-Identification Technique là gì?

**Đáp án:**

**Subject-Identification Technique** là kỹ thuật cho phép bạn xác định các subjects (chủ đề/đối tượng) trong câu trả lời của người tham gia phỏng vấn.

### Mục đích

✅ Identify subjects mà database cần track
✅ Build comprehensive subjects list
✅ Ensure không miss important entities
✅ Foundation cho table structures

### Cách thực hiện

**Bước 1: Lắng nghe câu trả lời**
- Tập trung vào nouns (danh từ)
- Don't interrupt
- Take notes

**Bước 2: Identify nouns trong response**
- Highlight hoặc underline nouns
- Look for multiple mentions
- Note relationships giữa nouns

**Bước 3: Phân loại nouns theo category**

**5 Categories of Subjects:**

1. **PERSON (Người)**
    - Individuals hoặc groups
    - Examples: Customer, Employee, Supplier, Student, Doctor

2. **PLACE (Nơi chốn)**
    - Physical hoặc virtual locations
    - Examples: Office, Warehouse, City, Website, Department

3. **THING (Vật)**
    - Tangible objects
    - Examples: Product, Equipment, Vehicle, Book, Computer

4. **EVENT (Sự kiện)**
    - Actions hoặc occurrences
    - Examples: Order, Appointment, Sale, Meeting, Transaction

5. **CONCEPT (Khái niệm)**
    - Abstract ideas
    - Examples: Account, Contract, License, Membership, Project

**Bước 4: Add to subjects list**
- Check for duplicates
- Use consistent naming
- Maintain organized list

### Ví dụ thực tế

**Example 1:**
```
Response: "We keep track of our CUSTOMERS, the PRODUCTS 
they buy, and the ORDERS they place."

Subjects identified:
✓ Customer (PERSON)
✓ Product (THING)
✓ Order (EVENT)
```

**Example 2:**
```
Response: "Each EMPLOYEE works in a DEPARTMENT and has 
access to our EQUIPMENT. They can reserve MEETING ROOMS 
for client APPOINTMENTS."

Subjects identified:
✓ Employee (PERSON)
✓ Department (PLACE)
✓ Equipment (THING)
✓ Meeting Room (PLACE)
✓ Appointment (EVENT)
```

**Example 3:**
```
Response: "Our SUPPLIERS deliver PARTS to our WAREHOUSE. 
We track each SHIPMENT and update our INVENTORY accordingly."

Subjects identified:
✓ Supplier (PERSON)
✓ Part (THING)
✓ Warehouse (PLACE)
✓ Shipment (EVENT)
✓ Inventory (CONCEPT)
```

### Lưu ý quan trọng

**✅ DO:**
- Listen carefully
- Identify ALL nouns
- Consider context
- Ask follow-up questions if unclear
- Maintain subjects list carefully

**❌ DON'T:**
- Ignore "small" subjects
- Assume you know subjects already
- Skip obvious subjects
- Forget to categorize
- Mix subjects with characteristics

### Benefits

1. **Systematic approach** to identifying subjects
2. **Ensures completeness** of subjects list
3. **Provides structure** for interviews
4. **Creates foundation** for database tables
5. **Reduces likelihood** of missing important entities

---

### Câu 9: Làm thế nào để bạn xác định các thuộc tính cụ thể cho một subject cụ thể?

**Đáp án:**

Bạn xác định các attributes (thuộc tính) cụ thể cho một subject bằng cách sử dụng **Characteristic-Identification Technique**.

### Mục đích

✅ Identify characteristics (details) của mỗi subject
✅ Build comprehensive characteristics list
✅ Understand data requirements fully
✅ Foundation cho field definitions

### Cách thực hiện

**Bước 1: Identify subject trước**
- Use Subject-Identification Technique
- Select một subject để focus

**Bước 2: Đặt targeted questions về subject**

**Question patterns:**
```
"What specific details do you keep about each [SUBJECT]?"
"Can you describe a typical [SUBJECT]?"
"What information does a [SUBJECT] contain?"
"Tell me everything you know about [SUBJECT]."
"What makes one [SUBJECT] different from another?"
```

**Bước 3: Lắng nghe descriptive details**
- Note adjectives (tính từ)
- Note descriptive phrases
- Note specific data points mentioned

**Bước 4: Extract characteristics**
- List each distinct detail
- Name each characteristic clearly
- Avoid ambiguity

**Bước 5: Add to characteristics list**
- Under appropriate subject
- Check for duplicates
- Use consistent naming

### Ví dụ thực tế

**Example 1: Customer**
```
Question: "What specific details do you keep about each customer?"

Response: "For each customer, we keep their NAME, ADDRESS, 
PHONE NUMBER, EMAIL, DATE OF BIRTH, and CUSTOMER TYPE 
(regular or preferred)."

Characteristics identified:
✓ Customer Name
✓ Customer Address
✓ Customer Phone Number
✓ Customer Email
✓ Customer Date of Birth
✓ Customer Type
```

**Example 2: Product**
```
Question: "Can you describe what information a product has?"

Response: "Each product has a PRODUCT ID, DESCRIPTION, 
CATEGORY, UNIT PRICE, QUANTITY ON HAND, REORDER LEVEL, 
and SUPPLIER NAME."

Characteristics identified:
✓ Product ID
✓ Product Description
✓ Product Category
✓ Unit Price
✓ Quantity On Hand
✓ Reorder Level
✓ Supplier Name
```

**Example 3: Order**
```
Question: "What details are included in an order?"

Response: "An order includes the ORDER NUMBER, ORDER DATE, 
CUSTOMER NAME, DELIVERY ADDRESS, ORDER STATUS, TOTAL AMOUNT, 
and PAYMENT METHOD."

Characteristics identified:
✓ Order Number
✓ Order Date
✓ Customer Name
✓ Delivery Address
✓ Order Status
✓ Total Amount
✓ Payment Method
```

### Advanced techniques

**1. Follow-up questions:**
```
"Are there any other details about [SUBJECT] that I should know?"
"What else describes a [SUBJECT]?"
"Is there anything unique about each [SUBJECT]?"
```

**2. Prompt với examples:**
```
"For example, do you track [CHARACTERISTIC]?"
"What about [ANOTHER CHARACTERISTIC]?"
```

**3. Review existing data:**
- Look at forms
- Examine reports
- Check data entry screens
- Review paper records

### Best Practices

**✅ DO:**
- Be thorough
- Ask follow-up questions
- Confirm understanding
- Record all characteristics
- Note relationships between characteristics

**❌ DON'T:**
- Assume characteristics
- Skip "obvious" details
- Mix characteristics from different subjects
- Use vague names
- Forget to document

### Organizing characteristics

**Create structured list:**
```
CUSTOMER
├─ Customer ID
├─ Customer Name
├─ Customer Address
├─ Customer Phone
└─ Customer Email

PRODUCT
├─ Product ID
├─ Product Name
├─ Product Description
├─ Unit Price
└─ Category

ORDER
├─ Order Number
├─ Order Date
├─ Customer ID (reference)
└─ Total Amount
```

### Verification

**Check characteristics by asking:**
- "Is this characteristic necessary?"
- "Does this describe the subject?"
- "Is this characteristic distinct?"
- "Can this be broken down further?"

---

### Câu 10: Đúng hay Sai: Bạn nên phỏng vấn người dùng và quản lý cùng một lúc.

**Đáp án: SAI (False)**

**Giải thích chi tiết:**

Bạn **NÊN phỏng vấn users và management RIÊNG BIỆT**, không cùng lúc.

### Lý do phỏng vấn riêng biệt

**1. Perspectives khác nhau**

**Users:**
- Focus on day-to-day operations
- Detailed, tactical information
- Hands-on experience với data
- Know practical problems
- Understand data entry và usage

**Management:**
- Focus on strategic decisions
- High-level, aggregated information
- Overview of organization
- Concerned with future direction
- Need analytical reports

**2. Communication dynamics**

**Riêng biệt Users:**
- ✅ More comfortable speaking openly
- ✅ Can discuss problems freely
- ✅ Won't feel intimidated
- ✅ More candid about issues
- ✅ Can express concerns about current system

**Riêng biệt Management:**
- ✅ Can discuss strategic plans
- ✅ Share confidential information
- ✅ Discuss organizational changes
- ✅ Express concerns about staff
- ✅ Plan for future without alarming users

**3. Question types khác nhau**

**For Users:**
```
❓ "How do you enter customer data?"
❓ "What problems do you face daily?"
❓ "What fields do you use most?"
❓ "How could data entry be easier?"
```

**For Management:**
```
❓ "What reports do you need for decisions?"
❓ "How is the organization evolving?"
❓ "What strategic information is missing?"
❓ "What future requirements do you foresee?"
```

**4. Information requirements khác nhau**

**Users need:**
- Detailed field-level information
- Daily operational data
- Transaction-level access
- Specific, granular data

**Management needs:**
- Summary và aggregated data
- Trend analysis
- Comparative reports
- Strategic insights

**5. Practical benefits của riêng biệt interviews

**More efficient:**
- Focus on relevant questions cho mỗi group
- Don't waste time với irrelevant topics
- Get deeper insights
- More productive use of time

**Better information quality:**
- More honest responses
- Complete information
- Less filtered communication
- True requirements emerge

### Interview strategy

**Recommended approach:**

```
PHASE 1: User Interviews
├─ Interview users first
├─ Focus on operational details
├─ Gather field-level requirements
├─ Understand daily workflows
└─ Identify practical problems

PHASE 2: Management Interviews
├─ Interview management after users
├─ Focus on strategic needs
├─ Gather high-level requirements
├─ Understand organizational direction
└─ Identify future plans

PHASE 3: Synthesis
├─ Combine insights từ both groups
├─ Resolve conflicts
├─ Create comprehensive requirements
└─ Validate với both groups
```

### Exceptions

**Có thể phỏng vấn cùng khi:**
- Final review sessions
- Presentation của findings
- Validation meetings
- Sign-off meetings
- Conflict resolution (nếu cần)

**Nhưng NOT for:**
- Initial requirements gathering
- Detailed interviews
- Problem identification
- Day-to-day operations discussions

### Best Practices

**✅ DO:**
- Schedule separate interviews
- Respect each group's perspective
- Tailor questions appropriately
- Maintain confidentiality
- Synthesize inputs later

**❌ DON'T:**
- Combine interviews
- Let one group dominate
- Share sensitive information inappropriately
- Create uncomfortable situations
- Rush the interview process

---

### Câu 11: Ba loại information requirements cơ bản mà bạn phải xác định là gì?

**Đáp án:**

Ba loại information requirements cơ bản cần xác định là:

### 1. CURRENT Information Requirements

**Định nghĩa:**
- Thông tin mà tổ chức hiện đang cần và sử dụng
- Information currently received và used

**Đặc điểm:**
- ✅ Existing data needs
- ✅ Present-day operations
- ✅ Current reports và queries
- ✅ Active business processes

**Cách xác định:**
- Review existing reports
- Examine current data entry forms
- Interview về daily tasks
- Analyze current database usage

**Ví dụ:**
```
Current Requirements:
□ Customer contact information
□ Product inventory levels
□ Daily sales reports
□ Employee work schedules
□ Invoice generation
□ Order tracking
```

**Questions to ask:**
```
❓ "What information do you currently receive?"
❓ "How do you use this information daily?"
❓ "What reports do you run regularly?"
❓ "What data do you access most often?"
```

---

### 2. ADDITIONAL Information Requirements

**Định nghĩa:**
- Thông tin bổ sung mà tổ chức cần nhưng hiện CHƯA có
- Information needed to supplement current information

**Đặc điểm:**
- ✅ Missing from current system
- ✅ Would improve current operations
- ✅ Address current gaps
- ✅ Enhance existing processes

**Cách xác định:**
- Review reports với participants
- Ask about missing information
- Identify gaps in current data
- Listen for "I wish we had..." statements

**Ví dụ:**
```
Additional Requirements:
□ Customer email addresses (currently not tracked)
□ Vendor performance metrics (not available now)
□ Product profitability analysis (missing)
□ Employee skill certifications (not recorded)
□ Supplier lead times (not tracked)
```

**Questions to ask:**
```
❓ "What information is missing from this report?"
❓ "What would you like to add to improve this?"
❓ "What information do you wish you had?"
❓ "What would make your job easier?"
```

**Notes attached to reports:**
```
Example: On Product Inventory Report
"Can we include Vendor Name? It would make it easier 
to identify specific products."
→ Additional Requirement: Vendor Name
```

---

### 3. FUTURE Information Requirements

**Định nghĩa:**
- Thông tin mà tổ chức dự kiến sẽ cần khi phát triển
- Information needed as organization evolves

**Đặc điểm:**
- ✅ Anticipatory needs
- ✅ Based on growth plans
- ✅ Support future operations
- ✅ Speculative but important

**Cách xác định:**
- Discuss organization's evolution
- Consider growth plans
- Think about future scenarios
- Plan for expansion

**Ví dụ:**
```
Future Requirements:
□ Multi-location inventory tracking (planning to expand)
□ International customer data (entering new markets)
□ Product line extensions (new categories)
□ Advanced analytics (as data grows)
□ Mobile access (future workforce needs)
```

**Questions to ask:**
```
❓ "How will the organization evolve?"
❓ "What information will you need as you grow?"
❓ "How will expansion affect your data needs?"
❓ "What future capabilities do you envision?"
❓ "What will change in the next 2-5 years?"
```

**Considerations:**
- ⚠️ Answers based on speculation
- ⚠️ Cannot predict with 100% accuracy
- ✅ Better to prepare in advance
- ✅ Define flexible structures
- ✅ Plan for scalability

---

### Tại sao cả ba đều quan trọng?

**Current Requirements:**
- ✅ Ensure database meets TODAY's needs
- ✅ Don't lose existing functionality
- ✅ Maintain business continuity

**Additional Requirements:**
- ✅ Improve current operations
- ✅ Address known gaps
- ✅ Enhance business processes

**Future Requirements:**
- ✅ Prepare for growth
- ✅ Avoid costly redesigns
- ✅ Support organization's evolution
- ✅ Build scalable foundation

### Integration strategy

**Combine all three:**

```
Current Requirements
        ↓
Define core structures
        ↓
Additional Requirements
        ↓
Enhance structures
        ↓
Future Requirements
        ↓
Plan for flexibility
        ↓
COMPREHENSIVE DATABASE DESIGN
```

### Documentation

**For each requirement type, record:**
- ✅ Specific information needed
- ✅ Source (who needs it)
- ✅ Purpose (why needed)
- ✅ Frequency (when needed)
- ✅ Priority (importance)

**Example documentation:**
```
Requirement: Customer Email Address
Type: Additional
Source: Marketing Department
Purpose: Email campaigns, customer communication
Frequency: Daily use
Priority: High
Notes: Currently missing from system
```

---

### Câu 12: Preliminary Field List là gì?

**Đáp án:**

**Preliminary Field List** là danh sách liệt kê các yêu cầu dữ liệu cơ bản (fundamental data requirements) của tổ chức và thiết lập core set của các fields mà bạn phải định nghĩa trong database.

### Đặc điểm chính

**1. Fundamental Data Requirements**
- Represents organization's BASIC data needs
- Core information tổ chức MUST track
- Foundation cho database structure
- Essential fields only (không có calculated fields)

**2. Starting Point for Design**
- Beginning của field definition process
- Will be refined later
- Subject to changes
- Not final but foundational

**3. Derived From**
- ✅ Characteristics list (từ interviews)
- ✅ Data collection samples
- ✅ Information presentation samples
- ✅ User và management input
- ✅ Current, additional, future requirements

### Cách tạo Preliminary Field List

**Process:**

```
Step 1: Compile characteristics list
        ↓
Step 2: Review all samples
        ↓
Step 3: Identify fields from samples
        ↓
Step 4: Combine với characteristics
        ↓
Step 5: Create complete field list
        ↓
Step 6: SEPARATE calculated fields
        ↓
Step 7: Result = Preliminary Field List
```

**What to include:**
- ✅ Single-value fields
- ✅ Atomic fields (không thể decompose)
- ✅ Non-calculated fields
- ✅ Distinct characteristics

**What to EXCLUDE:**
- ❌ Calculated fields → Move to Calculated Field List
- ❌ Multipart fields → Decompose first
- ❌ Multivalued fields → Separate
- ❌ Concatenated values → Break apart

### Ví dụ Preliminary Field List

**Example:**
```
PRELIMINARY FIELD LIST
As of: [Date]

CUSTOMER-RELATED:
□ Customer ID
□ Customer First Name
□ Customer Last Name
□ Customer Street Address
□ Customer City
□ Customer State
□ Customer Zip Code
□ Customer Phone Number
□ Customer Email Address
□ Customer Type
□ Customer Birth Date

PRODUCT-RELATED:
□ Product ID
□ Product Name
□ Product Description
□ Product Category
□ Unit Price
□ Quantity On Hand
□ Reorder Level
□ Supplier ID

ORDER-RELATED:
□ Order Number
□ Order Date
□ Customer ID
□ Shipping Address
□ Order Status
□ Payment Method
□ Shipping Method

EMPLOYEE-RELATED:
□ Employee ID
□ Employee First Name
□ Employee Last Name
□ Employee Position
□ Employee Department
□ Employee Hire Date
□ Employee Phone
□ Employee Email
```

### Naming conventions

**Requirements cho field names:**

**1. Unique (Duy nhất)**
- Mỗi field MUST have unique name
- Không duplicate names
- Avoid confusion
- Clear identification

**2. Descriptive (Mô tả rõ ràng)**
- Name indicates purpose
- Self-explanatory
- Meaningful to users
- No cryptic abbreviations

**3. Clear (Rõ ràng)**
- No ambiguity
- Easy to understand
- Consistent terminology
- Full words preferred

**Good examples:**
```
✅ Customer Last Name
✅ Product Unit Price
✅ Order Date
✅ Employee Hire Date
```

**Bad examples:**
```
❌ CustLN (cryptic abbreviation)
❌ Name (ambiguous - whose name?)
❌ Price (ambiguous - which price?)
❌ Date (ambiguous - which date?)
```

### Relationship với other lists

**Preliminary Field List connects to:**

**1. Calculated Field List**
```
Preliminary Field List ← Non-calculated fields
Calculated Field List ← Calculated fields

Example separation:
Preliminary: Unit Price, Quantity
Calculated: Item Total (Unit Price × Quantity)
```

**2. Subjects List**
```
Subjects → Help organize fields
Fields → Will be assigned to tables (subjects)
```

**3. Characteristics List**
```
Characteristics → Become fields
Fields → Refined characteristics
```

### Review process

**Review với users và management:**

**Goals:**
- ✅ Verify completeness
- ✅ Confirm accuracy
- ✅ Identify missing fields
- ✅ Remove unnecessary fields
- ✅ Refine field names

**Questions during review:**
```
❓ "Are any fields missing?"
❓ "Are all fields necessary?"
❓ "Are field names clear?"
❓ "Do you understand each field's purpose?"
❓ "Should any fields be added or removed?"
```

**Revisions:**
- Add missing fields
- Remove unnecessary fields
- Rename unclear fields
- Document changes
- Date each version

### Importance

**Why Preliminary Field List matters:**

**1. Foundation for database**
- Core data requirements
- Starting point for design
- Guides structure decisions

**2. Communication tool**
- Common understanding
- Clear documentation
- Reference for discussions

**3. Design progress**
- Moves process forward
- Enables next steps
- Supports table definition

**4. Validation mechanism**
- Ensures nothing overlooked
- Confirms requirements
- Verifies completeness

### Next steps after Preliminary Field List

**Use list to:**
1. Define tables (subjects)
2. Assign fields to tables
3. Define field specifications
4. Establish relationships
5. Continue design process

---

### Câu 13: Nêu lý do tại sao mỗi item trong Preliminary Field List nên có tên duy nhất.

**Đáp án:**

Mỗi field trong Preliminary Field List phải có **unique name** (tên duy nhất) vì những lý do quan trọng sau:

### 1. Tránh nhầm lẫn (Avoid Confusion)

**Vấn đề khi không unique:**
```
❌ Bad Example:
   Name (in Customers table)
   Name (in Products table)
   Name (in Employees table)

→ Question: "Update the Name field" - Which one?
→ Confusion in discussions
→ Errors in implementation
```

**Giải pháp với unique names:**
```
✅ Good Example:
   Customer Name
   Product Name
   Employee Name

→ Clear: "Update the Customer Name field"
→ No confusion
→ Precise communication
```

### 2. Dễ dàng tham chiếu (Easy Reference)

**Benefits:**
- ✅ Clear identification trong discussions
- ✅ Precise communication với team
- ✅ Accurate documentation
- ✅ Unambiguous requirements

**Example conversation:**
```
Without unique names:
Person 1: "We need to add the Address field"
Person 2: "Which address - customer or supplier?"
→ Requires clarification

With unique names:
Person 1: "We need to add Customer Shipping Address"
Person 2: "Got it!" 
→ Immediate understanding
```

### 3. Rõ ràng về mục đích (Clear Purpose)

**Unique names reveal:**
- What entity the field belongs to
- What data it contains
- How it should be used

**Example:**
```
✅ Customer Email Address
   → Clearly for customers
   → Contains email
   → Used for customer communication

✅ Employee Email Address
   → Clearly for employees
   → Contains email
   → Used for internal communication
```

### 4. Tránh lỗi kỹ thuật (Prevent Technical Errors)

**Database implementation issues:**

**Problem without unique names:**
```
Table: CUSTOMERS
Fields: Name, Address, Phone

Table: SUPPLIERS  
Fields: Name, Address, Phone

When joining tables:
SELECT Name, Address FROM Customers, Suppliers
→ ERROR: Ambiguous column names!
```

**Solution with unique names:**
```
Table: CUSTOMERS
Fields: Customer_Name, Customer_Address, Customer_Phone

Table: SUPPLIERS
Fields: Supplier_Name, Supplier_Address, Supplier_Phone

When joining tables:
SELECT Customer_Name, Supplier_Name 
FROM Customers, Suppliers
→ Works perfectly!
```

### 5. Hỗ trợ bảo trì database (Support Maintenance)

**Long-term benefits:**
- ✅ Easier to modify structure
- ✅ Clearer impact analysis
- ✅ Simpler to debug issues
- ✅ Faster to implement changes

**Example scenario:**
```
Request: "Change the Phone field to 15 characters"

Without unique names:
→ Which Phone field? (Customer, Employee, Supplier?)
→ All of them or specific one?
→ Need additional clarification

With unique names:
Request: "Change Customer_Phone to 15 characters"
→ Immediately clear
→ Can implement right away
→ No confusion about scope
```

### 6. Cải thiện documentation (Better Documentation)

**Clear specifications:**
```
✅ FIELD SPECIFICATION

Field Name: Customer Email Address
Description: Email address for customer communications
Parent Table: CUSTOMERS
Data Type: Text
Length: 255

vs.

❌ FIELD SPECIFICATION

Field Name: Email
Description: Email address
Parent Table: ??? (Which table?)
→ Unclear and incomplete
```

### 7. Facilitate team collaboration (Hỗ trợ làm việc nhóm)

**Multiple people working:**
- Database designer
- Developers
- Testers
- Users
- Management

**Unique names ensure:**
- ✅ Everyone refers to same field
- ✅ No miscommunication
- ✅ Consistent understanding
- ✅ Efficient collaboration

### 8. Hỗ trợ field specifications (Support Specs)

**Field specification benefits:**
```
With unique names:
- Specifications are unambiguous
- Easy to reference
- Clear ownership
- Simple to validate

Example:
Field Name: Product_Unit_Price
→ Clearly: Price of product per unit
→ Not: Total price, discount price, or cost
```

### Naming conventions best practices

**To ensure uniqueness:**

**1. Include subject/table name:**
```
✅ Customer_Name
✅ Product_Name
✅ Employee_Name
```

**2. Be specific about type:**
```
✅ Customer_Billing_Address
✅ Customer_Shipping_Address
(not just "Address")
```

**3. Indicate purpose:**
```
✅ Employee_Hire_Date
✅ Product_Discontinue_Date
(not just "Date")
```

**4. Avoid generic names:**
```
❌ ID, Name, Date, Phone, Address
✅ Customer_ID, Customer_Name, Order_Date, 
   Customer_Phone, Customer_Address
```

### Verification checklist

**Check your Preliminary Field List:**

□ Each field name appears only ONCE?
□ No two fields have same name?
□ Each name clearly identifies what it represents?
□ Names include context (subject/table)?
□ No ambiguous or generic names?
□ Easy to understand for all stakeholders?

**If any answer is NO:**
→ Revise field names immediately!

---

### Câu 14: Value list là gì?

**Đáp án:**

**Value list** (còn gọi là **enumerated list**) là một danh sách chỉ định phạm vi giá trị được phép (acceptable range of values) cho một field cụ thể trong Preliminary Field List.

### Định nghĩa chi tiết

**Value list:**
- List các giá trị hợp lệ cho một field
- Defines permitted values
- Establishes constraints
- Helps enforce business rules

### Mục đích và lợi ích

**1. Đảm bảo Data Consistency**
```
Without value list:
Customer_Type field có thể chứa:
- "Regular"
- "regular"
- "Reg"
- "REGULAR"
- "Normal"
→ Inconsistent data!

With value list:
Customer_Type MUST be one of:
□ Regular
□ Preferred
□ Gold
→ Consistent data!
```

**2. Enforce Business Rules**
- Implement organizational policies
- Restrict invalid entries
- Maintain data quality
- Support business logic

**3. Prevent Data Entry Errors**
- Reduce typos
- Eliminate invalid values
- Guide users
- Improve accuracy

**4. Improve Data Integrity**
- Valid values only
- No garbage data
- Clean database
- Reliable information

### Khi nào cần Value List?

**Create value list when:**

✅ **Field has finite set of values**
```
Example: Order_Status
□ Pending
□ Processing
□ Shipped
□ Delivered
□ Cancelled
```

✅ **Values must be standardized**
```
Example: Product_Category
□ Accessories
□ Components
□ Bikes
□ Clothing
□ Parts
```

✅ **Business rules require specific values**
```
Example: Employee_Status
□ Full-Time
□ Part-Time
□ Contract
□ Intern
```

✅ **Values rarely change**
```
Example: Customer_Type
□ Individual
□ Business
□ Government
□ Non-Profit
```

### Ví dụ Value Lists

**Example 1: Order Status**
```
FIELD: Order_Status
VALUE LIST:
□ Pending - Order received, not yet processed
□ Processing - Order being prepared
□ Shipped - Order sent to customer
□ Delivered - Order received by customer
□ Cancelled - Order cancelled by customer/system
□ Returned - Order returned by customer
```

**Example 2: Payment Method**
```
FIELD: Payment_Method
VALUE LIST:
□ Cash
□ Credit Card
□ Debit Card
□ Bank Transfer
□ PayPal
□ Check
```

**Example 3: Priority Level**
```
FIELD: Priority_Level
VALUE LIST:
□ Low
□ Normal
□ High
□ Urgent
□ Critical
```

**Example 4: Employee Department**
```
FIELD: Employee_Department
VALUE LIST:
□ Sales
□ Marketing
□ Engineering
□ Human Resources
□ Finance
□ Operations
□ Customer Service
```

**Example 5: Product Size**
```
FIELD: Product_Size
VALUE LIST:
□ XS - Extra Small
□ S - Small
□ M - Medium
□ L - Large
□ XL - Extra Large
□ XXL - Extra Extra Large
```

### Khi KHÔNG nên dùng Value List

**Avoid value lists when:**

❌ **Values are unlimited or unpredictable**
```
Example: Customer_Name
→ Cannot list all possible names
→ New names constantly added
```

❌ **Values change frequently**
```
Example: Product_Price
→ Prices change often
→ Not practical to maintain list
```

❌ **Values are numeric ranges**
```
Example: Quantity_On_Hand
→ Any number from 0 to max
→ Not a discrete list
```

❌ **Values are dates or timestamps**
```
Example: Order_Date
→ Any valid date
→ Cannot enumerate
```

❌ **Values are unique identifiers**
```
Example: Customer_ID
→ Each value is unique
→ No repeating set
```

### Implementation approaches

**How to use value lists:**

**1. Database constraints**
```sql
CREATE TABLE Orders (
    Order_ID INT PRIMARY KEY,
    Order_Status VARCHAR(20) CHECK (
        Order_Status IN ('Pending', 'Processing', 
                        'Shipped', 'Delivered', 'Cancelled')
    )
);
```

**2. Lookup/validation tables**
```
Table: ORDER_STATUS_TYPES
Status_Code | Status_Name    | Description
-----------+----------------+------------------
PEN        | Pending        | Order received
PRO        | Processing     | Being prepared
SHP        | Shipped        | Sent to customer
DEL        | Delivered      | Received
CAN        | Cancelled      | Cancelled
```

**3. Application-level validation**
- Dropdown lists
- Radio buttons
- Checkboxes
- Validation rules

### Documentation

**How to document value lists:**

**Format:**
```
FIELD: [Field_Name]
DESCRIPTION: [What field represents]

VALUE LIST:
□ Value1 - Description of when to use
□ Value2 - Description of when to use
□ Value3 - Description of when to use

NOTES:
- Any special considerations
- Business rules associated
- Frequency of changes
```

**Example documentation:**
```
FIELD: Customer_Type
DESCRIPTION: Classification of customer based on 
              purchase history and relationship

VALUE LIST:
□ Regular - Standard customer, no special benefits
□ Preferred - Loyal customer, 10% discount
□ Silver - High-value customer, 15% discount
□ Gold - Premium customer, 20% discount, priority service
□ Platinum - VIP customer, 25% discount, dedicated rep

NOTES:
- Customer type affects pricing and service level
- Automatically upgraded based on purchase volume
- Review and update annually
- Cannot downgrade below Regular
```

### Relationship với Business Rules

**Value lists often support business rules:**

```
Business Rule: "Orders can only be shipped if 
                payment is confirmed"

Supporting value list:
Order_Status values:
□ Pending (awaiting payment)
□ Payment_Confirmed (ready to ship)
□ Shipped (payment confirmed, order sent)

Rule enforced by limited status transitions
```

### Maintenance

**Managing value lists:**

**1. Review regularly**
- Are values still relevant?
- Need to add new values?
- Can obsolete values be removed?

**2. Version control**
- Track changes to lists
- Document reasons for changes
- Maintain history

**3. Communication**
- Notify users of changes
- Update documentation
- Train on new values

**4. Backward compatibility**
- Consider existing data
- Plan migration if needed
- Avoid breaking changes

### Benefits summary

**Value lists provide:**
- ✅ Data consistency
- ✅ Data integrity
- ✅ Business rule enforcement
- ✅ User guidance
- ✅ Error prevention
- ✅ Quality assurance
- ✅ Clear documentation
- ✅ Standardization

---

### Câu 15: Calculated fields là gì? Bạn nên làm gì với chúng (nếu có)?

**Đáp án:**

**Calculated fields** là các fields chứa giá trị là kết quả của:
1. **String concatenations** (nối chuỗi)
2. **Mathematical expressions** (biểu thức toán học)

### Định nghĩa chi tiết

**Calculated field characteristics:**
- ❌ NOT stored in database (không lưu trữ)
- ✅ Computed when needed (tính toán khi cần)
- ✅ Based on other fields (dựa trên fields khác)
- ✅ Values can be derived (giá trị có thể suy ra)

### Loại Calculated Fields

**1. String Concatenation (Nối chuỗi)**

**Definition:** Combining text values from multiple fields

**Examples:**
```
Full_Name = First_Name + " " + Last_Name
→ "John" + " " + "Smith" = "John Smith"

Full_Address = Street + ", " + City + ", " + State + " " + Zip
→ "123 Main St" + ", " + "Seattle" + ", " + "WA" + " " + "98101"
→ "123 Main St, Seattle, WA 98101"

Product_Code = Category + "-" + Product_ID
→ "BIKE" + "-" + "001" = "BIKE-001"

Employee_Email = First_Name + "." + Last_Name + "@company.com"
→ "john" + "." + "smith" + "@company.com"
→ "john.smith@company.com"
```

**2. Mathematical Expression (Biểu thức toán học)**

**Definition:** Performing calculations on numeric values

**Examples:**
```
Item_Total = Unit_Price × Quantity
→ $25.00 × 3 = $75.00

Subtotal = SUM(Item_Total)
→ $75.00 + $50.00 + $30.00 = $155.00

Discount_Amount = Subtotal × Discount_Rate
→ $155.00 × 0.10 = $15.50

Tax_Amount = Subtotal × Tax_Rate
→ $155.00 × 0.08 = $12.40

Grand_Total = Subtotal - Discount_Amount + Tax_Amount
→ $155.00 - $15.50 + $12.40 = $151.90

Average_Price = Total_Price ÷ Quantity
→ $100.00 ÷ 4 = $25.00

Profit_Margin = (Selling_Price - Cost_Price) ÷ Selling_Price × 100
→ ($50 - $30) ÷ $50 × 100 = 40%
```

### Bạn nên làm GÌ với Calculated Fields?

### ⚠️ CRITICAL: Separate from Preliminary Field List

**Action required:**
1. **IDENTIFY** all calculated fields
2. **REMOVE** from Preliminary Field List
3. **CREATE** separate Calculated Field List
4. **DOCUMENT** calculation logic

### Tại sao phải tách riêng?

**1. Data Redundancy (Dư thừa dữ liệu)**

```
❌ Bad Practice - Storing calculated value:

ORDERS table:
Order_ID | Unit_Price | Quantity | Item_Total (stored)
---------|-----------|----------|-------------------
001      | $25.00    | 3        | $75.00

Problem: Item_Total is redundant
→ Can be calculated: Unit_Price × Quantity
→ Wastes storage space
→ Can become inconsistent
```

**If Unit_Price changes to $30:**
```
❌ Inconsistency risk:
Order_ID | Unit_Price | Quantity | Item_Total
---------|-----------|----------|------------
001      | $30.00    | 3        | $75.00 (WRONG!)

Should be: $30.00 × 3 = $90.00
```

**✅ Good Practice - Calculate when needed:**
```
ORDERS table:
Order_ID | Unit_Price | Quantity
---------|-----------|----------
001      | $30.00    | 3

Calculate in query:
SELECT Order_ID, Unit_Price, Quantity,
       (Unit_Price * Quantity) AS Item_Total
FROM Orders

Result always correct: $90.00
```

**2. Data Integrity Issues**

**Problems when storing calculated values:**
- ❌ Can become out of sync
- ❌ Need to update múltiple places
- ❌ Risk of inconsistency
- ❌ Difficult to maintain
- ❌ Violates normalization

**Example problem:**
```
Customer changed quantity from 3 to 5:

If stored:
→ Must update Quantity: 3 → 5
→ Must update Item_Total: $75.00 → $125.00
→ Risk: Forget to update Item_Total
→ Result: Inconsistent data

If calculated:
→ Only update Quantity: 3 → 5
→ Item_Total automatically correct: $125.00
→ No risk of inconsistency
```

**3. Flexibility**

**Calculated fields are flexible:**
```
Change calculation logic easily:

Original: Item_Total = Unit_Price × Quantity
Updated: Item_Total = Unit_Price × Quantity × (1 - Discount)

If stored: Must recalculate ALL existing records
If calculated: Just change query, instant effect
```

### Tạo Calculated Field List

**Format:**
```
CALCULATED FIELD LIST
As of: [Date]

FIELD: Item_Total
CALCULATION: Unit_Price × Quantity
SOURCE FIELDS: Unit_Price, Quantity
DESCRIPTION: Total cost for line item

FIELD: Subtotal
CALCULATION: SUM(Item_Total)
SOURCE FIELDS: Item_Total
DESCRIPTION: Sum of all line items before discount/tax

FIELD: Discount_Amount
CALCULATION: Subtotal × Discount_Rate
SOURCE FIELDS: Subtotal, Discount_Rate
DESCRIPTION: Dollar amount of discount

FIELD: Tax_Amount
CALCULATION: (Subtotal - Discount_Amount) × Tax_Rate
SOURCE FIELDS: Subtotal, Discount_Amount, Tax_Rate
DESCRIPTION: Sales tax on discounted subtotal

FIELD: Grand_Total
CALCULATION: Subtotal - Discount_Amount + Tax_Amount
SOURCE FIELDS: Subtotal, Discount_Amount, Tax_Amount
DESCRIPTION: Final amount due

FIELD: Full_Name
CALCULATION: First_Name + " " + Last_Name
SOURCE FIELDS: First_Name, Last_Name
DESCRIPTION: Customer's complete name

FIELD: Full_Address
CALCULATION: Street + ", " + City + ", " + State + " " + Zip
SOURCE FIELDS: Street, City, State, Zip
DESCRIPTION: Complete mailing address
```

### Khi NÀO có thể store calculated values?

**Rare exceptions (very specific cases):**

**1. Performance optimization**
```
Scenario: Calculation very complex and slow
Example: Aggregating millions of records

Consider storing IF:
- Calculation takes >2 seconds
- Value doesn't change often
- Performance critical
- Have update mechanism in place
```

**2. Historical snapshots**
```
Scenario: Need to preserve exact values at point in time
Example: Invoice total at time of sale

Store because:
- Unit prices may change later
- Tax rates may change
- Discounts may expire
- Need exact historical record
```

**3. Audit requirements**
```
Scenario: Legal/compliance requires exact values
Example: Tax calculations for financial reporting

Store to:
- Meet regulatory requirements
- Provide audit trail
- Ensure reproducibility
```

**⚠️ Important:** Even in these cases:
- Document why stored
- Implement update mechanisms
- Maintain consistency checks
- Consider trade-offs carefully

### Implementation trong Database Design

**Where to handle calculated fields:**

**1. Database Views**
```sql
CREATE VIEW Order_Details_View AS
SELECT 
    Order_ID,
    Product_ID,
    Unit_Price,
    Quantity,
    (Unit_Price * Quantity) AS Item_Total
FROM Order_Items;
```

**2. Queries**
```sql
SELECT 
    Customer_Name,
    First_Name + ' ' + Last_Name AS Full_Name,
    SUM(Order_Amount) AS Total_Purchases
FROM Customers;
```

**3. Application Layer**
```javascript
// Calculate in application code
function calculateTotal(unitPrice, quantity, discountRate) {
    const subtotal = unitPrice * quantity;
    const discount = subtotal * discountRate;
    return subtotal - discount;
}
```

**4. Reports**
- Calculate when generating report
- Display computed values
- No storage needed

### Review với Users and Management

**When reviewing Calculated Field List:**

**Questions to ask:**
```
❓ "Is this calculation correct?"
❓ "Are the source fields available?"
❓ "Is the logic clear and documented?"
❓ "Should this be calculated or stored?"
❓ "Will this calculation change in the future?"
```

**Validation checklist:**
□ Calculation logic is correct
□ All source fields identified
□ Formula documented clearly
□ Business rules incorporated
□ Edge cases considered
□ Performance acceptable

### Summary: What to do với Calculated Fields

**✅ DO:**
1. ✅ Identify all calculated fields
2. ✅ Remove from Preliminary Field List
3. ✅ Create separate Calculated Field List
4. ✅ Document calculation formulas
5. ✅ Identify source fields
6. ✅ Review with stakeholders
7. ✅ Implement in views/queries/application
8. ✅ Keep list updated

**❌ DON'T:**
1. ❌ Store in database (usually)
2. ❌ Mix with regular fields
3. ❌ Leave undocumented
4. ❌ Forget source fields
5. ❌ Ignore in design process

**Result:**
- Clean Preliminary Field List (only stored fields)
- Well-documented Calculated Field List
- Clear understanding of all fields
- Proper database design
- Maintained data integrity

---

## 🎯 TÓM TẮT CHƯƠNG 6

### Điểm chính cần nhớ

1. **Mục đích phân tích:**
    - Hiểu database hiện tại
    - Xác định structural deficiencies
    - Chuẩn bị cho database mới

2. **Quy tắc vàng:**
    - KHÔNG bao giờ copy cấu trúc database cũ

3. **Ba bước phân tích:**
    - Review data collection
    - Review information presentation
    - Conduct interviews

4. **Kỹ thuật quan trọng:**
    - Subject-Identification Technique
    - Characteristic-Identification Technique
    - Open-ended và Closed questions

5. **Phỏng vấn:**
    - Users: Chi tiết vận hành
    - Management: Strategic information
    - RIÊNG BIỆT, không cùng lúc

6. **Kết quả cuối:**
    - Preliminary Field List (core fields)
    - Calculated Field List (computed fields)
    - Value Lists (valid values)

### Checklist hoàn thành

□ Đã review all data collection samples
□ Đã review all information presentation samples
□ Đã conduct user interviews
□ Đã conduct management interviews
□ Đã tạo subjects list
□ Đã tạo characteristics list
□ Đã tạo Preliminary Field List
□ Đã tạo Calculated Field List
□ Đã tạo Value Lists (nếu cần)
□ Đã review với stakeholders
□ Đã document tất cả findings

---

## 📚 TÀI LIỆU THAM KHẢO

**Nguồn:** Database Design for Mere Mortals, 25th Anniversary Edition
**Chương:** Chapter 6 - Analyzing the Current Database
**Tác giả:** Michael J. Hernandez

---

**Ngày tạo:** [Current Date]
**Version:** 1.0
**Status:** Complete

---

*Tài liệu này tổng hợp toàn bộ kiến thức quan trọng từ Chương 6, bao gồm các khái niệm, kỹ thuật, quy trình và câu hỏi ôn tập đầy đủ. Sử dụng như tài liệu học tập và ôn thi.*