# My Ghost

Giao diện tối giản cho [Nguyễn Hồng Thế Blog](https://nguyenhongthe.net).

## Hướng dẫn

### Cài đặt thủ công

1. [Tải theme](https://github.com/nguyenhongthe/myghost/archive/main.zip)
2. Đăng nhập vào Ghost, và điều hướng đến khu vực cài đặt `Design` để tải lên tệp zip của theme.
3. Sau khi tải lên, bạn có thể chọn theme `MyGhost` để sử dụng.

### Cài đặt tự động (khuyến khích nếu bạn muốn phát triển thêm giao diện)

Bạn có thể cài đặt theme tự động thông quan Github Action.

1. Đăng nhập vào khu vực admin của Ghost blog của bạn, và điều hướng đến khu vực `Settings` > `Integrations` > `Add custom integration` để tạo API.
2. Điền tên của API, ví dụ `Github Action`, và chọn `Create`.
3. Trong cửa sổ hiện ra, bạn sẽ thấy `Admin API Key` và `API URL`. Bạn sẽ cần 2 giá trị này để sử dụng trong các bước tiếp theo.
4. Tạo một fork của repo này.
5. Đăng nhập vào Github, và điều hướng đến khu vực `Settings` của repo.
6. Trong tab `Secrets and variables`, chọn `Action`.
7. Tiếp tục chọn `Secrets`, sau đó click nút `New repository secret` và tạo 2 biến môi trường `GHOST_ADMIN_API_URL` và `GHOST_ADMIN_API_KEY` với giá trị tương ứng là `API URL` và `Admin API Key` bạn đã tạo ở bước 3.
8. Chọn `Actions` và chọn `I understand my workflows, go ahead and enable them`.
9. Chọn `Actions` và chọn `Deploy Theme`.
10. Chọn `Run workflow` và chờ đợi quá trình cài đặt hoàn tất.

> Chú ý: Các bước ở trên chỉ cần thực hiện một lần duy nhất. Sau này, mỗi khi bạn chỉnh sửa code của theme, commit và push code lên Github, Github Action sẽ tự động cài đặt theme mới vào website đang chạy Ghost blog cho bạn.

## Phát triển

MyGhost được phát triển dựa trên theme cơ bản [Starter](https://github.com/TryGhost/Starter) của Ghost. Bạn có thể tham khảo [Ghost Themes Documentation](https://ghost.org/docs/themes/) để biết thêm chi tiết.

Giao diện được viết bằng [Handlebars](https://handlebarsjs.com/) và được biên dịch bằng Gulp/PostCSS. Bạn cần cài đặt [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) và [Gulp](https://gulpjs.com) để có thể phát triển giao diện.

Sau khi cài đặt các phần mềm cần thiết, bạn có thể chạy các lệnh sau để phát triển giao diện:

```bash
# Clone the repo
git clone https://github.com/nguyenhongthe/MyGhost.git

# Di chuyển vào thư mục giao diện
cd MyGhost

# Cài đặt các gói phụ thuộc
yarn

# Chạy giao diện trong chế độ phát triển
yarn dev
```

Bây giờ bạn có thể chỉnh sửa các tệp `/assets/css/`, các tệp này sẽ được biên dịch tự động vào thư mục `/assets/built/`.

Để chạy giao diện trên máy chủ Ghost, bạn cần tạo liên kết tượng trưng (symlink) từ thư mục giao diện đến thư mục chứa Ghost blog.

```bash
# Tạo liên kết tượng trưng
ln -s /dir/to/your/themes/MyGhost /dir/to/your/ghost-site/content/themes/myghost
```

Khởi động lại Ghost blog và giao diện sẽ được liệt kê trong khu vực `Design` của Ghost Admin.

## Các lệnh hữu ích

Đóng gói các tệp của giao diện vào tệp `dist/MyGhost.zip`, bạn có thể tải tệp này lên website của bạn để cài đặt giao diện thủ công.

```bash
yarn zip
```

## Đóng góp và báo lỗi

Repo này được đồng bộ tự động với `repo.vnscdn.com`. Nếu bạn muốn đóng góp hoặc báo lỗi, hãy truy cập vào repo chính [nguyenhongthe/repo.vnscdn.com](https://github.com/nguyenhongthe/repo.vnscdn.com/tree/main/packages/myghost) nơi giao diện chính thức được phát triển.

## Bản quyền và giấy phép

Copyright (c) 2013-2023 Nguyễn Hồng Thế Blog - Phát hành theo giấy phép [MIT](LICENSE).
