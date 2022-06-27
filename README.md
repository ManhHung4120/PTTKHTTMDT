# Hệ thống nhận diện vân tay sử dụng trích rút đặc trưng điểm bất thường
	1. Trích rút tọa độ và nhãn phân loại
Sau bước tiền xử lý ảnh, vân tay có thể sử dụng để tìm các điểm bất thường thông qua việc tính toán crossing number(CN) của điểm ảnh đó:
Bước 1 : Tại mỗi điểm ảnh x có tọa độ i, j ta chọn một vùng có kích cỡ 3x3 pixel có tọa độ trong khoảng [i-1:i+1, j-1:j+1]
Bước 2 : Khảo sát trị tuyệt đối của hiệu các cặp giá trị logic của các điểm ảnh xung quanh điểm ảnh [i,j] ở chính giữa cửa sổ đó bằng công thức:
CN =  1/2  ∑_(i=1)^8 |P_i-P_(i+1) |,     P_9=P_1

Trong đó, P1, P2… P8 thứ tự tạo thành các điểm lân cận điểm giữa cửa sổ [i,j] đang khảo sát, xét theo chiều thuận hoặc ngược kim đồng hồ.
 Bước 3 : Tùy kết quả tính toán của biểu thức crossing number thì kết luận ràng là điểm phân nhánh hay điểm kết thúc hoặc điểm trên đường vân.
Điểm [i,j] đang xét có đặc điểm là: 
	Không phải điểm bất thường nếu CN(p) = 2
	Điểm kết thúc nếu  CN(p) = 1
	Điểm phân nhánh nếu CN(p) = 3
 

	2. Trích rút hướng cục bộ 

	Vân tay có thể được coi là mô hình kết cấu định hướng. Trường định hướng của vân tay là hướng cục bộ của các đường vân nằm trên vân tay.
	Hướng cục bộ của điểm ảnh (i,j) được xác định như sau :
	 

	Điểm màu xanh là điểm bất thường cần xét hướng cục bộ.
	Ý tưởng : Xét cửa sổ 6 x 6 pixel bao quanh điểm ảnh và các mép của cửa sổ như hình trên. Tính độ dài cạnh đối và cạnh kề để ra góc như hình. Hướng cục bộ sẽ là góc của trục Ox của góc phần tư thứ nhất hợp với OC theo chiều ngược kim đồng hồ nếu OC nằm ở góc phần tư thứ I và II và theo chiều cùng chiều kim đồng hồ nếu OC nằm ở góc phần tư thứ III và IV
