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

dùng lệnh

SELECT * FROM SV
WHERE ns = '2004-11-26';

![image](https://github.com/user-attachments/assets/c70a0e46-81b2-44eb-bd8e-7f958ca6996c)


4.Nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?

dùng lệnh 

SELECT * FROM SV
WHERE DAY(ns) = 26 AND MONTH(ns) = 11;

![image](https://github.com/user-attachments/assets/aa449d40-07ca-4dc5-b451-779f9d8f5689)


5.Nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?

dùng lệnh 

SELECT * FROM SV
WHERE MONTH(ns) = 11 AND YEAR(ns) = 2004;

![Ảnh chụp màn hình 2025-04-24 170526](https://github.com/user-attachments/assets/03b8b601-ded2-4a56-b0d4-a0d963eb8dde)


6. Nhập sql để tìm xem có những sv nào trùng tên với em?

dùng lệnh

SELECT * FROM SV
WHERE ten = N'Lượng';

![image](https://github.com/user-attachments/assets/a0c9d9ee-cec3-4198-a2eb-150ed67d140b)


7. Nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.

dùng lệnh 

SELECT * FROM SV
WHERE hodem = N'Lăng Nguyễn Minh';

![image](https://github.com/user-attachments/assets/5f1571c3-8f8f-402f-974b-6a264772df33)


8. Nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.

dùng lệnh 


SELECT * FROM SV
WHERE LEN(sdt) = 10
  AND (
    (IIF(SUBSTRING(sdt,1,1) <> '0',1,0) +
     IIF(SUBSTRING(sdt,2,1) <> '9',1,0) +
     IIF(SUBSTRING(sdt,3,1) <> '8',1,0) +
     IIF(SUBSTRING(sdt,4,1) <> '2',1,0) +
     IIF(SUBSTRING(sdt,5,1) <> '2',1,0) +
     IIF(SUBSTRING(sdt,6,1) <> '4',1,0) +
     IIF(SUBSTRING(sdt,7,1) <> '7',1,0) +
     IIF(SUBSTRING(sdt,8,1) <> '1',1,0) +
     IIF(SUBSTRING(sdt,9,1) <> '0',1,0) +
     IIF(SUBSTRING(sdt,10,1) <> '5',1,0)) = 1
  );

![image](https://github.com/user-attachments/assets/4955c052-1779-4a15-a07d-42cde9ec0324)


kết quả không có sv nào có sđt chỉ khác 1 số với số 0982247105 

9. Hãy liệt kê tất cả các sv ngành kmt, sắp xếp theo tên và họ đệm, kiểu tiếng việt, giải thích.

dùng lệnh 

SELECT * FROM SV
WHERE lop LIKE N'%KMT%'
ORDER BY ten COLLATE Vietnamese_CI_AS, hodem COLLATE Vietnamese_CI_AS;

![image](https://github.com/user-attachments/assets/6c874f87-fc57-43e5-89f2-cb03721f1f7e)


10. Hãy nhập sql để liệt kê các sv nữ ngành kmt có trong bảng sv (trình bày quá trình suy nghĩ và giải những vướng mắc)

do database không có cột giới tính nên em sử dụng hodem 'Thi' để tạm thay thế cho giới tính nữ 

dùng lệnh 

SELECT * FROM SV
WHERE lop LIKE N'%KMT%'
  AND hodem LIKE N'%Thị%';

  ![image](https://github.com/user-attachments/assets/a7ba4f82-5aa5-4327-b759-cc2b670cf1a5)
