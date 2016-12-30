# MongoDB là gì?

Hiểu một cách nôm na thì **MongoDB** là một mã nguồn mở và là một tập tài liệu dùng cơ chế **NoSQL** để truy vấn, nó được viết bởi ngôn ngữ C++. Chính vì được viết bởi C++ nên nó có khả năng tính toán với tốc độ cao chứ không giống như các hệ quản trị CSDL hiện nay.

Nếu như bạn biết sử dụng **JSON** thì trong **MongoDB** cũng có cấu trúc lưu trữ tương tự, chính vì thế nó có hiệu suất cao, tương tác nhanh và khả năng mở rộng tốt, nó hoạt động trên khái niệm **collection**  và **document**. Tới đây thì có lẽ bạn sẽ thắc mắc collection là gì? và document là gì? phải  không nào? Nếu vậy thì ta sẽ tìm hiểu các phần tiếp theo nhé.

# Database là gì?

Database là một Ô chứa dữ liệu ở mức vật lý (physical), mỗi database sẽ có nhiều collection và được thiết lập lưu trữ ở một nơi trong máy chủ máy tính. Một máy chủ MongoDB thường có thể tạo nhiều cơ sở dữ liệu.

# Collection là gì?

Collection trong MongoDB là nhóm các tài liệu (document), nó tương đương với một bảng (table) trong CSDL thông thường nên mỗi collection sẽ thuộc về một database duy nhất. Tuy nhiên nó có một sực khác biệt đó là nó không có ràng buộc Relationship như các hệ quản trị CSDL khác nên việc truy xuất rất nhanh, chính vì thế mỗi collection có thể chứa nhiều thể loại khác nhau không giống như table trong hệ quản trị mysql là các field cố định.

# Document là gì?

Document trong MongoDB có cấu trúc tương tự như kiểu dữ liệu JSON, nghĩa là sẽ có các cặp (key => giá trị) nên nó có tính năng động rất lớn. Document ta có thể hiểu nó giống như các record dữ liệu trong MYSQL, tuy nhiên nó có sự khác biệt là các cặp (key => value) có thể không giống nhau ở mỗi document. 

Để rõ hơn chúng ta sẽ so sánh MongoDB và một hệ quản trị CSDL khác nhé.
So sánh giữa RDBMS và MongoDB
```
RDBMS 	          MongoDB
Database 	       Database
Table 	          Collection
Tuple/Row 	       Document
column 	          Field
Table Join 	       Embedded Documents
Primary Key 	    Primary Key (mặc định là _id)
```
Để rõ ràng hơn chúng ta sẽ tìm hiểu thông qua một ví dụ về cách lưu trữ trong MongoDB nhé.
```
{
   _id: ObjectId(7df78ad8902c)
   title: 'Tìm hiểu mongodb', 
   description: 'MongoDB sử dụng khái niệm NO-SQL',
   comments: [  
      {
         user:'user1',
         message: 'First comment',
         dateCreated: new Date(2011,1,20,2,15),
         like: 0 
      },
      {
         user:'user2',
         message: 'Second comment',
         dateCreated: new Date(2011,1,25,7,45),
         like: 5
      }
   ]
}
```
Trong đó ta thấy key _id là do hệ thống tự tạo ra một field như vậy làm khóa chính. Đây là cấu trúc của một mẫu document trong MongoDB, như vậy khi có thêm comment thì ta sẽ thêm nó vào phần comment của tin.

# Khi nào sử dụng MongoDB

MongoDB thật sự rất hot nhưng không phải lúc nào ta sử dụng nó cũng tốt, có những trường hợp không nên sử dụng và nên sử dụng, chi tiết thế nào thì chúng ta cùng thảo luận nhé.

Nếu website của bạn có tính chất INSERT cao, bởi vì mặc định MongoDB có sẵn cơ chế ghi với tốc độ cao và an toàn.

Website của bạn ở dạng thời gian thực nhiều, nghĩa là nhiều người thao tác với ứng dung. Nếu trong quá trình load bị lỗi tại một điểm nào đó thì nó sẽ bỏ qua phần đó nên sẽ an toàn.

Website bạn có nhiều dữ liệu quá, giả sử web bạn có đến 10 triệu records thì đó là cơn ác mộng với MYSQL. Bởi vì MongoDB có khả năng tìm kiến thông tin liên quan cũng khá nhanh nên trường hợp này nên dùng nó.

Máy chủ không có hệ quản trị CSDL, trường hợp này thường bạn sẽ sử dụng SQLITE hoặc là MongoDB.


# Lời kết

Với nhưng ưu điểm của MongoDB thì trong tương lai nó sẽ thay thế các hệ quản trị CSDL, tuy nhiên theo bản thân mình nghĩ thì điều này cũng khó có thể xảy ra, bởi vì các ứng dụng web vừa và nhỏ nếu được xây dựng bằng MYSQL thì sẽ nhanh hơn nhiều MongoDB. Vì thế hãy cân nhắc trước khi sử dụng nhé. Bài tiếp theo chúng ta sẽ tìm hiểu dịch vụ mongolab.com nhé, đây là một dịch vụ theo mình khá tiện dùng đẻ học mongodb.
