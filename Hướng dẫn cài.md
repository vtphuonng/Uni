- clone code về dùng lệnh 'git clone https://github.com/vtphuonng/Uni.git'
## Cấu trúc thư mục:
- Datasource/OriginData: file dữ liệu gốc
- Datasource/ModifiedData: chứa dataset sau khi đã chọn được cột và ghép dữ liệu các cột được chọn của các file dữ liệu gốc lại với nhau
- file MergeData.ipynb dùng để chọn cột trong 3 dataset (air pollution, water pollution, Solar uv pollution). Hiện đang thử 2 cách merge:
    - Cách 1: phân cụm từng file một. Sau khi có kết quả phân cụm của cả 3 file (giả sử tên cột chứa kết quả phân cụm của từng file có tên lần lượt là x,y,z)-> ghép kết quả phân cụm của 3 file vào một dataframe mới và dataframe đó có giá trị của 3 cột x,y,z có tên tương ứng lần lượt trong dataframe là air, uv, water -> phân cụm với dataframe mới được ghép và lưu kết quả vào một cột mới trong dataframe đó có tên 'classification' -> ghép dữ liệu số từ 3 file với cột mới 'classification' được file dataset mới và lưu trơng 'DataSource/ModifiedData/C1_PollutionsDataset.csv'
    - Cacsh2: chọn các cột sử dụng ở các file dữ liệu gốc rồi ghép với nhau tạo thành một bộ dataset mới, sau đó tiến hành phân cụm đối với bộ dataset và lưu trong 'DataSource/ModifiedData/C2_PollutionsDataset.csv'
- Linear_Regg.ipynb: dùng linear regression để thử dự đoán ảnh hưởng của môi trường đối với cả 2 dataset có từ file MergeData.ipynb
- Kết quả: file dataset ghép theo cách 2 có kết quả đánh giá cao hơn cách 1 khi sử dụng linear regression