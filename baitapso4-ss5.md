\# BÀI 4 QUẢN LÍ PATH TRONG HỆ THỐNG TỆP

\## P1: PHÂN  TÍCH VÀ ĐỀ XUẤT

so sánh giữa absolute và relative path

| Tiêu chí | Absolute | Relative |

| :---:| :---: | :---: |

| Portability | Tính di động thấp, path bị hard-code với user. Nên khi gửi cho bạn bè code sẽ báo lỗi File not found | Tính di động cao, khi gửi folder Project cho bạn bè nếu khác user hoặc ổ đĩa thì vẫn chạy bình thường |

| Độ dài câu lệnh | dài dòng làm đoạn code rườm rà | ngắn gọn thẩm mỹ |

| Độ an toàn | Cao vì chỉ chạy trên đúng user của nó | Nếu áp dụng đúng quy tắc và tuân thủ cấu trúc folder thì vẫn an toàn |

&#x20;## P2 Lựa chọn

* An nên sử dụng relative path
* . là vị trí hiện tại
* .. là lùi ra ngoài 1 cấp folder

