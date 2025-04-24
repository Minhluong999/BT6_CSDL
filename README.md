Họ Tên: Lăng Nguyễn Minh Lượng     MSSV: k225480106044
Bài tập 6: Hệ quản trị CSDL
Chủ đề: Câu lệnh Select
Yêu cầu bài tập: 
Cho file sv_tnut.sql (1.6MB)
1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server của em
2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)
3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
6. nhập sql để tìm xem có những sv nào trùng tên với em?
7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.
9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)
--------------------------------------------------------------------------------------------------------------------
Bài Làm

1. open file sv_tnut.sql

Execute tạo database sv_tnut

![image](https://github.com/user-attachments/assets/fdf801bd-f76b-4303-a277-b87430d9bfe7)

2.Dữ liệu đầu vào 
Họ tên : Lăng Nguyễn Minh Lượng
Sđt: 0982247105
Ngày Tháng Năm sinh: 26-11-2004

3.Nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
em dùng lệnh

SELECT * FROM SV
WHERE ns = '2004-11-26';

![image](https://github.com/user-attachments/assets/c70a0e46-81b2-44eb-bd8e-7f958ca6996c)


4.Nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
em dùng lệnh 

SELECT * FROM SV
WHERE DAY(ns) = 26 AND MONTH(ns) = 11;

![image](https://github.com/user-attachments/assets/aa449d40-07ca-4dc5-b451-779f9d8f5689)


5.Nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
em dùng lệnh 

SELECT * FROM SV
WHERE MONTH(ns) = 11 AND YEAR(ns) = 2004;



6. Nhập sql để tìm xem có những sv nào trùng tên với em?
em dùng lệnh
