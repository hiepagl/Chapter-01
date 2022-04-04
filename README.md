# Cơ chế hoạt động của website

## 1. Cơ chế hoạt động của internet

- Internet là mội mạng lưới cáp vật lý toàn cầu, bao gồm cáp đồng (ADSl) và cáp quang (FTTH), dùng để kết nối các thiết bị điện tử (máy tính, điện thoại...) có trang bị kết nối internet thông qua kết nối có dây hoặc không dây (wifi, 4G...). Ngay cả các kết nối không dây như Wi-Fi và 3G / 4G cũng dựa vào các loại cáp vật lý này để truy cập Internet.

- Thông qua việc truy cập internet này các thiết bị điện tử có thể chia sẻ dữ liệu, hình ảnh, tập tin với nhau.

- Khi mình truy cập một trang web, một yêu cầu (request) được gửi từ máy tính của mình qua các dây này (internet) đến máy chủ (server). Máy chủ là nơi lưu trữ các src code / dữ liệu (data), khi nhận được yêu cầu thì máy chủ sẽ truy xuất và trả lại (response) dữ liệu / src code trang web mà mình yêu cầu. Lúc này browser (trình duyệt web) sẽ biên dịch src code nhận được và xuất ra giao diện cho người dùng.

## 2. Giải thích về protocol của HTTP/HTTPS

### 2.1 Giao thức (protocol) của HTTP

- HTTP (Hypertext Transfer Protocol) là giao thức truyền tải siêu văn bản do World Wide Web (www) tiêu chuẩn hóa để truyền tải dữ liệu dưới dạng siêu văn bản (text, hình ảnh, video...) từ máy chủ (Web Server) tới trình duyệt web của người dùng và ngược lại.

- Giao thức HTTP sử dụng bộ giao thức TCP/IP (các giao thức nền tảng cho Internet mà hầu hết các mạng máy tính thương mại đang chạy trên đó).

- HTTP hoạt động theo mô hình Client (máy khách/ người dùng) – Server (máy chủ). Việc truy cập website được tiến hành dựa trên các giao tiếp giữa 2 đối tượng trên. Khi mình truy cập một trang web qua giao thức HTTP (ví dụ: http://allgrow-labo.jp/), trình duyệt (browser) sẽ thực hiện các phiên kết nối (gửi yêu cầu) đến server của trang web đó thông qua địa chỉ IP do hệ thống phân giải tên miền DNS cung cấp. Máy chủ (web server) sau k hi nhận yêu cầu, sẽ trả về lệnh (response) tương ứng giúp hiển thị website, bao gồm các nội dung như: văn bản, ảnh, video, âm thanh.

** Trong quá trình kết nối và trao đổi thông tin, trình duyệt của mình sẽ mặc nhiên thừa nhận địa chỉ IP đó đến từ server của chính website mà mình muốn truy cập mà không hề có biện pháp xác thực nào. Các thông tin được gửi đi qua giao thức HTTP (bao gồm địa chỉ IP, các thông tin mà mình nhập vào website…) cũng không hề được mã hóa và bảo mật. Đây chính là kẽ hở mà nhiều hacker đã lợi dụng để đánh cắp thông tin người dùng.**

### 2.2 Giao thức (protocol) của HTTPS

- HTTPS (Hypertext Transfer Protocol Secure) là giao thức truyền tải siêu văn bản an toàn. Thực chất, đây chính là giao thức HTTP nhưng tích hợp thêm bảo mật SSL (Secure Sockets Layer – tầng ổ bảo mật) hoặc TLS (Transport Layer Security – bảo mật tầng truyền tải) nhằm mã hóa các dữ liệu giao tiếp để tăng tính bảo mật, HTTPS là phiên bản HTTP an toàn, bảo mật hơn.

- Các tiêu chuẩn bảo mật này đảm bảo các nội dung sẽ được mã hóa trước khi truyền đi, và giải mã khi nhận. Việc này khiến hacker dù có lấy được thông tin cũng không thể hiểu được thông tin đó.

## 3. Cơ chế hoạt động của browser và sự khác nhau giữa các browser

### 3.1 Cơ chế hoạt động của browser

- Khi người dùng (user) dùng browser để truy cập website bằng việc nhập trên thanh địa chỉ (đó là nơi nhập tên miền để tìm một trang web) thì một request (yêu cầu) được gửi đi đến web server, web server sẽ nhận request và trả về (response) là đoạn mã HTMl (HTML code), sau đó browser sẽ biên dịch đoạn html code vừa nhận nếu trong đoạn html code có các link (css, js, fonts, hình ảnh....) thì browser sẽ tiếp tục gửi request đến web server để tải các nội dung đó về và xuất ra giao diện cho người dùng.

### 3.2 Sự khác nhau giữa các browser (Firefox, Chrome, Edge, Safari, Opera, Internet Explorer...)

- Các browser khác nhau về việc kết xuất nội dung (biên dịch code) vì mỗi trình duyệt có công cụ kết xuất riêng, nội dung không được hiển thị giống hệt nhau trên tất cả các trình duyệt. Kết quả là có thể có sự khác biệt trong bố cục và giao diện của trang web. Do đó khi lập trình web phải lưu ý đến các thuộc tính CSS được hỗ trợ trong trình duyệt hay không để tránh trường hợp vỡ layout khi dùng trình duyệt khác.

## 4. Cơ chế hoạt động của DNS và domain

- Domain (tên miền) là địa chỉ của website.

- DNS chính là hệ thống phân giải tên miền (Domain Name System), DNS sẽ giúp liên kết giữa địa chỉ IP (địa chỉ web) và Domain lại nhằm liên kết nhiều thông tin đa dạng trong hệ thống mà người dùng truy cập.

- Mỗi website đều có một địa chỉ IP riêng của nó, và chính nhờ có cơ chế làm việc của DNS mà khi chúng ta gõ một tên miền (allgow-labo.com là một ví dụ), hệ thống phân giải tên miền sẽ đưa chúng ta vào thẳng website của nó mà không cần phải gõ những cụm số IP khó nhớ như 192.168.2.8.

## 5. Giải thích về hosting server

- Hosting server là việc quản lý và duy trì các tài nguyên phần cứng mà trong đó lưu trữ các dữ liệu / src code của mình. Bằng cách trả phí hàng tháng cho dịch vụ hosting, mình có được cơ sở hạ tầng CNTT đầy đủ, mà không phải trả chi phí liên quan đến bảo trì, đào tạo và cập nhật thiết bị.

- Các loại server hosting: Shared hosting (hosting chia sẻ), Cloud hosting, Managed hosting.
