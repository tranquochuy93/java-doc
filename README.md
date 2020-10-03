## JDK
- JDK (  JRE ( JVM +  Các thư viện phục vụ cho runtime của JVM ) + Development Tool: javac, java )
- JVM ( Classloader tải class file + Memory Area ( Class Area + Heap + Stack + ... )  + Execution Engine ( Virtual Processor + interpreter để đọc bytecode và thực thi )
- code ->javac compiler -> bytecode(.class file) ->JVM thông dịch -> mã máy phụ thuộc vào nền tảng
## OOP
#### Overiding vs Overloading
| Overloading(nap chong)   | Overiding(ghi de)
|--------------|-------|
| giúp code của chương trình dễ đọc hơn.|  cài đặt cụ thể cho phương thức được khai báo ở lớp cha | 
| được thực hiện bên trong một class.   |  trong 2 class có quan hệ kế thừa. | 
| tham số phải khác nhau   |  tham số phải giống nhau | 
| là ví dụ về đa hình lúc biên dịch|  là ví dụ về đa hình lúc runtime | 
| Giá trị trả về có thể giống  hoặc nhau.  |  Giá trị trả về phải giống nhau.| 
#### Final
- variable: k thay đổi giá trị dc
- method: k được ghi đè
- class: final
#### Static
- variable: chung cho tất cả object
- method: thuộc lớp chứ k phải thuộc object, k cần instance, có thể truy cập biến static và thay đổi giá trị của nó
#### Abstract vs Interface
| Abstract   | Interface
|--------------|-------|
| có thể có phương thức có nội dung (các phương thức tường minh).|  chỉ có các phương thức trừu tượng. | 
| có thể có các biến instance.    |  không thể có các biến instance | 
| có thể có constructor.   |  không thể có constructor. | 
| có thể có các phương thức static.|   không thể có các phương thức static. | 
| có thể extends một lớp abstract.  |  có thể implement nhiều interface.| 
