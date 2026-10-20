## 🛡️ Website Source Protection
## Công cụ hỗ trợ hạn chế xem mã nguồn website bằng cách chặn một số phím tắt phổ biến, chuột phải và kết hợp làm rối mã JavaScript.

## ✨ Tính năng
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
## Bước 1: Tạo file JavaScript
## Tạo file ```js/protection.js``` và thêm toàn bộ đoạn code sau:

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

## Bước 2: Nhúng vào file HTML
## Thêm dòng sau ngay trước thẻ ```</body>``` của mỗi file HTML cần áp dụng:
```
<script src="./js/protection.js"></script>
```

## Ví dụ:
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

## Bước 3: Áp dụng cho toàn bộ website
Nếu website có nhiều trang HTML, hãy nhúng file protection.js vào tất cả các trang cần bảo vệ.
Ví dụ:
```
index.html
about.html
contact.html
```
Nếu các trang sử dụng chung template, bạn có thể thêm đoạn nhúng vào template để không cần lặp lại thủ công.
## 🔐 Làm rối mã nguồn JavaScript
Bạn có thể sử dụng các công cụ sau để làm code khó đọc hơn:
- JavaScript Obfuscator — làm rối mã JavaScript.
- Terser — minify và tối ưu JavaScript.
- CSS Minifier — nén CSS.

## Quy trình thực hiện
1. Hoàn thiện và kiểm thử code gốc.
2. Sao lưu mã nguồn ban đầu.
3. Minify hoặc obfuscate các file JavaScript cần phân phối.
4. Đưa các file đã xử lý lên hosting.
5. Kiểm tra lại website trên máy tính và điện thoại.

## ⚠️ Giới hạn bảo vệ
Đây chỉ là biện pháp hạn chế truy cập cơ bản, không thể bảo vệ mã nguồn tuyệt đối.
Người dùng vẫn có thể:
- Mở DevTools thông qua menu trình duyệt hoặc các công cụ khác.
- Tải xuống HTML, CSS và JavaScript từ website.
- Tắt JavaScript hoặc sửa các đoạn code phía client.
- Đọc mã nguồn sau khi đã minify hoặc obfuscate.



