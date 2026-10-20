🛡️ Website Source Protection

Hướng dẫn tích hợp các biện pháp bảo vệ mã nguồn cơ bản cho website HTML, CSS và JavaScript.

✨ Tính năng
🚫 Chặn phím F12.
🚫 Chặn Ctrl + U để hạn chế mở mã nguồn trang.
🚫 Chặn Ctrl + Shift + I, Ctrl + Shift + J, Ctrl + Shift + C.
🚫 Chặn chuột phải.
🚫 Chặn thao tác kéo thả nội dung.
🔒 Hỗ trợ kết hợp Minify và JavaScript Obfuscation để làm code khó đọc hơn.
📱 Có thể tích hợp vào website nhiều trang.
Lưu ý: Đây chỉ là các biện pháp hạn chế truy cập thông thường, không thể ngăn chặn hoàn toàn việc xem hoặc sao chép mã nguồn trên trình duyệt.
📁 Cấu trúc thư mục gợi ý

my-website/
├── index.html
├── about.html
├── contact.html
├── css/
│   └── style.css
└── js/
    └── protection.js

🚀 Bước 1: Tạo file protection.js

Tạo file js/protection.js và thêm đoạn code sau:

(function () {
    "use strict";

    // Chặn các phím tắt DevTools và xem mã nguồn
    document.addEventListener("keydown", function (event) {
        const key = event.key.toLowerCase();

        const blocked =
            key === "f12" ||
            (event.ctrlKey && key === "u") ||
            (event.ctrlKey && event.shiftKey &&
                ["i", "j", "c"].includes(key)) ||
            (event.metaKey && key === "u") ||
            (event.metaKey && event.altKey &&
                ["i", "j", "c"].includes(key));

        if (blocked) {
            event.preventDefault();
            event.stopPropagation();
        }
    }, true);

    // Chặn menu chuột phải
    document.addEventListener("contextmenu", function (event) {
        event.preventDefault();
    });

    // Chặn kéo thả nội dung
    document.addEventListener("dragstart", function (event) {
        event.preventDefault();
    });
})();

🔗 Bước 2: Nhúng vào HTML

Thêm dòng sau vào tất cả file HTML cần áp dụng, ngay trước thẻ </body>:

HTML
<script src="/js/protection.js"></script>


Nếu website nằm trong thư mục con hoặc triển khai trên GitHub Pages với project site, hãy điều chỉnh đường dẫn cho phù hợp, ví dụ:

HTML
<script src="./js/protection.js"></script>


Quan trọng: Đường dẫn /js/protection.js trỏ từ thư mục gốc của domain. Nếu website chạy tại username.github.io/ten-repository/, đường dẫn tương đối ./js/protection.js thường phù hợp hơn với trang ở thư mục gốc của repository.

🌐 Bước 3: Áp dụng cho toàn bộ website

Có thể nhúng file protection.js vào mọi trang HTML:

index.html
about.html
contact.html
Các trang HTML khác của project.

Nếu website sử dụng template chung, hãy đặt đoạn nhúng vào template để các trang sử dụng template đó đều được áp dụng.

🔐 Bước 4: Làm rối mã nguồn JavaScript

Để khiến JavaScript khó đọc hơn, bạn có thể dùng công cụ:

javascript-obfuscator — làm rối mã JavaScript.
Terser — minify và tối ưu JavaScript.
Clean CSS — minify CSS.

Quy trình gợi ý:

Hoàn thiện và kiểm thử code gốc.
Minify hoặc obfuscate các file JavaScript cần phân phối.
Đưa các file đã xử lý lên hosting.
Kiểm tra lại toàn bộ chức năng trên máy tính và điện thoại.

Nên giữ một bản source code gốc để dễ chỉnh sửa và bảo trì.

⚠️ Giới hạn bảo vệ

JavaScript chạy ở trình duyệt người dùng nên các biện pháp trên không thể bảo vệ tuyệt đối mã nguồn.

Người dùng vẫn có thể:

Mở DevTools qua menu trình duyệt hoặc công cụ bên ngoài.
Tải file HTML, CSS và JavaScript từ website.
Tắt JavaScript hoặc sửa các đoạn code phía client.
Đọc nội dung đã được tải xuống, kể cả khi code đã minify hoặc obfuscate.

Không đưa mật khẩu, API key bí mật, thông tin đăng nhập hoặc dữ liệu nhạy cảm vào JavaScript công khai. Các thông tin này cần được xử lý ở máy chủ.

🧪 Kiểm tra sau khi cài đặt
Website vẫn tải bình thường.
Các nút bấm và hiệu ứng JavaScript hoạt động.
File protection.js tải thành công.
Phím tắt bị chặn theo mong muốn.
Chuột phải bị hạn chế.
Website vẫn hoạt động trên điện thoại.
📜 License

Bạn có thể tùy chỉnh và tích hợp đoạn code này vào project của mình. Hãy kiểm tra giấy phép của từng thư viện hoặc công cụ bên thứ ba mà bạn sử dụng.

Made with ❤️ for website developers.
