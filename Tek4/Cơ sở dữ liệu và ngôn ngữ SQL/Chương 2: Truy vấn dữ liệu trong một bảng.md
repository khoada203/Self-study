# 1. Trích xuất dữ liệu

SELECT * <br>
FROM xe;

# 2. Lựa chọn một cột

SELECT hang_xe <br>
FROM xe;

# 3. Lựa chọn nhiều cột

SELECT <br>
  loai_xe, <br>
  gia <br>
FROM xe;

# 4. Chọn một vài hàng

SELECT * <br>
FROM xe <br>
WHERE nam_san_xuat = 2022;

# 5. Toán tử điều kiện
- < (nhỏ hơn), > (lớn hơn), <= (nhỏ hơn hoặc bằng), >= (lớn hơn hoặc bằng).

SELECT * <br>
FROM xe <br>
WHERE gia > 1000000000;

