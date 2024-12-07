## 1. Làm rõ các yêu cầu dự án:
### Đảm bảo hiểu rõ các yêu cầu của dự án
	- Xác định các nhu cầu về chức năng của dự án
	- Xác định các nhu cầu về hiệu suất của dự án
### Ở giai đoạn này, nên liệt kê các hệ thống hiện có mà lib mà bạn đã chọn sẽ cần phải tương thích để ngăn ngừa các vấn đề trong tương lai khi dự án của bạn tiến triển.

## 2. Nghiên cứu các thư viện có sẵn:
- Bắt đầu lọc ra các thư viện Java không tương thích để tạo danh sách rút gọn
- Việc chọn đúng thư viện Java đòi hỏi phải nghiên cứu kỹ lưỡng
- Danh sách của bạn càng ngắn thì bạn càng có thể đưa ra quyết định nhanh hơn
link: https://mergebase.com/blog/java-libraries/

## 3. Đánh giá các cân nhắc về bảo mật của dự án:
- Bảo mật phải là một trong những ưu tiên hàng đầu của bạn khi chọn thư viện Java
- Xem lại hồ sơ theo dõi bảo mật của thư viện
- Đánh giá các biện pháp quản lý lỗ hổng bảo mật và đảm bảo tuân thủ các tiêu chuẩn ngành, chẳng hạn như các tiêu chuẩn do OWASP

## 4. Đánh giá hiệu quả hoạt động của từng lib:
- Hiệu quả: Phân tích khả năng xử lý vấn đề của từng lib
- Hiệu xuất: Phân tích mức tiêu thụ tài nguyên của từng lib
- Xem xét khả năng mở rộng tiềm năng của từng lib để đảm bảo rằng nó sẽ hoạt động lâu dài cho dự án

## 5. Kiểm tra loại giấy phép của thư viện (và do đó cân nhắc về mặt pháp lý):
- Đảm bảo bạn hiểu loại giấy phép của thư viện
- Đánh giá khả năng tương thích với mọi giấy phép hiện có liên quan đến dự án
- Xem xét các tác động pháp lý tiềm ẩn của việc chọn loại giấy phép (và liệu nó có ảnh hưởng đến những cân nhắc pháp lý hiện tại của bạn hay không)
- Giấy phép nguồn mở quy định các điều khoản sử dụng và việc vi phạm chúng có thể dẫn đến các khoản phạt nặng và thiệt hại về mặt danh tiếng

## 6. Đảm bảo nó cung cấp các tích hợp và khả năng tương thích phù hợp cho dự án:
- Đánh giá mức độ dễ tích hợp với cơ sở mã hiện có của bạn để đảm bảo khả năng tương thích với các lib hoặc frameworks khác
- Việc xác minh sớm khả năng tương tác với môi trường phát triển của bạn trong quá trình ra quyết định sẽ hợp lý hóa quá trình tích hợp và giảm thiểu mọi vấn đề tương thích tiềm ẩn làm tăng nguy cơ xảy ra lỗ hổng bảo mật

## 7. Xem xét sự hỗ trợ của cộng đồng và tài liệu có sẵn cho mỗi thư viện:
- Khi đánh giá các thư viện Java khác nhau, đừng đánh giá thấp tầm quan trọng của sự hỗ trợ cộng đồng mạnh mẽ và tài liệu toàn diện.
- Sự tham gia tích cực của cộng đồng và cập nhật kịp thời cho thấy một hệ sinh thái lành mạnh ưu tiên bảo mật và độ tin cậy, điều này sẽ cực kỳ thuận lợi cho sự thành công của dự án của bạn

## 8. Test and validate in controlled environments:
- Khi bạn đã thu hẹp các tùy chọn thư viện Java của mình xuống còn hai hoặc ba đối thủ => conduct thorough testing in a controlled environment
- Xem xét các tình huống sử dụng trong thế giới thực và các trường hợp khó khăn
- Bằng cách tiến hành kiểm tra và xác thực nghiêm ngặt, bạn có thể phát hiện các lỗ hổng hoặc sự cố tiềm ẩn trước khi chúng tác động đến môi trường sản xuất của mình


*Việc chọn đúng thư viện Java sẽ tác động trực tiếp đến tính bảo mật và tính toàn vẹn của cơ sở mã của bạn, khiến nó trở thành một trong những quyết định quan trọng nhất quyết định sự thành công của dự án.*

# Dependency hell:
- *Đôi khi sẽ là vấn đề nếu một ứng dụng chỉ sử dụng một phần nhỏ của một thư viện lớn (có thể giải quyết bằng cách tái cấu trúc mã)*
- *Đôi khi, trong chuỗi dài các phần dependencies này, xung đột nảy sinh khi cần có hai phiên bản khác nhau của cùng một gói(khi có thể, vấn đề này sẽ được giải quyết bằng cách cho phép cài đặt đồng thời các phần phụ thuộc khác nhau)*
- *Đôi khi, Nếu app1 phụ thuộc vào libfoo 1.2 và app2 phụ thuộc vào libfoo 1.3 và không thể cài đặt đồng thời các phiên bản libfoo khác nhau thì không thể sử dụng đồng thời app1 và app2*

- *Đôi khi, Nếu App A phụ thuộc và không thể chạy nếu không có phiên bản cụ thể của App B, nhưng App B lại phụ thuộc và không thể chạy nếu không có phiên bản cụ thể của App A, thì việc nâng cấp bất kỳ App nào sẽ làm hỏng App khác.
 Tác động của nó có thể khá nặng nề nếu ảnh hưởng đến hệ thống cốt lõi*
- Ví dụ: trình quản lý gói (A), yêu cầu run-time library (B) cụ thể để hoạt động, (A) có thể tự hỏng giữa quá trình khi nâng cấp thư viện (B) này sang version tiếp theo



**Question: Làm sao để đánh giá vừa nhanh vừa rõ ràng rằng 1 dependencies có nên dùng trong dự án hay không?**


