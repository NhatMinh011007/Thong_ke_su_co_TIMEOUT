THỐNG KÊ SỰ CỐ TIMEOUT   
Yêu cầu   
 -Tìm file log →Tìm file TIMEOUT → Lọc file  → Đếm kết quả  
1. Giới thiệu  
 -Bài học giúp bạn làm chủ PowerShell Pipeline (|) để xử lý                          tệp log tự động bằng một dòng lệnh duy nhất. Khác với CMD/Bash truyền văn bản, PowerShell truyền đối tượng (object), giúp bạn lọc chính xác sự cố TIMEOUT (tránh nhầm lẫn với NOT TIMEOUT) và lấy ngay con số tổng bằng thuộc tính .Count.   
2. Phân tích & giải pháp  
   -Phân tích vấn đề:  
Mục tiêu: Xuất ra con số tổng duy nhất về số sự cố TIMEOUT từ tệp log.  
Thách thức: Tránh lọc nhầm các dòng chứa NOT TIMEOUT.  
Giải pháp: Dùng Pipeline một dòng để đọc tệp  lọc điều kiện loại trừ NOT TIMEOUT  truy xuất .Count từ object kết quả.  
3. So sánh & Kết luận ( GB + PS )  
   So sánh:  
 -Git Bash và PowerShell vận hành rất khác nhau. Git Bash hoạt động trên (text stream) qua các đường ống dẫn. Do đó, việc xử lý các từ khóa phủ định đòi hỏi người dùng phải kết hợp các công cụ phức tạp, và thao tác đếm số lượng kết quả phụ thuộc hoàn toàn vào các tiện ích bên ngoài như wc -l.  
   
-PowerShell mang lại sự dễ dàng với cấu trúc (object stream). Nhờ vậy, cso thể dễ dàng sử dung dòng lệnh phủ định dễ dàng hơn ví dụ: Where-Object kết hợp -notmatch, đếm kết quả  chỉ cần gom hết vào trong ngoặc (..).count là xong  
   
Kết luận  
Git Bash: Thích hợp nếu bạn quen thuộc với Linux/Unix, cú pháp ngắn gọn (grep, wc) nhưng xử lý dựa trên văn bản.  
PowerShell: Tối ưu hơn trên Windows nhờ khả năng truyền object, giúp thao tác với thuộc tính dữ liệu (.Count) ngắn gọn xúc tích dễ hiểu.  
   
   
   
   
   
   
   
   
   
   
   
   
