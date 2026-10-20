🛡️ Website Source Protection

Công cụ hỗ trợ hạn chế xem mã nguồn website bằng cách chặn một số phím tắt phổ biến, chuột phải và kết hợp làm rối mã JavaScript.

✨ Tính năng
🚫 Chặn phím F12.
🚫 Chặn Ctrl + U.
🚫 Chặn Ctrl + Shift + I.
🚫 Chặn Ctrl + Shift + J.
🚫 Chặn Ctrl + Shift + C.
🚫 Chặn chuột phải.
🔒 Hỗ trợ kết hợp Minify và Obfuscate JavaScript.
🌐 Dễ dàng tích hợp vào website HTML nhiều trang.
## 📂 Cấu trúc thư mục

```text
project/
├── index.html
├── about.html
├── css/
│   └── style.css
└── js/
    └── protection.js
```

🚀 Hướng dẫn cài đặt
Bước 1: Tạo file JavaScript

Tạo file js/protection.js và thêm đoạn code sau:

(function () {
    "use strict";

    document.addEventListener("keydown", function (e) {
        const key = e.key.toLowerCase();

        if (
            key === "f12" ||
            (e.ctrlKey && key === "u") ||
            (e.ctrlKey && e.shiftKey &&
                ["i", "j", "c"].includes(key)) ||
            (e.metaKey && key === "u") ||
            (e.metaKey && e.altKey &&
                ["i", "j", "c"].includes(key))
        ) {
            e.preventDefault();
            e.stopPropagation();
        }
    }, true);

    document.addEventListener("contextmenu", function (e) {
        e.preventDefault();
    });

    document.addEventListener("dragstart", function (e) {
        e.preventDefault();
    });
})();

Bước 2: Nhúng vào website

Thêm đoạn sau vào trước thẻ </body> trong file HTML:

HTML
<script src="./js/protection.js"></script>


Nếu website có nhiều trang HTML, hãy thêm đoạn nhúng vào tất cả các trang cần áp dụng.

Bước 3: Làm rối mã nguồn

Bạn có thể sử dụng các công cụ sau để khiến mã nguồn khó đọc hơn:

JavaScript Obfuscator
Terser
CSS Minifier

Sau khi xử lý, hãy kiểm tra lại website để đảm bảo các chức năng vẫn hoạt động bình thường.

⚠️ Lưu ý

Đây chỉ là biện pháp hạn chế truy cập cơ bản, không thể bảo vệ mã nguồn tuyệt đối.

Người dùng vẫn có thể xem hoặc tải xuống HTML, CSS và JavaScript bằng các công cụ khác hoặc thông qua trình duyệt.

Không lưu mật khẩu hoặc API key bí mật trong mã nguồn phía client.
Nên giữ bản code gốc để dễ chỉnh sửa và bảo trì.
Kiểm tra tính tương thích trên máy tính và điện thoại.
Nếu cần bảo vệ dữ liệu quan trọng, hãy xử lý ở phía máy chủ.
📜 License

Bạn có thể tùy chỉnh và tích hợp mã nguồn này vào project của mình. Hãy kiểm tra giấy phép của các thư viện bên thứ ba nếu có sử dụng.

Made with ❤️ for developers.
