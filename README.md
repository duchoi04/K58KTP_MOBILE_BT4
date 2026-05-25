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


<img width="427" height="684" alt="Screenshot 2026-05-22 152900" src="https://github.com/user-attachments/assets/5cdc6b97-d95d-4c6d-8143-1a9a45280f7b" />


Quản trị viên PhPA:

<img width="427" height="684" alt="Screenshot 2026-05-22 152900" src="https://github.com/user-attachments/assets/1fa5040e-6bcd-488c-b17a-dacf4a1a9adf" />

WordPress:

<img width="427" height="684" alt="Screenshot 2026-05-22 152900" src="https://github.com/user-attachments/assets/d45537c4-92e5-41d9-a3db-d60dcc90e2bf" />

Cấu hình Tunel cloudflare để truy cập các dịch vụ bằng các tên miền phụ ( em sử dụng lệnh cli thay vì thao tác đồ họa trên bảng điều khiển của cloudflare):

Tạo 3 subdomain:

<img width="871" height="78" alt="image" src="https://github.com/user-attachments/assets/41291894-04af-426a-b042-a2b7e479f46f" />

<img width="1210" height="393" alt="Screenshot 2026-05-22 153811" src="https://github.com/user-attachments/assets/1eafc644-3360-4d5d-8445-dc76403a5c6d" />


Thêm chuỗi id tunel vào config.yml:

<img width="932" height="455" alt="Screenshot 2026-05-22 154601" src="https://github.com/user-attachments/assets/1c08a001-cb37-4cd3-a86a-054de02ee027" />


Cấu hình dịch vụ cloudflare trong docker-compose.yml:

<img width="687" height="290" alt="Screenshot 2026-05-22 155114" src="https://github.com/user-attachments/assets/b7633d9a-521f-468b-9cdd-7918cfed44e0" />

Cấp lại quyền truy cập tệp trên máy chủ:


<img width="1080" height="236" alt="Screenshot 2026-05-22 155734" src="https://github.com/user-attachments/assets/24b1e3ce-0be4-47f2-9da8-456acb53448c" />

n8n:

<img width="812" height="550" alt="Screenshot 2026-05-23 162015" src="https://github.com/user-attachments/assets/ec379116-2ae3-48c5-8498-573589c9dc52" />

Kéo các hình ảnh về và chạy chúng:

<img width="907" height="328" alt="Screenshot 2026-05-22 162331" src="https://github.com/user-attachments/assets/276173ad-8b19-4a00-b30e-b744ff361a1e" />


Kiểm tra quyền truy cập các tên miền phụ:

Truy cập sub-domain2 để khảo sát xem cơ sở dữ liệu chưa có bảng nào:

<img width="1902" height="1067" alt="Screenshot 2026-05-22 163525" src="https://github.com/user-attachments/assets/ef247f4f-f326-4724-aada-5b24c0edee75" />

Truy cập subdomain1 để cài đặt wordpress:

<img width="1920" height="1080" alt="Screenshot 2026-05-22 164138" src="https://github.com/user-attachments/assets/db3742bd-6e30-40f3-b3b1-2cb4caaad50b" />

Truy cập sub-domain2 để khảo sát cơ sở dữ liệu có những dữ liệu bảng nào sau khi cài đặt wp:

<img width="1764" height="935" alt="Screenshot 2026-05-22 163640" src="https://github.com/user-attachments/assets/0a7cb11e-4366-4f83-8a98-5525df99486a" />

Tạo 1 bài viết trong wordpress giới thiệu về bản thân sinh viên: thông tin cá nhân, sở hữu, ... bài viết có thể chứa hình ảnh, âm thanh, video, ...

<img width="1920" height="1080" alt="Screenshot 2026-05-22 164750" src="https://github.com/user-attachments/assets/f19e4f2f-4636-4ef7-9c20-38c7319b6645" />


Tạo 1 bài viết trong wordpress giới thiệu về nhữn kiến ​​thức mà em đã học được ở môn Phát triển ứng dụng với mã nguồn mở

<img width="1920" height="1080" alt="Screenshot 2026-05-22 165024" src="https://github.com/user-attachments/assets/f6f7d38a-4873-4aae-af8b-c68923398dc5" />


Truy cập subdomain3 để cấu hình n8n:

Tạo tài khoản quản trị viên:

<img width="1920" height="1080" alt="Screenshot 2026-05-23 154303" src="https://github.com/user-attachments/assets/f1da0751-dcc0-4d5a-ac36-6377034ffe31" />

Cấu hình n8n:

Hãy gửi cho tôi mã bản quyền:

hình ảnh

Kiểm tra email:

hình ảnh

Kích hoạt License key: ( trang chủ -> cài đặt -> cách sử dụng và gói -> nhập key kích hoạt -> điền key vừa nhận từ email vào):

hình ảnh

Tạo quy trình làm việc mới:

<img width="1920" height="1080" alt="Screenshot 2026-05-25 152350" src="https://github.com/user-attachments/assets/6f5140b4-3557-4c79-a351-f8c145a7cc01" />

Thêm nút kích hoạt: nút tìm: Telegram => OnMessage ; cấu hình Thông tin xác thực: Thiết lập Thông tin xác thực => cần nhập Access Token


Cần trò chuyện với bot @BotFather trên Telegram để sinh ra bot mới của riêng mình:

<img width="1180" height="2556" alt="image" src="https://github.com/user-attachments/assets/8c938303-491b-4156-8b29-cd23018382b1" />


Sau khi tạo bot mới để sao chép mã thông báo

<img width="1180" height="2556" alt="image" src="https://github.com/user-attachments/assets/14c1d456-d291-48bd-8529-26f0f553e94c" />


Trò chuyện lần đầu với bot mới này:

hình ảnh

hình ảnh

Thêm nút (nối tiếp vào sau nút Telegram Trigger): AI Google Gemini => Nhắn tin cho mô hình => Thiết lập thông tin xác thực => cần nhập API KEY


Lấy API KEY tại trang: https://aistudio.google.com

hình ảnh

Nhập API Key lên giao diện n8n:

hình ảnh


kéo theo nội dung đã chat với bot của telegram (phía bên trái) vào nội dung phần PROMPT kết quả được {{ $json.message.text }}, cần nhập thêm vào sau {{
$json.message.text }} để quảng cáo dài hơn : vd ({{ $json.message.text }}. Kết quả sinh ra ở dạng HTML+CSS định dạng để tôi sử dụng HTML+CSS này để tạo
bài viết cho wordpress.)

hình ảnh

Bật Nội dung đầu ra dưới dạng JSON : để trả kết quả về dạng json

<img width="891" height="352" alt="image" src="https://github.com/user-attachments/assets/ece83b35-aa0c-47ab-953c-4a2e3026fbc7" />

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
