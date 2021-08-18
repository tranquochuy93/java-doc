## Trick

````java
public class HelloWorld{

     public static void main(String []args){
        System.out.println(roundAvoid(0.00000000001, 2)); // 0.01
     }
     
     public static double roundAvoid(double value, int places) {
        double scale = Math.pow(10, places);
        return Math.ceil(value * scale) / scale;
    }
}
```

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
## Collection
#### Set: 1 phần tử xuất hiện duy nhất 1 lần
  - TreeSet: các phần tử được sắp xếp
  - HashSet: lưu trữ dưới dạng hash table
  - EnumSet: các phần tử là enum, k phải object
  - HashSet không duy trì thứ tự nào, trong khi TreeSet duy trì thứ tự tăng dần.
  - Set chỉ chứa giá trị, trong khi Map chứa cặp key và value.
#### List: Các phần tử được sx theo thứ tự xác định, các phần tử có thể giống nhau
 - ArrayList: 1 mảng có thể thay đổi kích thước được
 - LinkedList: double linked list , non-synchronized
 - Vector: giống arraylist, nhưng synchronized
 - Stack: LIFO(last-in-first-out) 

#### Queue: FIFO
 - LinkedList
 - PriorityQueue: các phần tử được sx
 - ArrayDeque: queue 2 chiều

#### Map: quản lý dưới dạng Key-Value
 - TreeMap: các key đã được sắp xếp, thời gian thêm = sửa = xóa = O(logn)
 - HashMap: các key lưu trữ dưới dạng hashmap, cho phép tìm kiếm nhanh O(1).
 - EnumMap: các key là enum chứ k phải object
 - WeakHashMap: phần tử sẽ bị xóa khi key được giải phóng hay không còn một biến nào tham chiếu đến key nữa

#### Array vs ArrayList
| Array   | ArrayList
|--------------|-------|
| Kích thước cố định.  |  Kích thước có thể thay đổi được. | 
| Có thể lưu trữ dữ liệu kiểu nguyên thủy và đối tượng.    |  Chỉ có thể lưu trữ dữ liệu kiểu đối tượng. Kể từ Java 5, kiểu nguyên thủy được tự động chuyển đổi trong các đối tượng được gọi là auto-boxing. | 
| Tốc độ lưu trữ và thao tác nhanh hơn.   |  Tốc độ lưu trữ vào thao tác chậm hơn. | 
| Chỉ có thuộc tính length.|    Có nhiều phương thức để thao tác với dữ liệu. | 
#### ArrayList vs LinkedList
| ArrayList   | LinkedList|
|--------------|-------|
| sử dụng một mảng động.  |   sử dụng danh sách liên kết doubly. | 
|  không hiệu quả với thao tác vì cần nhiều chuyển đổi    |   hiệu quả cho thao tác.| 
| tốt hơn để lưu trữ và lấy dữ liệu  |   tốt hơn để thao tác dữ liệu | 

#### ArrayList vs Vector 
| ArrayList   | Vector  |
|--------------|-------|
| KHÔNG synchronized.  |    synchronized, các thread khác chỉ có thể sử dụng vector khi thread hiện tại giải phóng vector | 
|  được duyệt bởi Iterator    |   duyệt bởi Enumeration và Iterator| 
| Kích thước ArrayList chỉ được thay đổi khi thêm hoặc xóa phần tử   |   thay đổi kích thướng của Vector bằng phương thức setSize() | 
|  làm cho ArrayList đồng bộ bằng cách gọi phương thức: Collections.synchronizedList()    |    không thể hủy đồng bộ hóa | 
| không phải là legacy class.   |   là  legacy class. | 
| tăng kích thước của nó bằng 50% kích thước mảng   |   tăng kích thước của nó bằng cách nhân đôi kích thước mảng |   

#### Iterator  vs Enumeration  
| Iterator   | Enumeration  |
|--------------|-------|
| duyệt các phần tử legacy và non-legacy. |    chỉ có thể duyệt các phần tử legacy. | 
|  được duyệt bởi Iterator    |   duyệt bởi Enumeration và Iterator| 
| chậm hơn Enumeration.  |   nhanh hơn Iterator.| 

## Exception
- Checked exception : 
  - extends lớp Throwable ngoại trừ RuntimeException và Error
  - được kiểm tra tại thời gian biên dịch
- Unchecked exception
  - extends lớp RuntimeException
  - không được kiểm tra tại thời gian biên dịch
- finally 
  - dụng để thực thi các lệnh quan trọng như đóng kết nối, đóng cá stream,…
  - Khối lệnh finally trong java luôn được thực thi cho dù có ngoại lệ xảy ra hay không
    
#### throw  vs throws  
| throw    | throws  |
|--------------|-------|
| sử dụng để ném ra một ngoại lệ rõ ràng. |    sử dụng để khai báo một ngoại lệ. | 
|  Ngoại lệ checked không được truyền ra nếu chỉ sử dụng từ khóa throw.    |   Ngoại lệ checked được truyền ra ngay cả khi chỉ sử dụng từ khóa throws.| 
| Sau throw là một instance.  |  Sau throws là một hoặc nhiều class.| 
| Throw được sử dụng trong phương thức.  |    Throws được khai báo ngay sau dấu đóng ngoặc đơn của phương thức.| 
| Bạn không thể throw nhiều exceptions.  | Bạn có thể khai báo nhiều exceptions, Ví dụ: public void method()throws IOException,SQLException.| 

## Web
#### GET  vs POST  
| GET    | POST  |
|--------------|-------|
|  Số lượng dữ liệu được gửi cho mỗi request bị giới hạn, vì nó được gửi qua header |    Số lượng lớn dữ liệu được gửi cho mỗi request, vì nó gửi qua body. | 
|  Không an toàn vì người dùng nhìn thấy dữ liệu rõ ràng trên URL.    |   An toàn vì người dùng không nhìn thấy dữ liệu trên URL.| 

#### forward  vs sendRedirect  
| forward    | sendRedirect  |
|--------------|-------|
|  gửi yêu cầu tương tự tới một tài nguyên khác |    luôn luôn gửi yêu cầu mới vì nó sử dụng thanh URL của trình duyệt.. | 
|  hoạt động ở phía server.    |   hoạt động ở phía client.| 
|  chỉ hoạt động trong server.   |    hoạt động bên trong và bên ngoài server.| 

#### war, jar, pom
- jar: đóng gói class, chỉ cần import và sử dụng
- war: giống jar, nhưng là file build của webapp như servlet, maven
- pom: project để build jar và war
#### configuration
- servlet, jsp basic: sử dụng web.xml để mapping servlet
- maven: tạo ra các dependences để get thư viện : pom.xml
   - dependences -> import các thư viện, ví dụ javax.servlet
   - build: định nghĩa tên file war sẽ build ra
   - module: định nghĩa module con, parent project
   - parent: link to parent project
- osgi: tạo plug-in project
  - java khi chỉnh sửa phải build và start lại server, còn osgi thì không cần build lại
  - osgi định nghĩa activator, từ đó có thể gọi qua servlet 
    Có thể dùng response.getWriter().println để out string về client
đối với japanese, dùng response.setContentType("text/html; charset=UTF-8");
response.setCharacterEncoding("UTF-8");
```js
 response.getWriter().println;
 response.setContentType("text/html; charset=UTF-8"); // japanese
```
## Spring MVC
- @Service là một annotation, nó được sử dụng để chú thích trên một class để nói với Spring rằng class đó là một Spring BEAN

- @Autowired được chú thích trên một trường (field) để nói với Spring rằng hãy tiêm (inject) giá trị vào cho trường đó. Chú ý: Từ tiêm ở đây có ý giống với gán giá trị cho trường đó.

- @Repository là một annotation, nó được sử dụng để chú thích trên một class để nói với Spring rằng class này là một Spring BEAN.

- @Component là một annotation, nó được chú thích trên một class để nói với Spring rằng class này là một Spring BEAN.

- Không có sự khác biệt về cách sử dụng của @Service, @Component và @Repository

- @Configuration là một annotation, nó được chú thích trên một class, class này sẽ định nghĩa các Spring BEAN.
 
- @ComponentScan - Nói cho Spring các package để tìm kiếm các Spring BEAN khác, Spring sẽ quét (scan) các package đó để tìm kiếm.

- Các Spring BEAN được tạo ra sẽ được quản lý trong Spring IoC Container (Bộ chứa Spring IoC).





