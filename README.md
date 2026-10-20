🛡️ Website Source Protection
Công cụ hỗ trợ hạn chế xem mã nguồn website bằng cách chặn một số phím tắt phổ biến, chuột phải và kết hợp làm rối mã JavaScript.

✨ Tính năng
🚫 Chặn phím F12.
🚫 Chặn Ctrl + U.
🚫 Chặn Ctrl + Shift + I.
🚫 Chặn Ctrl + Shift + J.
🚫 Chặn Ctrl + Shift + C.
🚫 Chặn chuột phải.
🚫 Chặn thao tác kéo thả nội dung.
🔒 Hỗ trợ kết hợp Minify và Obfuscate JavaScript.
🌐 Dễ dàng tích hợp vào website HTML nhiều trang.


## 📂 Cấu trúc thư mục

```
project/
├── index.html
├── about.html
├── css/
│   └── style.css
└── js/
    └── protection.js
```

## 🚀 Hướng dẫn cài đặt
Bước 1: Tạo file JavaScript
Tạo file ```js/protection.js``` và thêm toàn bộ đoạn code sau:

```
(function () {
    "use strict";

    // Chặn các phím tắt phổ biến
    document.addEventListener("keydown", function (e) {
        const key = e.key.toLowerCase();

        const blocked =
            key === "f12" ||
            (e.ctrlKey && key === "u") ||
            (e.ctrlKey && e.shiftKey &&
                ["i", "j", "c"].includes(key)) ||
            (e.metaKey && key === "u") ||
            (e.metaKey && e.altKey &&
                ["i", "j", "c"].includes(key));

        if (blocked) {
            e.preventDefault();
            e.stopPropagation();
        }
    }, true);

    // Chặn menu chuột phải
    document.addEventListener("contextmenu", function (e) {
        e.preventDefault();
    });

    // Chặn kéo thả nội dung
    document.addEventListener("dragstart", function (e) {
        e.preventDefault();
    });
})();
```

Bước 2: Nhúng vào file HTML
Thêm dòng sau ngay trước thẻ ```</body>``` của mỗi file HTML cần áp dụng:
```
<script src="./js/protection.js"></script>
```

Ví dụ:
```
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website của tôi</title>
</head>
<body>

    <h1>Xin chào!</h1>

    <script src="./js/protection.js"></script>
</body>
</html>
```

Bước 3: Áp dụng cho toàn bộ website
