# Financial-Risk-Analytics-Solution
Dự án xây dựng hệ thống báo cáo Quản trị Rủi ro Tín dụng (Credit Risk Dashboard) trực quan trên nền tảng Power BI, xử lý dữ liệu của hơn 8,000 hồ sơ vay vốn
**Đối tượng sử dụng:** Ban Quản trị (C-Level) và Khối Thẩm định rủi ro (Risk Underwriters).
**Mục đích báo cáo:** Giám sát sức khỏe danh mục giải ngân và minh bạch hóa thuật toán phê duyệt tự động của hệ thống.

Mô hình dữ liệu được thiết kế theo chuẩn **Star Schema (Lược đồ hình sao)** với mối quan hệ 1-Many, bao gồm 1 bảng Fact trung tâm và các bảng Dimension vệ tinh để tối ưu hóa hiệu suất truy vấn DAX.

**1. Fact Table (Bảng Dữ liệu trung tâm)**
* `Fact_LoanApplications` *(hoặc tên bảng fact của bạn)*: Đây là trái tim của mô hình, lưu trữ hơn 8,000 dòng dữ liệu lịch sử hồ sơ. Chứa các chỉ số định lượng (Metrics) và khóa ngoại (Foreign Keys)

**2. Dimension Tables (Các bảng Danh mục phân tích)**
* `Dim_Customer`: Lưu trữ hồ sơ định danh và nhân khẩu học của khách hàng (Thu nhập, Cấp bậc học vấn, Trạng thái việc làm).
* `Dim_CreditProfile`: Bảng phân tích chuyên sâu về rủi ro tài chính của khách hàng (Điểm tín dụng, Điểm rủi ro, Tỉ lệ DTI, Lịch sử phá sản/Bùng nợ).
* `Dim_LoanProduct`: Phân loại các mục đích giải ngân của khoản vay (Home, Auto, Debt Consolidation...).

**Mối quan hệ dữ liệu:**
* Fact_LoanApplications -> Dim_Customer (Customer_ID)
* Fact_LoanApplications -> Dim_CreditProfile (CreditProfile_ID)
* Fact_LoanApplications -> Dim_LoanProduct (Product_ID)

Dashboard (Excutive Overview):
<img width="1388" height="846" alt="image" src="https://github.com/user-attachments/assets/c8b236dd-bc92-4d11-9c4e-90dc4cdfe014" />

Dashboard (Risk Intelligence):
<img width="1372" height="840" alt="image" src="https://github.com/user-attachments/assets/dab2168b-48d0-4830-b288-042bb6e4d719" />
