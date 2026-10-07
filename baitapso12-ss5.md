\# BÀI 12: Vận dụng Terminal để cập nhật và xử lý sự cố file Menu tại OrderTech (PowerShell)



\## Nhiệm vụ 1: Điều hướng thư mục

1\. Lệnh di chuyển vào thư mục con assets\\menus:

cd assets\\menus

(dùng lệnh cd để chui thẳng vào thư mục chứa thực đơn của nhà hàng)



2\. Lệnh in ra đường dẫn thư mục làm việc hiện tại để xác minh:

pwd

(lệnh pwd giúp mình in ra cái đường dẫn hiện tại để chắc chắn 100% là mình đã đứng đúng vị trí mục tiêu rồi mới làm tiếp các bước sau)



\## Nhiệm vụ 2: Sao chép \& Nhân bản tệp tin

lệnh Terminal để tạo bản sao độc lập từ file cũ ra file menu\_lehoi.txt:

Copy-Item -Path "menu\_cu.txt" -Destination "menu\_lehoi.txt"

(hoặc xài lệnh copy thu gọn: cp menu\_cu.txt menu\_lehoi.txt)

(dùng lệnh này để nhân bản cái thực đơn cũ ra một file mới hoàn toàn độc lập tên là menu\_lehoi.txt để chuẩn bị chỉnh sửa cho dịp lễ)



\## Nhiệm vụ 3: Xử lý sự cố gõ lệnh

1\. Nguyên nhân cốt lõi gây ra lỗi (mkkdir):

\- Do kỹ sư bị gõ nhầm chính tả, thừa chữ 'k' thành từ `mkkdir` thay vì `mkdir` (hoặc `New-Item`). Hệ thống không tìm thấy lệnh này trong danh sách câu lệnh hợp lệ nên nó réo lên lỗi `CommandNotFoundException` (Command not found).



2\. Câu lệnh Terminal chính xác đã được sửa lại:

mkdir backup\_menu

(hoặc dùng lệnh gốc của PowerShell: New-Item -Path "backup\_menu" -ItemType Directory)



\## Nhiệm vụ 4: Tư duy kỹ sư hệ thống (CLI vs GUI)

2 ưu điểm vượt trội của CLI khi quản trị máy chủ so với giao diện bấm chuột (GUI):

\- Tốc độ và hiệu suất cao hơn: CLI cực kỳ nhẹ, không tốn tài nguyên đồ họa, giúp thực thi các câu lệnh và xử lý hàng loạt file chỉ trong vài nốt nhạc mà không bị giật lag.

\- Tự động hóa tuyệt đối (Automation): CLI cho phép viết thành các đoạn script để chạy tự động hàng loạt tác vụ lặp đi lặp lại, trong khi GUI thì bắt buộc phải click chuột thủ công từng cái rất mất thời gian.

