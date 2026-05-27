# Báo Cáo Bài Tập Kiểm Thử API Bằng Postman

**Sinh viên thực hiện:** Nguyễn Hữu Hưng
**Mã sinh viên:** 23010124
**Lớp/Môn học:** CSE703010-1-3-25(COUR01.LT3) - Đánh giá và kiểm định chất lượng phần mềm

---

## 1. Mục tiêu bài tập
* Tìm hiểu và sử dụng công cụ Postman (Phiên bản Web) để kiểm thử giao diện lập trình ứng dụng (API).
* Thực hành cấu hình HTTP Request (phương thức GET) và truyền tham số truy vấn (Query Parameters).
* Làm quen với Automation Test: Viết kịch bản kiểm thử tự động bằng JavaScript để bóc tách dữ liệu JSON và xác thực kết quả (Assertion).

## 2. API Thực Hành
Trong bài tập này, em sử dụng **MyMemory Translation API** - một Public API miễn phí chuyên hỗ trợ dịch thuật văn bản tự động.

* **Endpoint:** `GET https://api.mymemory.translated.net/get`
* **Tham số truyền vào (Query Params):** * `q`: Nội dung văn bản cần dịch (Ví dụ: *"đây là 1 câu tiếng việt"*)
  * `langpair`: Cặp ngôn ngữ nguồn và ngôn ngữ đích (Ví dụ: `vi|en` - Dịch từ tiếng Việt sang tiếng Anh)

## 3. Quá Trình Thực Hiện & Kết Quả

### 3.1. Gửi GET Request và Phân Tích Dữ Liệu
* **Mô tả thao tác:** Tiến hành thiết lập Request với các tham số tương ứng và gửi đi.
* **Kết quả:** Máy chủ (Server) đã phản hồi thành công với mã trạng thái `200 OK` trong thời gian nhanh chóng. Dữ liệu trả về là cấu trúc JSON chi tiết chứa nội dung đã được dịch thuật.
* **Ảnh minh họa quá trình lấy dữ liệu:**
  
<img width="1920" height="1080" alt="Screenshot 2026-05-27 164046" src="https://github.com/user-attachments/assets/9583026d-6845-4408-b23a-a4337c9ae722" />


### 3.2. Cấu Hình Kiểm Thử Tự Động (Test Automation)
* **Mô tả thao tác:** Viết một đoạn mã kịch bản (Script) tại thẻ `Tests` để Postman tự động xác thực 2 điều kiện:
  1. Mã trạng thái (Status code) bắt buộc phải là `200`.
  2. Bóc tách dữ liệu JSON theo đường dẫn cây `responseData.translatedText` và so sánh xem chuỗi trả về có chính xác khớp với `"this is a Vietnamese sentence"` hay không.
* **Kết quả:** Quá trình Test Automation chạy thành công. Cả 2 bài kiểm tra đều vượt qua (Trạng thái: **PASSED**).
* **Ảnh minh họa kết quả Test:**

<img width="1920" height="1080" alt="Screenshot 2026-05-27 163704" src="https://github.com/user-attachments/assets/c8dc11b7-9f2c-4751-91e4-e2314d4302b9" />


## 4. Tài Liệu Mở Rộng Tự Nghiên Cứu
Bên cạnh video bài giảng gốc, em đã tham khảo thêm các tài liệu sau để hoàn thành bài tập này:
* [Tài liệu chính thức API MyMemory](https://mymemory.translated.net/doc/spec.php) (Hiểu cấu trúc dữ liệu trả về).
* [Postman Learning Center - Intro to scripts](https://learning.postman.com/docs/writing-scripts/intro-to-scripts/) (Cách sử dụng biến `pm.response` và hàm `pm.expect` trong Postman).
