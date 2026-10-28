# BÀI LÀM – HACKATHON 01

- **Mã đề:** 20
- **Họ tên:** Vũ Quốc Linh
- **Lớp:** CNTT1
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -force
mv lich_lam_viec.txt docs
mv logo_saloc_toc.PNG media
cp media/logo_saloc_toc.PNG backup
rm temp_289.tmp
ls
cd logs
ls -force
cd ..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
     Directory: C:\Users\linhs\Downloads\starter-kit (1)\salon-toc-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026   7:59 AM                backup
d-----        10/28/2026   7:45 AM                data
d-----        10/28/2026   7:57 AM                docs
d-----        10/28/2026   7:46 AM                logs
d-----        10/28/2026   7:57 AM                media
-a----        10/27/2026   1:32 AM             67 .env
-a----        10/27/2026   1:32 AM           2230 bai_lam.md


    Directory: C:\Users\linhs\Downloads\starter-kit (1)\salon-toc-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6113 logo_saloc_toc.PNG


    Directory: C:\Users\linhs\Downloads\starter-kit (1)\salon-toc-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6103 hoa_don_saloc_thang.xlsx


    Directory: C:\Users\linhs\Downloads\starter-kit (1)\salon-toc-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM             62 lich_lam_viec.txt


    Directory: C:\Users\linhs\Downloads\starter-kit (1)\salon-toc-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           1032 salon.log


    Directory: C:\Users\linhs\Downloads\starter-kit (1)\salon-toc-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6113 logo_saloc_toc.PNG

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-content ./logs/salon.log | Select-String "ERROR" > ./logs/daily_report.txt
Get-Content .\logs\daily_report.txt
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-11-28 09:53:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
2026-11-28 09:57:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
 Get-Content ../logs/salon.log | Select-String "ERROR" >> ../script/auto_report.ps1
```

### Kết quả hiển thị

```text
2026-11-28 09:53:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
2026-11-28 09:57:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
2026-11-28 10:13:35 [ERROR] Dat lich that bai
2026-11-28 10:33:35 [ERROR] Dat lich that bai
2026-11-28 10:37:35 [ERROR] Thanh toan bi tu choi
```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
# Ghi lệnh vào đây (xoá dòng này)

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
6

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
cd ..
cd logs
new-item tong_hop.txt
write-output === TONG HOP LOG ===
Get-content salon.log | Select-String "ERROR" >> tong_hop.txt
Get-content salon.log | Select-String "WARNING" >> tong_hop.txt

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===
 
 2 0 2 6 - 1 1 - 2 8   0 9 : 5 3 : 3 5   [ E R R O R ]   K h o n g   t i m   t h a y   t r a n g   / k i e u - t o c - m o i   ( 4 0 4 ) 
 
 2 0 2 6 - 1 1 - 2 8   0 9 : 5 7 : 3 5   [ E R R O R ]   K h o n g   t i m   t h a y   t r a n g   / k i e u - t o c - m o i   ( 4 0 4 ) 
 
 2 0 2 6 - 1 1 - 2 8   1 0 : 1 3 : 3 5   [ E R R O R ]   D a t   l i c h   t h a t   b a i 
 
 2 0 2 6 - 1 1 - 2 8   1 0 : 3 3 : 3 5   [ E R R O R ]   D a t   l i c h   t h a t   b a i 
 
 2 0 2 6 - 1 1 - 2 8   1 0 : 3 7 : 3 5   [ E R R O R ]   T h a n h   t o a n   b i   t u   c h o i 
 
 
 
 
 
 
 
 2 0 2 6 - 1 1 - 2 8   0 9 : 3 3 : 3 5   [ W A R N I N G ]   A n h   k i e u   t o c   d u n g   l u o n g   l o n 
 
 2 0 2 6 - 1 1 - 2 8   0 9 : 3 7 : 3 5   [ W A R N I N G ]   L i c h   t o i   t h u   s a u   s a p   k i n 
 
 2 0 2 6 - 1 1 - 2 8   1 0 : 0 1 : 3 5   [ W A R N I N G ]   A n h   k i e u   t o c   d u n g   l u o n g   l o n 
 
 2 0 2 6 - 1 1 - 2 8   1 0 : 0 9 : 3 5   [ W A R N I N G ]   T h o i   g i a n   p h a n   h o i   c h a m 
 
 
 
 
 
 
```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_salon_thang_11.xlsx`, không cần ghi vào đây.
