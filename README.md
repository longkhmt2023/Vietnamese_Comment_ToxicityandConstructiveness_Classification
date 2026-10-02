# Phân loại bình luận tiếng Việt: Độc hại và Tính xây dựng

## 1. Giới thiệu

Đồ án môn học **Xử lý ngôn ngữ tự nhiên (Natural Language Processing)**
tập trung xây dựng hệ thống phân loại bình luận tiếng Việt theo hai khía
cạnh:

-   **Tính độc hại (Toxicity):** xác định bình luận có độc hại hay
    không.
-   **Tính xây dựng (Constructiveness):** xác định bình luận có mang
    tính xây dựng hay không.

Hệ thống hỗ trợ dự đoán nhãn cho bình luận tiếng Việt và cung cấp giao
diện minh họa để người dùng thử nghiệm với nội dung tự nhập.

## 2. Dữ liệu

Đồ án sử dụng bộ dữ liệu **ViCTSD**, gồm 10.000 bình luận tiếng Việt,
được chia thành:

  Tập dữ liệu                           Số lượng
  --------------------------------- ------------
  Huấn luyện (`ViCTSD_train.csv`)          7.000
  Xác thực (`ViCTSD_valid.csv`)            2.000
  Kiểm tra (`ViCTSD_test.csv`)             1.000
  **Tổng cộng**                       **10.000**

Hai tác vụ phân loại sử dụng nhãn nhị phân:

-   **Toxicity:** `1` -- độc hại; `0` -- không độc hại.
-   **Constructiveness:** `1` -- có tính xây dựng; `0` -- không có tính
    xây dựng.

## 3. Phương pháp thực hiện

Quy trình xử lý và phân loại gồm các bước chính:

1.  **Tiền xử lý văn bản:** chuẩn bị bình luận tiếng Việt cho quá trình
    trích xuất đặc trưng.
2.  **Trích xuất đặc trưng:** sử dụng TF-IDF, bao gồm các đặc trưng
    n-gram.
3.  **Huấn luyện mô hình:** xây dựng mô hình phân loại cho hai tác vụ
    Toxicity và Constructiveness.
4.  **Đánh giá:** đánh giá kết quả trên dữ liệu kiểm tra bằng các chỉ số
    phù hợp.

## 4. Các mô hình

Đồ án có đề cập và hỗ trợ thử nghiệm các mô hình:

-   **Support Vector Machine (SVM):** mô hình chính được trình bày trong
    đồ án.
-   **Logistic Regression:** mô hình dùng để so sánh/thử nghiệm.
-   **LSTM:** mô hình học sâu được tích hợp trong phần minh họa.

## 5. Đánh giá mô hình

Các phương pháp đánh giá được sử dụng gồm:

-   Accuracy
-   Precision
-   Recall
-   F1-score
-   Confusion Matrix
-   Phân tích lề (margin) của mô hình SVM

Bộ dữ liệu có sự mất cân bằng nhãn, đặc biệt ở tác vụ Toxicity. Đây là
yếu tố cần lưu ý khi diễn giải các chỉ số đánh giá.

## 6. Ứng dụng minh họa

Ứng dụng cho phép người dùng:

-   Nhập một bình luận tiếng Việt.
-   Chọn mô hình để thực hiện dự đoán.
-   Xem kết quả phân loại Toxicity và Constructiveness.
-   Quan sát độ tin cậy dự đoán do ứng dụng cung cấp.

## 7. Phạm vi và giới hạn

Đồ án tập trung vào phân loại **văn bản bình luận tiếng Việt** theo hai
tiêu chí Toxicity và Constructiveness. Phạm vi không bao gồm dữ liệu
hình ảnh, âm thanh, video hoặc các tác vụ phân loại cảm xúc khác.
## 8. Cấu trúc thư mục

```text
.
├── NLP PROJECT.ipynb
├── lr_constructive_model.pkl
├── lr_toxicity_model.pkl
├── lstm_constructive_model.keras
├── lstm_toxicity_model.keras
├── svm_constructive_model.pkl
├── svm_toxicity_model.pkl
├── tfidf_vectorizer.pkl
└── tokenizer.pkl

## 9. Cách chạy

Các lệnh cài đặt thư viện và khởi chạy phụ thuộc vào cấu trúc repository
cũng như cách triển khai ứng dụng thực tế. Hãy bổ sung tại đây:

1.  Phiên bản Python và các yêu cầu môi trường.
2.  Lệnh cài đặt thư viện, ví dụ thông qua `requirements.txt`.
3.  Lệnh chạy notebook hoặc ứng dụng demo.

## 10. Thành viên thực hiện

  Họ và tên           MSSV
  ------------------- ----------
  Nguyễn Thành Long   23520886
  Phan Vũ Anh Tuấn    23521727
  Nguyễn Thanh Tuấn   23521724

## 11. Giảng viên hướng dẫn

**TS. Nguyễn Trọng Chỉnh**

## 12. Thông tin môn học

-   **Môn học:** Xử lý ngôn ngữ tự nhiên
-   **Mã lớp:** CS221.Q11
-   **Đơn vị:** Trường Đại học Công nghệ Thông tin -- Đại học Quốc gia
    TP. Hồ Chí Minh
