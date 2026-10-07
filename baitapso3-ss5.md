#BÀI TẬP 3 Kiến trúc sư hạ tầng Cloud Server

## P1: Mã nguồn (trên lớp học power shell nên em sẽ giải bài bằng power shell)

 

đề :

Farm-Manager\code\app, Farm-Manager\database\db, Farm-Manager\logs\guides 

* Tham số -Recurse (đệ quy) bắt buộc phải có để sao chép toàn bộ thư mục logs cùng các thư mục con (guides) và file bên trong nó. 

 New-Item -Path ".\Farm-Manager\code\app", ".\Farm-Manager\database\db", ".\farm-manager\logs\guides" -ItemType Directory -Force

*lệnh New-Item này tạo một chuỗi folder và có thư mục con ở trong và tham số -Force giúp tạo toàn bộ thư mục cha trên đường dẫn nếu chưa tồn tại và không báo lỗi nếu folder đã có*



 đề:  Trong thư mục app, tạo sẵn 3 file rỗng: main.py, models.py, utils.py.

New-Item -Path ".\Farm-Manager\code\app\main.py", ".\Farm-Manager\code\app\models.py", ".\Farm-Manager\code\app\utils.py" -ItemType File

*lệnh này tạo file trong thư mục đã có sẵn *



đề : sao toàn bộ logs sang logs-backup

Copy-Item -Path ".\Farm-Manager\logs" -Destination ".\Farm-Manager\logs-backup" -Recurse

*lệnh Copy-Item là copy, còn tham số -Recurse bắt buộc phải có để sao chép toàn bộ thư mục logs cùng các thư mục con (guides) và file bên trong nó.



## P2 Kiểm thử

ls .\farm-manager 

còn ls -Recurse .\farm-manager nó sẽ liệt recursive toàn bộ folder và file bên trong, giúp mình nắm được cấu trúc rõ ràng hơn



vì khi sử dụng absolute path thì khi chạy trên một OS khác hoặc tên user khác thì sẽ gặp lỗi NO SUCH FILE OR DIRECTORY, còn khi sd relative path thì vẫn hoạt động bình thường