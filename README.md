MÔN: Phát triển ứng dụng với mã nguồn mở-TEE0421
Họ và tên: Hoàng Đức Hội
MSSV: K225480106085
Lớp: K58KTP
Bài tập 4:

KHAI THÁC N8N ĐỂ TỰ ĐỘNG ĐĂNG BÀI LÊN WORDPRESS

thời hạn : 23h59 ngày 25 tháng 5 năm 2026.

SỬ DỤNG KẾT THÚC QUẢ ĐÀ Ở BÀI TẬP 3, BỔ SUNG VÀO DOCKER COMPOSE ĐỂ CÓ THÊM DỊCH VỤ 8N8:

Cấu hình các tập tin trong dokcer-compose.yml:

Mariadb:

hình ảnh

Quản trị viên PhPA:

hình ảnh

WordPress:

hình ảnh

Cấu hình Tunel cloudflare để truy cập các dịch vụ bằng các tên miền phụ ( em sử dụng lệnh cli thay vì thao tác đồ họa trên bảng điều khiển của cloudflare):


Tạo 3 subdomain:

hình ảnh

hình ảnh


Thêm chuỗi id tunel vào config.yml:

hình ảnh
Cấu hình dịch vụ cloudflare trong docker-compose.yml:

hình ảnh

Cấp lại quyền truy cập tệp trên máy chủ:

hình ảnh
n8n:
hình ảnh

Kéo các hình ảnh về và chạy chúng:
hình ảnh
Kiểm tra quyền truy cập các tên miền phụ:
Truy cập sub-domain2 để khảo sát xem cơ sở dữ liệu chưa có bảng nào:
hình ảnh
Truy cập subdomain1 để cài đặt wordpress:
hình ảnh
Truy cập sub-domain2 để khảo sát cơ sở dữ liệu có những dữ liệu bảng nào sau khi cài đặt wp:
hình ảnh
Tạo 1 bài viết trong wordpress giới thiệu về bản thân sinh viên: thông tin cá nhân, sở hữu, ... bài viết có thể chứa hình ảnh, âm thanh, video, ...
hình ảnh
Tạo 1 bài viết trong wordpress giới thiệu về nhữn kiến ​​thức mà em đã học được ở môn Phát triển ứng dụng với mã nguồn mở
hình ảnh
Truy cập subdomain3 để cấu hình n8n:
Tạo tài khoản quản trị viên:
hình ảnh
Cấu hình n8n:
Hãy gửi cho tôi mã bản quyền:
hình ảnh

Kiểm tra email:
hình ảnh

Kích hoạt License key: ( trang chủ -> cài đặt -> cách sử dụng và gói -> nhập key kích hoạt -> điền key vừa nhận từ email vào):
hình ảnh

Tạo quy trình làm việc mới:
hình ảnh

Thêm nút kích hoạt: nút tìm: Telegram => OnMessage ; cấu hình Thông tin xác thực: Thiết lập Thông tin xác thực => cần nhập Access Token

Cần trò chuyện với bot @BotFather trên Telegram để sinh ra bot mới của riêng mình:
hình ảnh
Sau khi tạo bot mới để sao chép mã thông báo
hình ảnh
hình ảnh
Trò chuyện lần đầu với bot mới này:
hình ảnh
hình ảnh
Thêm nút (nối tiếp vào sau nút Telegram Trigger): AI Google Gemini => Nhắn tin cho mô hình => Thiết lập thông tin xác thực => cần nhập API KEY

Lấy API KEY tại trang: https://aistudio.google.com
hình ảnh

Nhập API Key lên giao diện n8n:
hình ảnh

kéo theo nội dung đã chat với bot của telegram (phía bên trái) vào nội dung phần PROMPT kết quả được {{ $json.message.text }}, cần nhập thêm vào sau {{ $json.message.text }} để quảng cáo dài hơn : vd ({{ $json.message.text }}. Kết quả sinh ra ở dạng HTML+CSS định dạng để tôi sử dụng HTML+CSS này để tạo bài viết cho wordpress.)
hình ảnh

Bật Nội dung đầu ra dưới dạng JSON : để trả kết quả về dạng json
hình ảnh

Add Option to AI write bài thông minh hơn, văn phong nhiều màu hơn thay vì những văn bản chứa nội dung cứng ngắc:
hình ảnh

Nút Add (nối tiếp vào sau Message a model): Code in JavaScript
hình ảnh

Thêm nút (nối tiếp vào sau nút Code in JavaScript): WordPress => Create a Post

Set up Credential: vào wp tại url: https://sub-domain1/wp-admin => vào mục Tài khoản => chọn người dùng đã tạo lúc setup wordpress => Mật khẩu ứng dụng => Nhập n8n và "Thêm mật khẩu ứng dụng" => sao chép chuỗi 24 ký tự : Đây là mật khẩu ứng dụng => dán vào mục Mật khẩu của n8n Credential
hình ảnh
hình ảnh

Quay lại n8n:
hình ảnh

Nút cấu hình Tạo một bài đăng: nhấn nút Thực thi các nút trước đó sau đó thực hiện các bước trong ảnh:
hình ảnh

PUBLISH flow (góc trên phải) Nút này thực hiện công việc xuất bản flow <=> flow sẽ tự động thực thi khi đủ điều kiện kích hoạt
hình ảnh

Kết quả: Em sẽ để video demo kết quả ở link youtube bên dưới file
Nhận xét kết quả đạt được:
Triển khai thành công Stack mở mã nguồn dịch vụ bao gồm MariaDB, phpMyAdmin, WordPress và n8n chạy cài đặt trên môi trường Docker. Kết nối HTTPS qua Cloudflare Tunnel hoạt động ổn định.
Tự động hóa hoàn chỉnh: Xây dựng thành công luồng dữ liệu kín tự động 24/7: Người dùng tin nhắn (Telegram Bot) ➔ Trí tuệ nhân tạo (Google Gemini AI) xử lý & sinh cấu trúc JSON/HTML ➔ Mã JavaScript giúp dọn dẹp, xử lý chuỗi ➔ Tự động xuất bản bài viết (API WordPress).

Tối ưu hoá và xử lý lỗi: Hệ thống được cấu hình System Message chặt chẽ giúp ép văn bản chuẩn xác hơn, xử lý chuỗi bằng JavaScript giúp hệ thống vận hành mượt mà.
