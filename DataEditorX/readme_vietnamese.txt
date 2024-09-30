# [DataEditorX]
Lưu ý: Đây là phiên bản đã được sửa đổi. Bạn có thể tải xuống phiên bản gốc tại đây:

[URL]https://github.com/247321453/DataEditorX/raw/master/win32/win32.zip [URL]

## Môi trường hoạt động (Environment)
Chương trình này được phát triển dựa trên .Net framework 2.0 (3.5).
DLL bắt buộc:
System.Data.SQLite.dll				Database Operations
FastColoredTextBox.dll				Script Editing
WeifenLuo.WinFormsUI.Docking.dll	Multiple Tags
winXP	(need to install .Net2.0)
win7	(comes with .Net2.0)
win8	(need to install .Net3.5 including 2.0)

## Cài đặt cấu hình ứng dụng
Bạn có thể thiết lập Cấu hình ứng dụng trong cửa sổ Cấu hình ứng dụng.
Không nên chỉnh sửa lưới dữ liệu trong cửa sổ Cấu hình ứng dụng hoặc chỉnh sửa trực tiếp tệp config trừ khi thực sự cần thiết.

## File liên kết
.cdb	(bắt buộc)DataEditorX
.lua	(Tùy chọn) Notepad++/Sublime text/DataEditorX
### Phương thức:
Left Click vào File Menu, chọn Mở tệp, duyệt tìm file, chựa chọn, click OK.
Right Click vào File, chọn mở tệp bằng, duyệt tìm ứng dụng, lựa chọn, click OK.
Lưu ý: Theo mặc định, .lua sẽ được mở bằng chương trình này. Nếu bạn cần sửa đổi nó, hãy đặt Open File trong cửa sổ Cấu hình ứng dụng thành false.

## Cài đặt
★ DataEditorX.exe.config
★ Language settings
★ Image settings
★ CodeEditor settings
★ data/language_xxx.txt		Ngôn ngữ giao điện và văn bản hiển thị.
★ data/cardinfo_xxx.txt		Series, Loại, Chủng tộc, Nguyên mẫu, Thuộc tính, Cấu độ/Xếp hạng/Cấp liên kết, Hạng mục.
★ data/constant.lua			Danh sách của (hầu hết) hằng số và mô tả của chúng được sử dụng trong EDOPro
★ data/_functions.txt		Danh sách của (hầu hết) hàm và mô tả của chúng được sử dụng trong EDOPro

## Cài đặt ngôn ngữ
Bạn có thể tự thêm tệp ngôn ngữ vào folder data. Tối thiểu cần phải có 2 file. Tên file ngôn ngữ phải theo định dạng:
language_xxx.txt
cardinfo_xxx.txt	
Với xxx là ngôn ngữ mà bạn muốn.
Đối với danh sách các hàm và hằng số, bạn có thể xóa mọi thứ trong các file data/constant.lua và data/_functions.txt
Sau đó copy mọi thứ trong các file tương ứng từ folder data/constants và data/functions rồi dán vào các file đã xóa.
LƯU Ý: Đảm bảo bạn đã có đầy đủ các file ngôn ngữ khi thực hiện thao tác này.
Các ngôn ngữ hiện có:
- Tiếng Anh
- Tiếng Việt Nam
- Tiếng Trung Quốc phồn thể
- Tiếng Trung Quốc giản thể
- Tiếng Nhật

## Cài đặt cấu hình ứng dụng
Left Click vào Windows, Configuration, Load Data.

### Cài đặt hình ảnh
- Chất lượng hình ảnh: chấp nhận số tự nhiên từ 1~100
- Kích thước mặc định: chấp nhận số tự nhiên theo định dạng a,b (chỉ chấp nhận số tự nhiên, a cho chiều rộng, b cho chiều cao)

- Kích thước hình ảnh: Kích thước của hai hình ảnh được xuất ra.
- Kích thước khác: Kích thước của phần được cắt của hình ảnh thông thường.
- Kích thước eXceed: Kích thước của phần được cắt của hình ảnh eXceed.
- Kích thước Pendulum: Kích thước của phần được cắt của hình ảnh pendulum.
Chấp nhận số tự nhiên theo định dạng a,b,c,d

### Cài đặt tem độ hiếm
★ Vị trí đặt tem trên hình ảnh được xuất theo thứ tự: Tem trên hình ảnh nhỏ - Tem trên hình ảnh lớn.
Các vị trí khả dụng:
- Top_Left
- Top_Right
- Bottom_Left
- Bottom_Right
★ Kích thước tem: chấp nhận số tự nhiên theo định dạng a,b,c,d
★ Căn lề tem: chấp nhận số nguyên theo định dạng a,b,c,d làm tọa độ đặt tem (hệ trục tọa độ Oxy, với O ở góc trên-trái, Ox hướng sang phải, Oy hướng xuống dưới).
Chấp nhận tọa độ âm, nhưng nó không được nhỏ hơn (kích thước tem * (-1)) và không được lớn hơn kích thước của hình ảnh được xuất ra (theo từng cạnh tương ứng).

### Giá trị chấp nhận:
★ "a,b,c,d"
- a: Chiều rộng hình ảnh nhỏ
- b: Chiều cao hình ảnh nhỏ
- c: Chiều rộng hình ảnh lớn
- d: Chiều cao hình ảnh lớn

★ Đối với lề tem
- a: Khoảng cách từ cạnh tem (cạnh song song với trục Oy, cạnh trái nếu vị trí tem là X_Left, cạnh phải nếu là X_Right) tới cạnh tương ứng của hình ảnh cơ sở (hình ảnh nhỏ).
- b: Khoảng cách từ cạnh tem (cạnh song song với trục Ox, cạnh trên nếu vị trí tem là Top_X, cạnh dưới nếu là Bottom_X) tới cạnh tương ứng của hình ảnh cơ sở (hình ảnh nhỏ).
- c: Khoảng cách từ cạnh tem (cạnh song song với trục Oy, cạnh trái nếu vị trí tem là X_Left, cạnh phải nếu là X_Right) tới cạnh tương ứng của hình ảnh cơ sở (hình ảnh lớn).
- d: Khoảng cách từ cạnh tem (cạnh song song với trục Ox, cạnh trái nếu vị trí tem là Top_X, cạnh dưới nếu là Bottom_X) tới cạnh tương ứng của hình ảnh cơ sở (hình ảnh lớn).

### Cài đặt mã
★ Font chữ: Font được sử dụng trong cửa sổ CodeEditor, mặc định sử dụng font Consolas
★ Font Size: Font size được sử dụng trong cửa sổ CodeEditor, mặc định sử dụng size 14.5
★ Phương thức nhập: Sử dụng phương thức nhập sẽ hiển thị văn bản như bình thường, nhưng tốc độ phản hồi sẽ chậm đi
★ Line Wrap: Tự động ngắt dòng.
★ Tab-Space: Tự động chuyển đổi Tab sang Space
★ Async Load: true: Tải dữ liệu nền không đồng bộ (hiển thị nhanh), false: Tải dữ liệu trực tiếp
★ Change Card File: Khi sửa đổi hoặc xóa thẻ, hình ảnh và nội dung của thẻ cũng sẽ bị xóa, sửa đổi hoặc sao chép.
★ Open File: Mở lua bằng trình soạn thảo tập lệnh tích hợp sẵn.
★ Check Update: Kiểm tra cập nhập
★ Auto Rarity: Tự động sử dụng độ hiếm cho hình ảnh MSE

## DataEditor

### ATK/DEF
Để đặt chỉ số ATK/DEF là '?', bạn có thể viết ?, ?, -2.
Folder pics và script sẽ nằm cùng trong một folder mẹ với tệp .cdb

### Đổi Card ID
Khi click Sửa đổi, nếu bạn chọn Delete, thao tác này sẽ trực tiếp thay đổi ID card (tạo một bản sao với ID mới và xóa bản gốc)
Nếu không chọn Delete, thao tác này sẽ chỉ tạo một bản sao của Card gốc với ID mới.

### Cài đặt tem độ hiếm
Chỉ cần đặt hình ảnh bất kỳ vào folder data/stamps, và nó sẽ hiển thị trong combobox độ hiếm.
Chỉ chấp nhận hình ảnh .png
Bạn có thể sử dụng bất kỳ tên file nào, ngoại trừ "None.png"

### Cài đặt kích thước hình ảnh
★ Auto Size
Bạn có thể điền kích thước chiều rộng của hình ảnh xuất ra vào ô chiều rộng, sau đó click Auto Size, sẽ tự động tính toán kích thước chiều cao theo tỉ lệ mặc định nếu ô chiều cao trống.
Tương tự, nhập kích thước chiều cao để tự động tính toán kích thước chiều rộng.
Nếu cả hai ô chiều cao và chiều rộng đều trống, sẽ tự động thiết lập theo kích thước mặc định (được thiết lập trong cửa sổ cấu hình ứng dụng)
Nếu cả hai ô đều chứa kích thước nhưng không hợp lệ (chiều rộng > chiều cao), sẽ tự động đảo ngược hai giá trị này.

★ Set Size
Thiết lập kích thước hình ảnh xuất ra dựa trên kích thước từ hai ô chiều rộng và chiều cao.
Hình ảnh lớn sẽ có kích thước của hai ô chiều rộng và chiều cao được nhập.
Hình ảnh nhỏ theo mặc định sẽ có kích thước mỗi chiều bằng 1/4 kích thước của hình ảnh lớn.
Bạn có thể thiết lập kích thước hình ảnh trong cửa sổ Cấu hình ứng dụng.

## Đọc danh sách card từ file .ydk và pics folder
Hỗ trợ: card ID, card name (.png, .jpg)

## Lưu trữ MSE
### Đọc
Cấu trúc file lưu trữ (yêu cầu: nội dung từng card, đầu tiên là "card", kết thúc là "gamecode", đổi gamecode thành phần thử cuối trong card_fields của MSE
card
	...
gamecode: 123456
card
	...
gamecode: 456789

### Hình ảnh
Hỗ trợ: card ID, card name (.png, .jpg)
Khi "Set MSE'Image" được chọn, hình ảnh card sẽ được đặt trong folder MSE Image

## Trích xuất dữ liẹu
Ví dụ: mydiy.cdb
- New card: deck/mydiy.ydk
- Description: mydiy.txt
- Script
- Pictures

Tạo mydiy.zip, có thể được đặt trong expansions, được sử dụng trực tiếp hoặc có thể dùng để xuất bản.

## So sánh Database
★ Chức năng tìm kiếm lua
Nhận các hàm Lua từ mã nguồn C++
Kiểu trả về, kiểu tham số, mã triển khai C++.

★ Bản sao card:
Bản sao thay thế: Nếu có thẻ thì thay thế thẻ mới nhất
Sao chép không thay thế: bỏ qua nếu thẻ tồn tại

★ Tìm kiếm thẻ
1. Chỉ hỗ trợ tìm kiếm tên Series đầu tiên và chưa hỗ trợ tìm kiếm Pendulum Scale.
2. Hỗ trợ card name, mô tả effect, quy tắc, thuộc tính, cấp độ, chủng tộc, loại thẻ, loại hiệu ứng, ID
3.ATK, DEF tìm kiếm:
Nếu là 0, hãy nhập -1 hoặc .search
Nếu là ?, hãy nhập -2 hoặc ? tìm kiếm
4. Tra cứu tên thẻ:
AOJ%% bắt đầu bằng "AOJ"
Liu%%tian bắt đầu bằng "liu" và kết thúc bằng "tian"
%%Warrior kết thúc bằng "Warrior"
5. Ví dụ tìm kiếm phạm vi mật khẩu:
--ID hoặc card trùng tên là 10000000. ID card: 10000000 card trùng tên: 0
--Card cùng tên với 10000000. ID Card: 0 Card cùng tên: 10000000
--Card có ID lớn hơn 10000000 và nhỏ hơn 20000000. Card có cùng tên: 10000000 ID card: 20000000

## CodeEditor
Nhập từ khóa vào hộp văn bản bên dưới và nhấn Enter
Ctrl+F Tìm
Ctrl+H Thay thế
Ctrl + chuột trái nhảy tới định nghĩa hàm
Danh sách chức năng Ctrl+K
Ctrl+T danh sách hằng số
Ctrl+thu phóng văn bản bằng con lăn chuột

# Magic Set Editor 2
下载/更新："Magic Set Editor 2/download.bat"
或者
https://github.com/247321453/MagicSetEditor2

## Cài đặt tạo kho lưu trữ MSE
Sửa đổi \r\n trong mse_xxx.txt của từng ngôn ngữ và nó sẽ được thay thế bằng dòng mới và \t sẽ được thay thế bằng tab.
Chuyển đổi tiếng Trung giản thể sang tiếng Trung phồn thể,
cn2tw = false
Số lượng tối đa của mỗi kho lưu trữ, 0 là không giới hạn
maxcount = 0
Tìm một hình ảnh từ thư mục bên dưới và thêm nó vào kho lưu trữ. Tên là pass/card name.png/jpg.
imagepath = ./Images
Dấu bẫy ma thuật, %% được thay thế bằng ký hiệu Nếu chỉ là %%, bạn cần đặt dấu ST sau là văn bản: yes.
spell = [Spell Card%%]
trap = [Trap Card%%]
Game yugioh, phong cách chuẩn, ngôn ngữ CN, Edition: MSE, hình giữa quái P không chứa vùng chữ P
head = phiên bản mse: 0.3.8\r\ngame: yugioh\r\nstylesheet: Standard\r\nset info:\r\n\tlingu: CN\r\n\tedition: MSE\r\n\tST mark là văn bản: không\r\n\thình ảnh con lắc nhỏ: có
Đọc lưu trữ, mô tả thẻ
text =[Hiệu ứng vung kiếm]\n%ptext%\n[Hiệu ứng quái vật]\n%text%\n
Nhận văn bản P
con lắc-text = 】[\s\S]*?\n([\S\s]*?)\n♥
Nhận văn bản quái vật
monster-text = [trái cây | giới thiệu | báo cáo mô tả]]\n([\S\s]*)
Thay thế chữ số đặc biệt
thay thế = ([韟|鱇|・|·]) <i>$1</i>
Thay thế dấu cách bằng ^, (độ rộng 1/3 ký tự)
#replace = \s <sym-auto>^</sym-auto>
Thay thế A-Z bằng phông chữ khác
#replace = ([A-Z]) <i>$1</i>
