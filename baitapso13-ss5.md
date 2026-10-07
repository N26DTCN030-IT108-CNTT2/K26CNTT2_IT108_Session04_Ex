\# BÀI TẬP TỔNG HỢP SESSION 05: GIAO DIỆN DÒNG LỆNH TERMINAL CƠ BẢN (PowerShell)



\## Phần 1 – CLI vs GUI và cấu trúc câu lệnh

1\. Phân tích câu lệnh `ls -Force C:\\Windows\\Logs`:

\- Command: `ls` (hoặc `Get-ChildItem`)

\- Options/Flags: `-Force`

\- Argument: `C:\\Windows\\Logs`



2\. Giải thích vì sao nhóm bắt buộc phải dùng Terminal (PowerShell/SSH) thay vì giao diện đồ họa khi làm việc với máy chủ Cloud:

\- Vì máy chủ Cloud (Cloud Server) thường chạy hệ điều hành không có giao diện đồ họa (headless/Core OS) hoặc nằm ở rất xa, việc xài Terminal giúp tiết kiệm tối đa tài nguyên phần cứng, truyền tải dữ liệu nhẹ nhàng và thực thi các câu lệnh từ xa một cách nhanh chóng, chính xác tuyệt đối.



\## Phần 2 – Điều hướng hệ thống file

1\. Lệnh Relative Path để di chuyển từ `C:\\Users\\student\\Desktop` vào bên trong thư mục `quan-ly-sinh-vien`:

cd .\\quan-ly-sinh-vien

(hoặc xài Set-Location .\\quan-ly-sinh-vien)



2\. Absolute Path đầy đủ tới file `main.py`:

C:\\Users\\student\\Desktop\\quan-ly-sinh-vien\\src\\main.py



3\. Đang ở thư mục `src\\`, dùng một lệnh PowerShell duy nhất để xem toàn bộ nội dung (kể cả file ẩn) của thư mục `data\\` (cùng cấp, nằm trong thư mục cha):

ls -Force ..\\data

(kết hợp lùi ra ngoài 1 cấp bằng .. rồi trỏ vô thư mục data kèm cờ -Force để ép hiện file ẩn)



\## Phần 3 – Thao tác file và thư mục

1\. Lệnh PowerShell tạo cùng lúc 2 thư mục con `src` và `data` bên trong `quan-ly-sinh-vien` (khi thư mục này chưa tồn tại):

New-Item -Path "quan-ly-sinh-vien\\src", "quan-ly-sinh-vien\\data" -ItemType Directory -Force

(hoặc xài mkdir quan-ly-sinh-vien\\src, quan-ly-sinh-vien\\data)



2\. Lệnh PowerShell tạo 3 file rỗng `main.py`, `utils.py` và `README.md` trong cùng một dòng lệnh:

New-Item -Path "quan-ly-sinh-vien\\src\\main.py", "quan-ly-sinh-vien\\src\\utils.py", "quan-ly-sinh-vien\\README.md" -ItemType File



3\. Đổi tên thư mục gốc thành `quan-ly-sinh-vien` và sao lưu toàn bộ thành `backup-quan-ly-sinh-vien`:

\- Lệnh đổi tên:

Rename-Item -Path "quan-ly-sv" -NewName "quan-ly-sinh-vien"

\- Lệnh sao lưu toàn bộ (kèm nội dung con bằng cờ đệ quy):

Copy-Item -Path "quan-ly-sinh-vien" -Destination "backup-quan-ly-sinh-vien" -Recurse



\## Phần 4 – Xử lý lỗi Terminal

1\. Dựa vào Log lỗi số 2 (môn `scr` bị sai chính tả):

\- Chẩn đoán: Đây là lỗi gõ sai tên thư mục (Command/Path not found do typo).

\- Cách dùng phím Tab: Gõ cd sc rồi bấm phím Tab, hệ thống sẽ tự động nhảy ra chữ `src` chuẩn chỉnh giúp mình luôn mà không sợ gõ sai.



2\. Dựa vào Log lỗi số 3 (Access is denied khi chạy `.\\setup.ps1`):

\- Chẩn đoán: Lỗi này tương ứng với việc thiếu quyền thực thi (Execution Policy chặn) hoặc tài khoản user hiện tại không đủ quyền Administrator để chạy script hệ thống trên Windows.

\- Cách khắc phục: Tắt Terminal đi, click chuột phải mở lại bằng quyền Run as Administrator, hoặc chạy lệnh Set-ExecutionPolicy Unrestricted để cấp phép chạy script.



3\. Dựa vào Log lỗi số 1 (xóa thư mục `old-version` có chứa file con):

\- Nguyên nhân cảnh báo: Do thư mục còn chứa dữ liệu bên trong và thiếu tham số đệ quy nên PowerShell sợ mình xóa nhầm nên hỏi lại cho chắc.

\- "Đơn thuốc" (lệnh xóa không cần hỏi):

Remove-Item -Path "old-version" -Recurse -Force

(xài kèm -Recurse để quét sạch file con và -Force để ép xóa luôn không thèm hỏi lằng nhằng)



4\. Quy trình 3 bước đọc log lỗi cho Log lỗi số 4:

| Bước | Câu trả lời của bạn |

| :--- | :--- |

| (a) Dòng chứa thông điệp lỗi trực tiếp nhất | FileNotFoundError: \[Errno 2] No such file or directory: 'data/input.csv' |

| (b) Từ khóa lỗi (Error Keyword) | FileNotFoundError / No such file or directory |

| (c) Điều cần kiểm tra tiếp để sửa lỗi (vị trí đang đứng / đường dẫn trong code) | Kiểm tra lại vị trí thực thi file script đang đứng (`src\\`) so với cấu trúc đường dẫn tương đối gọi tới file `data/input.csv` trong code (vì từ trong src gọi `data/input.csv` sẽ bị lệch cấp thư mục). |

