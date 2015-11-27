#Mô hình OSI
Mô hình mạng mà Windows và hầu hết các hệ điều hành mạng khác sử dụng được gọi là mô hình OSI. Thuật ngữ OSI được viết tắt bởi cụm từ tiếng Anh Open System Interconnection Basic Reference. Mô hình này gồm có bảy lớp khác nhau. Mỗi một lớp trong mô hình này được thiết kế để có thể thực hiện một nhiệm vụ cụ thể và làm thuận tiện cho việc truyền thông giữa lớp trên và lớp dưới nó.

<a href="http://imgur.com/qOexPtk"><img src="http://i.imgur.com/qOexPtk.jpg?1" title="source: imgur.com" /></a>

|   | Mô Hình OSI 7 Tầng |      Ý nghĩa các tầng           | Data Unit |
|---|--------------------|---------------------------------|-----------|
| 7 | Application | Các quá trình giao tiếp với các ứng dụng | Data |
| 6 | Presentation | Biểu diễn dữ liệu | Data |
| 5 | Session | Thông tin liên host | Data |
| 4 | Transport | Kết thúc từ đầu cuối đến đầu cuối | Segments |
| 3 | Network | Định địa chỉ và chọn đường dẫn tốt nhất | Packets |
| 2 | Data Link | Truy xuất môi trường truyền | Frames |
| 1 | Physical | Truyền dẫn nhị phân | Bits |
Mô hình OSI phân chia chức năng của một giao thức ra thành một chuỗi các tầng cấp. Mỗi một tầng cấp có một đặc tính là nó chỉ sử dụng chức năng của tầng dưới nó, đồng thời chỉ cho phép tầng trên sử dụng các chức năng của mình. Một hệ thống cài đặt các giao thức bao gồm một chuỗi các tầng nói trên được gọi là "chồng giao thức" (protocol stack). Chồng giao thức có thể được cài đặt trên phần cứng, hoặc phần mềm, hoặc là tổ hợp của cả hai. Thông thường thì chỉ có những tầng thấp hơn là được cài đặt trong phần cứng, còn những tầng khác được cài đặt trong phần mềm.
##Các tầng trong mô hình OSI
###Tầng1: tầng vật lí ( Physical Layer ) 
**Tầng vật lý** định nghĩa tất cả các đặc tả về điện và vật lý cho các thiết bị. Trong đó bao gồm bố trí của các chân cắm (pin), các hiệu điện thế, và các đặc tả về cáp nối (cable). Các thiết bị tầng vật lý bao gồm Hub, bộ lặp (repeater), thiết bị tiếp hợp mạng (network adapter) và thiết bị tiếp hợp kênh máy chủ (Host Bus Adapter)- (HBA dùng trong mạng lưu trữ (Storage Area Network)). Chức năng và dịch vụ căn bản được thực hiện bởi tầng vật lý bao gồm:

- Thiết lập hoặc ngắt mạch kết nối điện (electrical connection) với một môi trường truyền dẫn phương tiện truyền thông (transmission medium).
- Tham gia vào quy trình mà trong đó các tài nguyên truyền thông được chia sẻ hiệu quả giữa nhiều người dùng. Chẳng hạn giải quyết tranh chấp tài nguyên (contention) và điều khiển lưu lượng.

- Điều chế (modulation), hoặc biến đổi giữa biểu diễn dữ liệu số (digital data) của các thiết bị người dùng và các tín hiệu tương ứng được truyền qua kênh truyền thông (communication channel).
