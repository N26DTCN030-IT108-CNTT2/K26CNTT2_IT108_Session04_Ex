\# BÀI TẬP SỐ 7 Phân tích và khắc phục lỗi điều hướng thư mục trên Terminal tại OrderTech



\## P1 Phân tích vấn đề

vì tên thư mục có chứa khoảng trắng, nên khi mình gõ lệnh cd Menu Thang 9 thì terminal nó sẽ hiểu nhầm Menu, Thang, 9 là 3 cái đối số riêng biệt. nó sẽ cố gắng tìm cái thư mục chỉ có tên là Menu để chui vào, nhưng mà không có folder nào tên như vậy hết nên nó báo lỗi Cannot find path.



\## P2 Hoàn thiện bài

cách 1: mình bọc cái tên folder vào trong dấu ngoặc kép

cd "Menu Thang 9"

(khi có ngoặc kép thì hệ thống sẽ hiểu nguyên cái cụm bên trong là 1 tên duy nhất)



cách 2: mình bọc bằng dấu nháy đơn 

cd 'Menu Thang 9'

(ngoài ra nếu lười gõ thì mình có thể xài phím Tab, kiểu gõ cd Menu xong bấm Tab là hệ thống tự điền phần còn lại chuẩn định dạng cho mình luôn)

