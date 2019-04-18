# Naming Convention

## camelCase

Ký tự đầu tiên của từ đầu tiên viết thường, những ký tự đầu tiên của những từ tiếp theo viết hoa.
	
````
Ví dụ: productName, productPrice, thisIsTheNameFollowTheCamelCase
````    
    
   
## PascalCase

Cú pháp: viết hoa chữ cái đầu tiên của mỗi từ.
```
Ví dụ: ProductName, ProductPrice, ThisIsTheNameFollowThePascalCase
```

## snake_case

Cú pháp: Tất cả các chữ cái đều viết thường, và các từ cách nhau bởi dấu gạch dưới.
```
Ví dụ: product_name, product_price, this_is_the_name_follow_the_snake_case
```




– Tên lớp: đặt theo PascalCase.

– Tên biến, tên hàm: đặt theo camelCase hoặc snake_case.

– Hằng số: đặt theo UPPER_CASE. VD: CLICK_COUNTER.

– Tên biến, tên lớp: thường là danh từ, cụm danh từ hoặc tính từ. VD: UserModel, userName, downloadCounter, isDownloaded.

– Tên hàm thường** bắt đầu bằng động từ**. VD: getUserName, setUserName, increaseDownloadCounter.

– Tên phải có nghĩa, không được đặt tên kiểu viết tắt. VD: uName, pName, idl, a, a1, doFA.

– Tránh đặt những tên quá chung chung, tối nghĩa. VD: top, doIncrease, getAll.

# Quy tắc về số lượng

– Hàm không nên quá 30 dòng.

– Lớp không nên vượt quá 500 dòng. (Clean Code).

– Một hàm không được vượt quá 5 tham số. (nên giữ <=3).

– Một hàm chỉ làm duy nhất 1 việc, trong trường hợp cần thiết, có thể cho phép làm 2 việc, tuy nhiên tên hàm phải nói rõ điều này. VD: increaseDownloadCounterAndSaveToDatabase.

– Khi khai báo biến, một dòng chỉ chứa một biến.

– Một dòng không nên dài quá 80 ký tự (Oracle).

– Các câu lệnh lồng nhau tối đa 4 cấp.

# Quy tắc xuống hàng

- Nếu có dấu "," thì xuống hàng sau dấu ",".

- Xuống hàng trước toán tử + - ...

- Nếu có nhiều cấp lồng nhau, thì xuống hàng theo từng cấp.

- Dòng xuống hàng mới thì được bắt đầu ở cùng cột với đoạn lệnh cùng cấp ở trên.

# Comment

- Hạn chế dùng comment để giải thích code, thay vào đó hãy cải thiện đoạn code của bạn.

- Chỉ nên dùng comment khi viết documentation cho thư viện, thông tin đính kèm cho class …