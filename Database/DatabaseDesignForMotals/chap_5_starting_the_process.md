# 📚 CHƯƠNG 5: BẮT ĐẦU QUY TRÌNH THIẾT KẾ DATABASE

> *"Where shall I begin, please your Majesty?" he asked. "Begin at the beginning," the King said gravely, "and go on till you come to the end: then stop."* — Lewis Carroll, Alice's Adventures in Wonderland

---

## 🎯 MỤC TIÊU CHƯƠNG

Chương này giúp bạn:
- Hiểu tầm quan trọng của việc phỏng vấn trong quá trình thiết kế
- Định nghĩa **Mission Statement** (Tuyên bố Sứ mệnh) cho database
- Xác định **Mission Objectives** (Mục tiêu Sứ mệnh)
- Áp dụng các kỹ thuật phỏng vấn hiệu quả

---

## 📋 NỘI DUNG CHI TIẾT

### 1️⃣ **CONDUCTING INTERVIEWS** (Tiến hành Phỏng vấn)

#### 🔑 Tại sao phỏng vấn quan trọng?

Phỏng vấn cung cấp **kênh giao tiếp quan trọng** giữa:
- Database designer (người thiết kế)
- Users (người dùng)
- Management (quản lý)

**Lợi ích của phỏng vấn:**
- Đảm bảo thành công cho quá trình thiết kế
- Cung cấp thông tin quan trọng ảnh hưởng đến cấu trúc database
- Giúp xác định nhu cầu thông tin thực tế của tổ chức

#### 📝 Lưu ý đặc biệt về COVID-19 & Remote Work

Cuốn sách phiên bản 4 có cập nhật về việc **làm việc từ xa (WFH)** và **họp online** đã trở nên phổ biến, điều này ảnh hưởng đến cách tiến hành phỏng vấn trong quá trình thiết kế database.

---

#### 🎤 CÁC LOẠI CÂU HỎI

##### **Open-Ended Questions** (Câu hỏi mở)

- **Đặc điểm:** Khuyến khích người trả lời đưa ra phản hồi chi tiết, mô tả đầy đủ
- **Khi nào sử dụng:** Khi cần thu thập thông tin tổng quan, hiểu rõ về công việc hàng ngày

**Ví dụ:**
```
- "What kind of work do you perform on a daily basis?"
  (Bạn thực hiện loại công việc gì hàng ngày?)

- "How would you define your job description?"
  (Bạn định nghĩa công việc của mình như thế nào?)

- "What kind of data do you work with?"
  (Bạn làm việc với loại dữ liệu nào?)

- "What types of reports do you generate?"
  (Bạn tạo ra những loại báo cáo nào?)

- "How would you describe the type of work you do?"
  (Bạn mô tả công việc của mình như thế nào?)
```

##### **Closed Questions** (Câu hỏi đóng)

- **Đặc điểm:** Yêu cầu câu trả lời ngắn gọn, cụ thể (Yes/No hoặc thông tin đơn giản)
- **Khi nào sử dụng:** Khi cần xác nhận chi tiết cụ thể hoặc làm rõ thông tin

**Ví dụ:**
```
- "Do you maintain customer information?"
  (Bạn có duy trì thông tin khách hàng không?)

- "How many employees work in your department?"
  (Có bao nhiêu nhân viên làm việc trong phòng ban của bạn?)
```

---

#### 👥 PARTICIPANT GUIDELINES (Hướng dẫn cho Người tham gia)

Những điều người tham gia phỏng vấn cần biết:

1. **Tập trung vào công việc của bạn**
   - Mô tả nhiệm vụ hàng ngày
   - Giải thích quy trình làm việc
   - Chia sẻ về dữ liệu bạn sử dụng

2. **Đừng lo lắng về thuật ngữ kỹ thuật**
   - Sử dụng ngôn ngữ thông thường
   - Database designer sẽ chuyển đổi sang thuật ngữ kỹ thuật

3. **Chuẩn bị các mẫu tài liệu**
   - Reports (báo cáo)
   - Forms (biểu mẫu)
   - Spreadsheets (bảng tính)
   - Documents liên quan khác

4. **Trả lời đầy đủ và chi tiết**
   - Đừng giả định interviewer đã biết
   - Giải thích rõ ràng mọi khía cạnh

---

#### 🎯 INTERVIEWER GUIDELINES (Hướng dẫn cho Người phỏng vấn)

##### **Quy tắc vàng: LUÔN DUY TRÌ KIỂM SOÁT CUỘC PHỎNG VẤN**

**✅ Các nguyên tắc quan trọng:**

1. **Chuẩn bị kỹ lưỡng**
   - Lập danh sách câu hỏi trước
   - Nghiên cứu về tổ chức
   - Chuẩn bị tài liệu ghi chú

2. **Giới hạn số lượng người tham gia**
   - Tối đa 5-7 người cho mỗi phiên
   - Số người nhiều → mức độ запугивание tăng → thông tin kém chất lượng

3. **Phỏng vấn Users và Management riêng biệt**
   - **Users:** Tập trung vào công việc hàng ngày, chi tiết vận hành
   - **Management:** Tập trung vào tầm nhìn tổng thể, chiến lược

4. **Sử dụng open-ended questions chủ yếu**
   - Khuyến khích phản hồi chi tiết
   - Tạo cơ hội cho follow-up questions

5. **Ghi chú hiệu quả**
   - Ghi lại các câu trả lời dưới dạng câu hoàn chỉnh
   - Ghi chú những điểm quan trọng
   - Yêu cầu làm rõ khi cần thiết

6. **Lắng nghe chủ động**
   - Chú ý đến cả verbal và non-verbal cues
   - Đừng ngắt lời người trả lời
   - Cho phép họ suy nghĩ trước khi trả lời

7. **Giữ trọng tâm**
   - Đưa cuộc trò chuyện quay về chủ đề chính nếu lạc hướng
   - Tránh đi sâu vào chi tiết kỹ thuật quá sớm

---

### 2️⃣ **DEFINING THE MISSION STATEMENT** (Định nghĩa Tuyên bố Sứ mệnh)

#### 📌 Mission Statement là gì?

**Mission Statement** là một câu tuyên bố:
- Xác định **mục đích cụ thể** của database
- Được diễn đạt ở mức **tổng quát**
- Cung cấp **định hướng rõ ràng** cho toàn bộ quá trình thiết kế

> 💡 **Ẩn dụ:** Mission Statement giống như ngọn đuốc soi sáng đường hầm tối - nó dẫn dắt bạn đến cuối đường hầm (hoàn thành thiết kế database).

---

#### ✨ Đặc điểm của Mission Statement tốt

**✅ Một Mission Statement tốt phải:**

1. **Rõ ràng, không mơ hồ (Unambiguous)**
   - Dễ hiểu
   - Không gây nhầm lẫn

2. **Súc tích, đi thẳng vào vấn đề (Succinct and to the point)**
   - Ngắn gọn
   - Không dài dòng

3. **Không mô tả nhiệm vụ cụ thể**
   - Chỉ nói về MỤC ĐÍCH chung
   - Không đề cập đến các task chi tiết

---

#### 📝 Ví dụ Mission Statement

##### **❌ VÍ DỤ SAI:**

```
The purpose of the Whatcom County Hearing Examiner's database 
is to keep track of applications for land use, maintain data on 
applicants, keep a record of all hearings, keep a record of all 
decisions, keep a record of all appeals, maintain data on department 
employees, and maintain data for general office use.
```

**Vấn đề:**
- ❌ Quá dài dòng (verbose)
- ❌ Mục đích không rõ ràng
- ❌ Mô tả nhiều task cụ thể
- ❌ Tạo cảm giác "chưa đầy đủ"

##### **✅ VÍ DỤ ĐÚNG (Sửa lại):**

```
The purpose of the Whatcom County Hearing Examiner's database 
is to maintain the data the examiner's office uses to make 
decisions on land-use requests submitted by citizens of 
Whatcom County.
```

**Ưu điểm:**
- ✅ Mục đích rõ ràng
- ✅ Súc tích
- ✅ Không mô tả task cụ thể
- ✅ Hoàn chỉnh

---

#### 🔨 Quy trình xây dựng Mission Statement

**Bước 1: Phỏng vấn Owner/Manager**
- Người hiểu tổng quan về tổ chức
- Hiểu lý do cần database

**Bước 2: Tìm hiểu về tổ chức**
- Tổ chức làm gì?
- Tổ chức vận hành như thế nào?
- Vai trò của database trong tổ chức?

**Bước 3: Đặt câu hỏi mở**

Ví dụ câu hỏi tốt:
```
"How would you describe the purpose of your organization 
to a new client?"

(Bạn sẽ mô tả mục đích của tổ chức như thế nào với 
một khách hàng mới?)
```

**Bước 4: Phân tích câu trả lời**
- Tìm câu/cụm từ mô tả mục đích database
- Loại bỏ chi tiết không cần thiết
- Viết lại thành mission statement

**Bước 5: Xem xét và hoàn thiện**
- Review với owner/manager
- Đảm bảo mọi người hiểu và đồng ý
- Commit vào tài liệu

---

#### 🎯 VÍ DỤ THỰC TẾ: MIKE'S BIKES

**Câu trả lời của Mike:**
```
"To provide a wide array of bicycle products and bicycle-related 
services to our customers. We have a lot of great customers. 
And regular ones, too! They're our biggest asset."
```

**Mission Statement kết quả:**
```
The purpose of the Mike's Bikes database is to maintain the 
data we need to support our retail sales business and our 
customer service operations.
```

**Phân tích:**
- ✅ Rõ ràng về mục đích
- ✅ Súc tích
- ✅ Tập trung vào supporting business operations
- ✅ Không đề cập task cụ thể

---

### 3️⃣ **DEFINING THE MISSION OBJECTIVES** (Xác định Mục tiêu Sứ mệnh)

#### 📌 Mission Objectives là gì?

**Mission Objectives** là các câu tuyên bố:
- Đại diện cho **các nhiệm vụ tổng quát** (general tasks)
- Được hỗ trợ bởi dữ liệu trong database
- Mỗi objective = **MỘT nhiệm vụ duy nhất**

---

#### 🎯 Vai trò của Mission Objectives

Mission Objectives giúp:

1. **Định nghĩa cấu trúc table**
   - Xác định tables cần thiết
   - Xác định relationships giữa tables

2. **Định nghĩa field specifications**
   - Xác định fields trong mỗi table
   - Xác định data types và constraints

3. **Thiết lập data integrity**
   - Validation rules
   - Constraints

4. **Định nghĩa business rules**
   - Quy tắc nghiệp vụ cần implement

5. **Hướng dẫn việc phát triển**
   - Đảm bảo database hỗ trợ mission statement
   - Cung cấp roadmap cho quá trình thiết kế

6. **Xác định views cần thiết**
   - Các góc nhìn khác nhau về dữ liệu

---

#### ✨ Đặc điểm Mission Objective tốt

**✅ Một Mission Objective tốt phải:**

1. **Là câu tuyên bố (Declarative sentence)**
   - Định nghĩa rõ ràng một nhiệm vụ tổng quát
   - Không có chi tiết không cần thiết

2. **Được diễn đạt ở mức tổng quát (General terms)**
   - Không quá cụ thể
   - Không quá chi tiết kỹ thuật

3. **Súc tích và đi thẳng vào vấn đề**
   - Ngắn gọn
   - Rõ ràng

4. **Không mơ hồ (Unambiguous)**
   - Dễ hiểu
   - Không gây nhầm lẫn

---

#### 📝 Ví dụ Mission Objectives

##### **✅ VÍ DỤ TỐT:**

```
1. Maintain complete patient address information.
   (Duy trì đầy đủ thông tin địa chỉ bệnh nhân.)

2. Keep track of all customer sales.
   (Theo dõi tất cả doanh số bán hàng của khách hàng.)

3. Make sure an account representative is responsible for 
   no more than 20 accounts at any given time.
   (Đảm bảo một đại diện tài khoản chỉ chịu trách nhiệm 
   tối đa 20 tài khoản tại một thời điểm.)

4. Keep track of vehicle maintenance.
   (Theo dõi việc bảo trì xe.)

5. Produce employee phone directories.
   (Tạo danh bạ điện thoại nhân viên.)
```

**Phân tích:**
- ✅ Mỗi objective = 1 task
- ✅ Rõ ràng, dễ hiểu
- ✅ Không có chi tiết kỹ thuật
- ✅ Ở mức tổng quát

---

##### **❌ VÍ DỤ SAI:**

```
We need to keep track of the entertainers we represent and 
the type of entertainment they provide, as well as the 
engagements that we book for them.
```

**Vấn đề:**
1. ❌ **Nhiều hơn 1 task:**
   - Tracking entertainers
   - Tracking engagements

2. ❌ **Chi tiết không cần thiết:**
   - "type of entertainment" → nên là field hoặc objective riêng

##### **✅ CÁCH SỬA:**

```
1. Maintain complete entertainer information.
   (Duy trì đầy đủ thông tin về nghệ sĩ.)

2. Keep track of all the engagements we book.
   (Theo dõi tất cả các buổi biểu diễn chúng tôi đặt.)
```

---

#### 🔨 Quy trình xây dựng Mission Objectives

**Bước 1: Phỏng vấn Users và Management**
- Xác định các nhiệm vụ cần được hỗ trợ bởi database
- Tập trung vào level tổng quát, không phân tích chi tiết

**Bước 2: Đặt câu hỏi mở**

Ví dụ:
```
- "What kind of work do you perform on a daily basis?"
- "What kind of data do you work with?"
- "What types of reports do you generate?"
- "What types of things do you keep track of?"
- "What types of services does your organization provide?"
```

**Bước 3: Ghi chép câu trả lời**
- Ghi thành **câu hoàn chỉnh (declarative sentences)**
- Dễ chuyển đổi thành mission objectives

**Bước 4: Xác định subjects và tasks**

Sử dụng 2 kỹ thuật:
- **Subject-Identification Technique:** Xác định chủ thể (subjects)
- **Characteristic-Identification Technique:** Xác định đặc tính (characteristics)

**Bước 5: Viết Mission Objectives**

Có 2 cách:
- **Explicit (Tường minh):** Objectives xuất phát trực tiếp từ câu trả lời
- **Implicit (Ngầm định):** Objectives được suy luận từ câu trả lời

---

#### 🎯 VÍ DỤ THỰC TẾ: AUTO REPAIR SHOP

**Câu trả lời của nhân viên:**
```
"First, I try to determine the general problem with the vehicle. 
Then I fill out a work order and note my assessment of the problem. 
Finally, I send the vehicle to the next available service team."
```

**Mission Objectives rút ra:**

**Explicit (Tường minh):**
```
1. Maintain information on customer vehicles.
2. Keep track of work orders.
3. Maintain information on our service teams.
```

**Implicit (Ngầm định - được suy luận):**
```
4. Maintain information on our mechanics.
5. Maintain information on our customers.
```

**Follow-up question có thể hỏi:**
```
"Is there any type of customer information incorporated 
within the procedure you just described?"
```

---

#### 🎯 VÍ DỤ THỰC TẾ: MIKE'S BIKES

**Các câu hỏi đặt ra:**
```
You: "Can you give me an idea of the things you'd like 
      to track in the database?"

Mike: "Oh sure, that's pretty easy. I want to keep track of 
       our inventory, our customers, and our sales."

You: "Is there anything else that is related to these subjects?"

Mike: "Well, I guess if we're going to keep track of our inventory, 
       we should know who our suppliers are."

You: "What about the sales reps involved in each sale?"

Mike: "Oh yeah, we should definitely keep information about our 
       employees. If nothing else, it's a good idea to do this 
       from a human resources point of view."
```

**Mission Objectives kết quả:**
```
1. Maintain complete inventory information.
   (Duy trì đầy đủ thông tin hàng tồn kho.)

2. Maintain complete customer information.
   (Duy trì đầy đủ thông tin khách hàng.)

3. Track all customer sales.
   (Theo dõi tất cả doanh số bán hàng.)

4. Maintain complete supplier information.
   (Duy trì đầy đủ thông tin nhà cung cấp.)

5. Maintain complete employee information.
   (Duy trì đầy đủ thông tin nhân viên.)
```

---

#### ⚠️ Lưu ý quan trọng

**1. Mission Objectives có thể được bổ sung sau:**
- Trong quá trình thiết kế, có thể phát hiện thêm objectives mới
- Đừng lo lắng nếu ban đầu không đầy đủ 100%

**2. Tập trung vào tính tổng quát:**
- Không đi vào chi tiết kỹ thuật
- Không mô tả "HOW" (cách thực hiện)
- Chỉ mô tả "WHAT" (cái gì cần làm)

**3. Review với tất cả stakeholders:**
- Users phải hiểu
- Management phải đồng ý
- Database designer phải có thể sử dụng để thiết kế

---

### 4️⃣ **MỐI QUAN HỆ GIỮA MISSION STATEMENT VÀ MISSION OBJECTIVES**

```
┌─────────────────────────────────────────────┐
│        MISSION STATEMENT                    │
│  (Mục đích tổng thể của database)          │
└─────────────────────────────────────────────┘
                    │
                    │ hỗ trợ bởi
                    ↓
┌─────────────────────────────────────────────┐
│        MISSION OBJECTIVES                   │
│  (Các nhiệm vụ cụ thể database phải hỗ trợ)│
│                                             │
│  • Objective 1                              │
│  • Objective 2                              │
│  • Objective 3                              │
│  • ...                                      │
└─────────────────────────────────────────────┘
                    │
                    │ dẫn dắt việc định nghĩa
                    ↓
┌─────────────────────────────────────────────┐
│    CÁC CẤU TRÚC DATABASE                   │
│  • Tables                                   │
│  • Fields                                   │
│  • Relationships                            │
│  • Views                                    │
│  • Business Rules                           │
└─────────────────────────────────────────────┘
```

---

## 📊 TÓM TẮT CHƯƠNG 5

### ✅ Các điểm chính cần nhớ:

1. **Interviews là bước quan trọng đầu tiên**
   - Tạo kênh giao tiếp giữa designer, users, management
   - Sử dụng open-ended questions chủ yếu
   - Phỏng vấn users và management riêng biệt

2. **Mission Statement xác định mục đích database**
   - Phải rõ ràng, súc tích, không mơ hồ
   - Không mô tả tasks cụ thể
   - Cung cấp focus cho toàn bộ quá trình thiết kế

3. **Mission Objectives xác định các nhiệm vụ tổng quát**
   - Mỗi objective = 1 task
   - Diễn đạt ở mức general
   - Hỗ trợ mission statement

4. **Mission Statement + Mission Objectives = Nền tảng**
   - Định hướng cho toàn bộ quá trình thiết kế
   - Đảm bảo database đáp ứng được nhu cầu thực tế
   - Giúp xác định tables, fields, relationships, views

---

## 📝 CÂU HỎI ÔN TẬP VÀ ĐÁP ÁN

### **Câu 1: Why are interviews important?**
**Tại sao phỏng vấn quan trọng?**

**Đáp án:**
Interviews quan trọng vì:
- Cung cấp **kênh giao tiếp quan trọng** giữa database developer và người dùng database
- Giúp **đảm bảo thành công** cho quá trình thiết kế
- Cung cấp **thông tin quan trọng** có thể ảnh hưởng đến thiết kế cấu trúc database
- Giúp hiểu rõ nhu cầu thực tế của tổ chức

---

### **Câu 2: What problem can arise when you conduct an interview with a large number of people?**
**Vấn đề gì có thể phát sinh khi phỏng vấn với số lượng người lớn?**

**Đáp án:**
Vấn đề phát sinh là **mức độ e dè/intimidation** của một số người tham gia sẽ **tăng tỉ lệ thuận** với số lượng người tham gia trong cuộc phỏng vấn.

**Giải thích:** Càng nhiều người → càng e ngại → ít chia sẻ thông tin → chất lượng thông tin thu được kém.

**Khuyến nghị:** Giới hạn 5-7 người mỗi phiên phỏng vấn.

---

### **Câu 3: What is the primary reason for conducting separate interviews with users and management?**
**Lý do chính để phỏng vấn users và management riêng biệt?**

**Đáp án:**
Lý do chính là mỗi nhóm có **góc nhìn khác nhau** (different perspective) về:
- Tổ chức nói chung (organization as a whole)
- Cách tổ chức sử dụng dữ liệu hàng ngày (how the organization uses its data on a daily basis)

**Chi tiết:**
- **Users:** Tập trung vào công việc hàng ngày, chi tiết vận hành
- **Management:** Tập trung vào tầm nhìn chiến lược, quyết định cấp cao

---

### **Câu 4: True or False: You'll commonly use closed questions in your interviews.**
**Đúng hay Sai: Bạn sẽ thường xuyên sử dụng closed questions trong phỏng vấn.**

**Đáp án:** **FALSE** (SAI)

**Giải thích:**
Bạn sẽ **chủ yếu sử dụng OPEN-ENDED QUESTIONS** trong phỏng vấn vì:
- Open-ended questions khuyến khích câu trả lời chi tiết, mô tả đầy đủ
- Closed questions chỉ dùng để xác nhận chi tiết cụ thể hoặc làm rõ

---

### **Câu 5: What kind of responses should you try to evoke from the interview participants?**
**Loại phản hồi nào bạn nên cố gắng gợi ra từ người tham gia phỏng vấn?**

**Đáp án:**
Bạn nên cố gắng gợi ra **các phản hồi đầy đủ và mô tả chi tiết** (complete, descriptive responses) từ người tham gia phỏng vấn.

**Cách thực hiện:**
- Sử dụng open-ended questions
- Khuyến khích họ giải thích chi tiết
- Cho phép họ mở rộng câu trả lời

---

### **Câu 6: What is the single most important guideline for every interview you conduct?**
**Nguyên tắc quan trọng nhất cho mọi cuộc phỏng vấn bạn tiến hành?**

**Đáp án:**
Nguyên tắc quan trọng nhất là: **ALWAYS MAINTAIN CONTROL OF THE INTERVIEW** (LUÔN DUY TRÌ KIỂM SOÁT CUỘC PHỎNG VẤN)

**Nghĩa là:**
- Giữ cuộc phỏng vấn đúng hướng
- Không để cuộc trò chuyện đi chệch hướng
- Quản lý thời gian hiệu quả
- Đảm bảo thu thập được thông tin cần thiết

---

### **Câu 7: What is a mission statement?**
**Mission statement là gì?**

**Đáp án:**
Mission statement là **một tuyên bố xác định mục đích cụ thể của database ở mức tổng quát** (a statement that declares the specific purpose of the database in general terms).

**Đặc điểm:**
- Xác định WHY database tồn tại
- Cung cấp focus cho quá trình thiết kế
- Giúp đảm bảo database đáp ứng đúng mục đích

---

### **Câu 8: State two characteristics of a well-written mission statement.**
**Nêu 2 đặc điểm của một mission statement tốt.**

**Đáp án - Một mission statement tốt phải:**

1. **Unambiguous (Rõ ràng, không mơ hồ)**
   - Dễ hiểu, không gây nhầm lẫn

2. **Succinct and to the point (Súc tích và đi thẳng vào vấn đề)**
   - Ngắn gọn, không dài dòng

3. **Free of phrases or sentences that explicitly describe specific tasks**
   **(Không có cụm từ hoặc câu mô tả nhiệm vụ cụ thể)**
   - Chỉ nói về mục đích chung, không đề cập tasks chi tiết

*(Câu hỏi yêu cầu 2 đặc điểm nhưng có 3 đặc điểm chính, bạn chỉ cần trả lời 2 trong số đó)*

---

### **Câu 9: True or False: You need not learn about the organization to compose a mission statement.**
**Đúng hay Sai: Bạn không cần tìm hiểu về tổ chức để viết mission statement.**

**Đáp án:** **FALSE** (SAI)

**Giải thích:**
Bạn **PHẢI tìm hiểu về tổ chức** (must learn about the organization) để viết mission statement vì:
- Cần hiểu tổ chức làm gì
- Cần hiểu tổ chức hoạt động như thế nào
- Cần hiểu nhu cầu sử dụng database của tổ chức
- Thông tin này giúp bạn xác định đúng mục đích của database

---

### **Câu 10: When is your mission statement complete?**
**Khi nào mission statement của bạn hoàn thành?**

**Đáp án:**
Mission statement hoàn thành khi:
- Có **một câu mô tả mục đích cụ thể** của database
- **Mọi người liên quan đều hiểu và đồng ý** (understood and agreed on by everyone concerned)

**Chi tiết:**
- Owner/Manager đồng ý
- Database designer hiểu rõ
- Stakeholders đều chấp nhận
- Câu statement đáp ứng các tiêu chí của mission statement tốt

---

### **Câu 11: What is a mission objective?**
**Mission objective là gì?**

**Đáp án:**
Mission objective là **một tuyên bố đại diện cho một nhiệm vụ tổng quát duy nhất được hỗ trợ bởi dữ liệu duy trì trong database** (a statement that represents a single, general task supported by the data maintained in the database).

**Đặc điểm:**
- Mỗi objective = 1 task
- Được diễn đạt ở mức tổng quát
- Hỗ trợ mission statement

---

### **Câu 12: State two characteristics of a well-written mission objective.**
**Nêu 2 đặc điểm của một mission objective tốt.**

**Đáp án - Một mission objective tốt phải:**

1. **It is a declarative sentence that clearly defines a general task and is free from unnecessary details**
   **(Là câu tuyên bố định nghĩa rõ ràng một nhiệm vụ tổng quát và không có chi tiết không cần thiết)**

2. **It is expressed in general terms (Được diễn đạt ở mức tổng quát)**

3. **It is succinct and to the point (Súc tích và đi thẳng vào vấn đề)**

4. **It is unambiguous (Rõ ràng, không mơ hồ)**

*(Câu hỏi yêu cầu 2 đặc điểm nhưng có 4 đặc điểm chính, bạn chỉ cần trả lời 2 trong số đó)*

---

### **Câu 13: True or False: You should interview users and management to help you define mission objectives.**
**Đúng hay Sai: Bạn nên phỏng vấn users và management để giúp định nghĩa mission objectives.**

**Đáp án:** **TRUE** (ĐÚNG)

**Giải thích:**
Bạn **NÊN phỏng vấn cả users và management** vì:
- Users cung cấp thông tin về công việc hàng ngày, tasks cụ thể
- Management cung cấp tầm nhìn tổng thể, chiến lược
- Kết hợp cả hai góc nhìn giúp xác định đầy đủ mission objectives

---

### **Câu 14: How does the staff's daily work relate to the mission objectives?**
**Công việc hàng ngày của nhân viên liên quan như thế nào đến mission objectives?**

**Đáp án:**
Công việc hàng ngày của nhân viên liên quan đến mission objectives theo cách: **Nhiều tasks mà họ thực hiện sẽ trở thành mission objectives** (many of the tasks they perform will become mission objectives).

**Giải thích:**
- Phân tích công việc hàng ngày → Xác định tasks cần hỗ trợ
- Tasks này được chuyển thành mission objectives
- Mission objectives phản ánh nhu cầu thực tế của users

---

### **Câu 15: True or False: A mission objective can describe more than one task.**
**Đúng hay Sai: Một mission objective có thể mô tả nhiều hơn một task.**

**Đáp án:** **FALSE** (SAI)

**Giải thích:**
Một mission objective **KHÔNG THỂ mô tả nhiều hơn một task** (cannot describe more than one task).

**Nguyên tắc:**
- 1 mission objective = 1 task
- Nếu một statement mô tả nhiều tasks → Phải tách thành nhiều objectives riêng biệt

**Ví dụ:**
- ❌ SAI: "Track customers and their orders" (2 tasks)
- ✅ ĐÚNG:
   - "Maintain customer information" (1 task)
   - "Track customer orders" (1 task)

---

### **Câu 16: State two ways that a mission objective can be derived from a response.**
**Nêu 2 cách một mission objective có thể được rút ra từ câu trả lời.**

**Đáp án:**
Mission objective có thể được rút ra từ câu trả lời theo 2 cách:

1. **Explicitly (Tường minh)**
   - Mission objective xuất phát **trực tiếp** từ câu trả lời
   - Subjects được đề cập **rõ ràng** trong response
   - Ví dụ: "I track customer orders" → "Track customer orders"

2. **Implicitly (Ngầm định)**
   - Mission objective được **suy luận** từ câu trả lời
   - Subjects **được ngụ ý** nhưng không được đề cập trực tiếp
   - Dựa trên **assumptions** (giả định) từ context
   - Ví dụ: "I create work orders" → Ngụ ý phải có "Maintain customer information"

---

### **Câu 17: When is a mission objective complete?**
**Khi nào một mission objective hoàn thành?**

**Đáp án:**
Mission objective hoàn thành khi:

1. **Được định nghĩa đúng đắn (Properly defined)**
   - Đáp ứng các tiêu chí của mission objective tốt
   - Cấu trúc câu rõ ràng

2. **Được định nghĩa tốt (Well defined)**
   - Không mơ hồ
   - Súc tích, đầy đủ ý nghĩa

3. **Có ý nghĩa với bạn và những người bạn thiết kế database cho họ**
   **(Makes sense to you and to those for whom you are designing the database)**
   - Database designer hiểu
   - Users hiểu
   - Management đồng ý

**Tóm lại:** Mission objective hoàn thành khi nó vừa đúng về mặt kỹ thuật (properly & well defined) vừa có ý nghĩa thực tế (makes sense to stakeholders).

---

## 🎓 CHECKLIST HỌC TẬP

Sau khi học xong Chương 5, bạn cần:

- [ ] Hiểu tầm quan trọng của interviews trong database design
- [ ] Phân biệt được open-ended và closed questions
- [ ] Nắm được participant guidelines và interviewer guidelines
- [ ] Hiểu rõ Mission Statement là gì và vai trò của nó
- [ ] Biết cách viết một Mission Statement tốt
- [ ] Hiểu rõ Mission Objectives là gì và vai trò của chúng
- [ ] Biết cách viết các Mission Objectives tốt
- [ ] Hiểu mối quan hệ giữa Mission Statement và Mission Objectives
- [ ] Biết cách phỏng vấn để thu thập thông tin định nghĩa Mission Statement/Objectives
- [ ] Có thể phân biệt explicit và implicit mission objectives

---

## 💡 TIPS HỌC TẬP

1. **Thực hành viết Mission Statements:**
   - Tìm các database/system quen thuộc
   - Thử viết mission statement cho chúng
   - Đánh giá xem có đáp ứng tiêu chí không

2. **Phân tích các ví dụ:**
   - Đọc kỹ các ví dụ trong chương
   - Hiểu tại sao ví dụ tốt là tốt
   - Hiểu tại sao ví dụ xấu là xấu

3. **Luyện tập kỹ năng phỏng vấn:**
   - Thử vai người phỏng vấn với bạn bè
   - Thực hành đặt open-ended questions
   - Luyện ghi chú hiệu quả

4. **Kết nối với các chương khác:**
   - Chương 4: Conceptual Overview
   - Chương 6: Analyzing Current Database
   - Mission Statement/Objectives sẽ được sử dụng xuyên suốt quá trình thiết kế

---

## 🔗 KẾT NỐI VỚI CÁC CHƯƠNG KHÁC

**← Chương 4:** Conceptual Overview
- Giới thiệu tổng quan về Mission Statement và Mission Objectives

**→ Chương 6:** Analyzing the Current Database
- Sử dụng Mission Statement và Mission Objectives
- Phỏng vấn users và management để phân tích database hiện tại

**→ Chương 7:** Establishing Table Structures
- Mission Objectives giúp xác định tables

**→ Các chương sau:**
- Mission Objectives hỗ trợ định nghĩa fields, relationships, views, business rules

---

## 📌 THUẬT NGỮ QUAN TRỌNG (ENGLISH - VIETNAMESE)

| English | Vietnamese |
|---------|------------|
| Mission Statement | Tuyên bố Sứ mệnh |
| Mission Objective | Mục tiêu Sứ mệnh |
| Interview | Phỏng vấn |
| Open-ended question | Câu hỏi mở |
| Closed question | Câu hỏi đóng |
| Participant | Người tham gia |
| Interviewer | Người phỏng vấn |
| Stakeholder | Bên liên quan |
| General task | Nhiệm vụ tổng quát |
| Declarative sentence | Câu tuyên bố |
| Subject-Identification Technique | Kỹ thuật Xác định Chủ thể |
| Characteristic-Identification Technique | Kỹ thuật Xác định Đặc tính |
| Explicit | Tường minh |
| Implicit | Ngầm định |

---

**📅 Cập nhật:** Dựa trên "Database Design for Mere Mortals, 25th Anniversary Edition" (2020) - Michael J. Hernandez

**🔖 Chú thích:** Tài liệu này tổng hợp nội dung Chương 5, bao gồm lý thuyết, ví dụ, và câu hỏi ôn tập đầy đủ với đáp án chi tiết.