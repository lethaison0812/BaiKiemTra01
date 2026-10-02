Câu 1: Phân biệt Value Types và Reference Types trong C#

Trong C#, dữ liệu được chia thành hai nhóm chính là Value Types (kiểu giá trị) và Reference Types (kiểu tham chiếu).

Value Type là kiểu mà biến lưu trực tiếp giá trị của dữ liệu. Khi gán một biến Value Type cho biến khác thì giá trị được sao chép, vì vậy hai biến hoạt động độc lập. Các kiểu thường gặp gồm int, double, bool, char, struct, enum.

Reference Type là kiểu mà biến lưu một tham chiếu đến đối tượng. Đối tượng thường được cấp phát trên Heap. Khi gán một Reference Type cho biến khác, reference được sao chép nên hai biến có thể cùng tham chiếu đến một đối tượng.

Về bộ nhớ, cách hiểu cơ bản là Value Type thường được lưu trên Stack khi là biến cục bộ, còn Reference Type có đối tượng thường được lưu trên Heap và biến chứa reference đến đối tượng đó. Tuy nhiên, không nên hiểu tuyệt đối rằng mọi Value Type luôn nằm trên Stack và mọi Reference Type luôn nằm trên Heap, vì vị trí thực tế còn phụ thuộc vào ngữ cảnh và cách CLR/JIT quản lý bộ nhớ.

Câu 2: Sự khác nhau giữa init và set

set thông thường cho phép thuộc tính được thay đổi sau khi đối tượng đã được tạo.

Trong khi đó, init cho phép thuộc tính được thiết lập trong quá trình khởi tạo đối tượng, nhưng sau khi quá trình khởi tạo hoàn tất thì thuộc tính không thể được gán lại.

Vì vậy, init giúp tạo ra các đối tượng có tính bất biến một phần, hạn chế việc thay đổi dữ liệu ngoài ý muốn sau khi đối tượng được khởi tạo.

init phù hợp trong các trường hợp như DTO, dữ liệu cấu hình, request model hoặc các đối tượng mà một số thuộc tính chỉ cần xác định một lần khi khởi tạo.

Tóm lại:

set: Có thể gán và thay đổi giá trị sau khi object được tạo.

init: Chỉ cho phép thiết lập giá trị trong quá trình khởi tạo object.

Câu 3: Phân biệt virtual và override trong tính Đa hình

virtual và override được sử dụng để triển khai Polymorphism (tính đa hình) trong C#.

virtual được khai báo ở lớp cha, cho phép phương thức đó được lớp con ghi đè và cung cấp cách triển khai riêng.

override được khai báo ở lớp con, dùng để ghi đè phương thức virtual của lớp cha bằng một cách triển khai mới.

Khi chương trình gọi một phương thức virtual thông qua reference của lớp cha, phương thức được thực thi có thể phụ thuộc vào kiểu thực tế của đối tượng. Đây là cơ chế đa hình tại thời điểm chạy (Runtime Polymorphism).

Tóm lại:

virtual: Khai báo ở lớp cha và cho phép lớp con ghi đè.

override: Khai báo ở lớp con để ghi đè phương thức của lớp cha.

Cặp virtual và override giúp C# thực hiện tính đa hình.

Câu 4: Tại sao thành phần static không thể truy xuất thông qua Object Instance?

Trong C#, thành phần được khai báo static thuộc về Class, không thuộc về một Object Instance cụ thể.

Thành phần static chỉ có một bản dùng chung ở cấp độ lớp, bất kể có bao nhiêu object của lớp đó được tạo ra.

Ngược lại, các instance member thuộc về từng object. Mỗi object có thể có một trạng thái riêng đối với các thành phần này.

Do đó, thành phần static được truy cập thông qua tên lớp, còn instance member được truy cập thông qua object instance.

Nguyên nhân không thể truy xuất static thông qua instance là vì static không gắn với một vùng dữ liệu riêng của từng object. Nó tồn tại ở cấp độ Class và được chia sẻ giữa các instance.

Tóm lại:

Static member → thuộc về Class → dùng chung.

Instance member → thuộc về Object → mỗi object có dữ liệu riêng.
