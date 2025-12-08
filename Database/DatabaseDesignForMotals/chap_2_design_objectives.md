# CHƯƠNG 2: DESIGN OBJECTIVES (MỤC TIÊU THIẾT KẾ)

## Tổng quan
Chương này đặt nền móng về tư tưởng và phương pháp luận cho toàn bộ quá trình thiết kế cơ sở dữ liệu quan hệ.

---

## 1. TẠI SAO CẦN QUAN TÂM ĐẾN THIẾT KẾ CƠ SỞ DỮ LIỆU?

### Vấn đề chính
- **Thiết kế kém = Thông tin không chính xác** (hậu quả nghiêm trọng nhất)
- Ảnh hưởng trực tiếp đến hoạt động và định hướng của tổ chức

### Sai lầm thường gặp
- Chỉ dựa vào công cụ thiết kế tự động của RDBMS
- Sao chép và sửa đổi database mẫu mà không hiểu thiết kế
- Sử dụng các công cụ trước khi tạo cấu trúc logic

### So sánh với xây nhà
Giống như việc xây nhà tùy chỉnh:
- Không thuê thợ xây ngay mà không có thiết kế
- Phải thuê kiến trúc sư thiết kế trước
- **Database cũng vậy**: Thiết kế trước, triển khai sau

---

## 2. TẦM QUAN TRỌNG CỦA LÝ THUYẾT

### Nền tảng toán học
- Mô hình cơ sở dữ liệu quan hệ dựa trên lý thuyết toán học
- Tạo nên cấu trúc vững chắc và đáng tin cậy
- Đảm bảo tính nhất quán trong thiết kế

### Ý nghĩa thực tiễn
Lý thuyết không chỉ là học thuật mà là nền tảng để:
- Hiểu được "tại sao" đằng sau các quy tắc thiết kế
- Áp dụng đúng các nguyên tắc trong thực tế
- Tránh được các lỗi phổ biến

---

## 3. LỢI ÍCH CỦA VIỆC HỌC PHƯƠNG PHÁP THIẾT KẾ TỐT

### Lợi ích chính
✅ **Cấu trúc hiệu quả và đáng tin cậy**
- Database được tổ chức logic
- Dữ liệu nhất quán và chính xác

✅ **Tiết kiệm thời gian**
- Giảm thời gian thiết kế
- Tránh phải thiết kế lại nhiều lần

✅ **Tránh vấn đề điển hình**
- Không bị dữ liệu dư thừa
- Không gặp vấn đề về data integrity
- Không phải sửa lỗi sau này

✅ **Hiểu RDBMS sâu hơn**
- Biết tại sao RDBMS cung cấp các công cụ nhất định
- Sử dụng RDBMS hiệu quả hơn

### So sánh
**KHÔNG có phương pháp:**
- Thiết kế theo kiểu thử-sai
- Lãng phí thời gian
- Thiếu logic và tổ chức

**CÓ phương pháp:**
- Có hướng dẫn rõ ràng
- Không lặp lại các bước không cần thiết
- Quy trình logic và có tổ chức

---

## 4. CÁC MỤC TIÊU CỦA THIẾT KẾ TỐT

### Mục tiêu 1: Hỗ trợ truy xuất thông tin
- Database phải lưu trữ dữ liệu cần thiết cho yêu cầu thông tin đã xác định
- Phải hỗ trợ **cả truy vấn ad hoc** (truy vấn tùy ý của người dùng)

### Mục tiêu 2: Bảng được xây dựng đúng và hiệu quả
Mỗi bảng phải:
- ✓ Đại diện cho **một chủ đề duy nhất**
- ✓ Gồm các trường **tương đối riêng biệt**
- ✓ **Giảm thiểu dữ liệu dư thừa** xuống mức tối thiểu
- ✓ Được xác định bởi **trường có giá trị duy nhất** (primary key)

### Mục tiêu 3: Data Integrity ở nhiều cấp độ
Đảm bảo tính toàn vẹn ở:
- **Field level**: Ràng buộc ở cấp trường
- **Table level**: Ràng buộc ở cấp bảng
- **Relationship level**: Ràng buộc ở mối quan hệ giữa các bảng

Mục đích: Đảm bảo cấu trúc và giá trị dữ liệu luôn hợp lệ và chính xác

### Mục tiêu 4: Hỗ trợ Business Rules
- Dữ liệu phải cung cấp thông tin **hợp lệ và chính xác**
- Thông tin luôn **có ý nghĩa với tổ chức**
- Phản ánh đúng các quy tắc nghiệp vụ

### Mục tiêu 5: Dễ mở rộng trong tương lai
- Cấu trúc database dễ sửa đổi
- Dễ mở rộng khi yêu cầu thay đổi và phát triển
- Không cần thiết kế lại từ đầu

### ⚠️ Lưu ý quan trọng
> "Đôi khi khó đạt được tất cả các mục tiêu này, nhưng khi đạt được, bạn sẽ rất hài lòng với cấu trúc database cuối cùng."

---

## 5. LỢI ÍCH CỦA THIẾT KẾ TỐT

### Lợi ích 1: Cấu trúc dễ sửa đổi và bảo trì
- Sửa đổi field, table hoặc relationship không ảnh hưởng xấu đến các phần khác
- Thay đổi cấu trúc một cách an toàn

### Lợi ích 2: Dữ liệu dễ thay đổi
- Thay đổi giá trị của một trường không ảnh hưởng đến các trường khác
- Giảm thiểu trường trùng lặp
- Thường chỉ cần sửa một giá trị ở một nơi

### Lợi ích 3: Thông tin dễ truy xuất
- Tạo query dễ dàng
- Bảng được xây dựng tốt
- Mối quan hệ giữa các bảng được thiết lập đúng
- Mối quan hệ rõ ràng ngay cả khi không được enforce

### Lợi ích 4: Ứng dụng người dùng dễ phát triển
- Dành nhiều thời gian cho lập trình
- Tập trung vào xử lý dữ liệu
- Không phải xử lý các vấn đề do thiết kế kém gây ra

### 💡 Kết luận về lợi ích
> "Thời gian đầu tư vào thiết kế database tốt là thời gian được sử dụng hiệu quả. Thiết kế tốt tiết kiệm thời gian về lâu dài vì bạn không phải liên tục sửa lại cấu trúc được thiết kế nhanh và kém."

---

## 6. PHƯƠNG PHÁP THIẾT KẾ TRUYỀN THỐNG

### Ba giai đoạn chính

#### Giai đoạn 1: Requirements Analysis (Phân tích yêu cầu)
- Nghiên cứu nghiệp vụ đang được mô hình hóa
- Phỏng vấn người dùng và quản lý
- Đánh giá hệ thống hiện tại
- Phân tích nhu cầu tương lai
- Đánh giá yêu cầu thông tin cho toàn tổ chức

#### Giai đoạn 2: Data Modeling (Mô hình hóa dữ liệu)
Sử dụng các phương pháp:
- **Entity-Relationship (ER) Diagrams**
- Semantic-Object Modeling
- Object-Role Modeling
- UML Modeling

Mục đích: Biểu diễn trực quan các khía cạnh của cấu trúc database:
- Bảng (tables)
- Mối quan hệ giữa các bảng
- Đặc điểm của mối quan hệ

Ví dụ ER Diagram cơ bản:
```
Agents ----1:N---- Clients
(Một agent quản lý nhiều clients)
```

#### Giai đoạn 3: Normalization (Chuẩn hóa)
- Áp dụng các quy tắc chuẩn hóa
- Đảm bảo cấu trúc database được tối ưu
- Loại bỏ dư thừa và bất thường

### Đặc điểm của phương pháp truyền thống
- Phức tạp và khó học
- Mất thời gian để nắm vững
- Yêu cầu kiến thức chuyên sâu

---

## 7. PHƯƠNG PHÁP TRONG CUỐN SÁCH NÀY

### Điểm khác biệt

#### ✨ Ưu điểm
- **Rõ ràng và dễ hiểu**: Viết bằng ngôn ngữ đơn giản (plain English)
- **Dễ thực hiện**: Hướng dẫn từng bước cụ thể
- **Tích hợp normalization**: Không tách biệt mà tích hợp vào quy trình
- **Kết quả tương đương**: Cho ra cấu trúc fully normalized như phương pháp truyền thống

#### 📋 Phương pháp tích hợp
Thay vì tách biệt 3 giai đoạn, cuốn sách:
- Tích hợp data modeling vào quy trình thiết kế
- Giới thiệu và giải thích kỹ thuật modeling khi cần thiết
- Kết hợp normalization một cách tự nhiên

### ⚠️ NGUYÊN TẮC QUAN TRỌNG

> **Phương pháp này chỉ cho ra cấu trúc fully normalized NẾU bạn tuân thủ nó một cách trung thành.**

**KHÔNG ĐƯỢC:**
- ❌ Cắt ngắn quy trình (shortcut)
- ❌ Phá vỡ quy trình (circumvent)
- ❌ Giảm nhẹ tầm quan trọng (de-emphasize)
- ❌ Bỏ qua bất kỳ phần nào (omit)

**PHẢI:**
- ✅ Thực hiện **cẩn thận** (diligently)
- ✅ Thực hiện **có phương pháp** (methodically)
- ✅ Thực hiện **đầy đủ** (completely)

---

## 8. NORMALIZATION (CHUẨN HÓA)

### Định nghĩa
Normalization là một quy trình toán học:
- Đảm bảo mỗi bảng trong database được cấu trúc đúng
- Áp dụng một loạt các quy tắc (normal forms)
- Loại bỏ dữ liệu dư thừa và các bất thường

### Trong cuốn sách này
- Không giải thích chi tiết lý thuyết normalization
- Tích hợp các nguyên tắc normalization vào phương pháp thiết kế
- Giải thích chi tiết hơn trong **Appendix G: "On Normalization"**

### Lợi ích của cách tiếp cận này
- Không cần học lý thuyết phức tạp trước
- Áp dụng normalization một cách tự nhiên
- Vẫn đạt được kết quả fully normalized

---

## 9. NGUYÊN TẮC VÀNG

### Câu nói nổi tiếng
> **"There's never time to do it right, but there's always time to do it over!"**
>
> *(Không bao giờ có thời gian để làm đúng, nhưng luôn có thời gian để làm lại!)*

### Ý nghĩa
- Đừng vội vàng và cắt ngắn quy trình thiết kế
- Kiên nhẫn và làm đúng từ đầu
- Chi phí sửa lại sau này sẽ lớn hơn nhiều

### Quy luật quan trọng
📊 **Mức độ toàn vẹn của database ∝ Mức độ tuân thủ quy trình thiết kế**

Nghĩa là:
- Càng ít thời gian cho thiết kế → Càng nhiều rủi ro gặp vấn đề
- Tuân thủ đầy đủ quy trình → Giảm thiểu vấn đề tối đa

### Lời khuyên
- Thiết kế database **KHÔNG KHÓ**
- Chỉ cần **chút thời gian** để thiết kế đúng
- **Đừng bao giờ** cắt ngắn quy trình dù có vẻ mất nhiều thời gian

---

## 10. TÓM TẮT CHƯƠNG 2

### Các điểm chính cần nhớ

1. **Thiết kế là quan trọng**: Ảnh hưởng trực tiếp đến tính toàn vẹn và chính xác của dữ liệu

2. **Lý thuyết là nền tảng**: Mô hình quan hệ dựa trên toán học, tạo nên độ tin cậy

3. **Phương pháp luận là cần thiết**: Học và sử dụng một phương pháp thiết kế tốt

4. **5 mục tiêu thiết kế**: Hỗ trợ truy xuất, bảng hiệu quả, data integrity, business rules, dễ mở rộng

5. **Lợi ích rõ ràng**: Dễ sửa đổi, dữ liệu dễ thay đổi, dễ truy xuất, dễ phát triển ứng dụng

6. **Phương pháp truyền thống**: Phức tạp nhưng hiệu quả (Requirements → Modeling → Normalization)

7. **Phương pháp của sách**: Đơn giản, dễ hiểu, tích hợp, hiệu quả

8. **Tuân thủ đầy đủ**: Không được bỏ qua bất kỳ bước nào

### Câu hỏi ôn tập quan trọng

1. Khi nào là thời điểm tốt nhất để sử dụng các công cụ thiết kế của RDBMS?
    - **Đáp án**: Sau khi đã tạo cấu trúc logic của database

2. Hậu quả nghiêm trọng nhất của thiết kế kém là gì?
    - **Đáp án**: Thông tin không chính xác

3. Tại sao phải tuân thủ phương pháp thiết kế?
    - **Đáp án**: Để đảm bảo cấu trúc fully normalized và tránh vấn đề

---

## 📚 CHUẨN BỊ CHO CHƯƠNG TIẾP THEO

Trước khi bắt đầu quy trình thiết kế, cần học một số thuật ngữ cơ bản.

**Chương 3** sẽ giới thiệu các thuật ngữ này.

---

*Tài liệu được tổng hợp từ: Database Design for Mere Mortals, 25th Anniversary Edition (2020) - Michael J. Hernandez*