#Mô hình OSI
Mô hình mạng mà Windows và hầu hết các hệ điều hành mạng khác sử dụng được gọi là **mô hình OSI**. Thuật ngữ **OSI** được viết tắt bởi cụm từ tiếng Anh *Open System Interconnection Basic Reference*. Mô hình này gồm có bảy lớp khác nhau. Mỗi một lớp trong mô hình này được thiết kế để có thể thực hiện một nhiệm vụ cụ thể và làm thuận tiện cho việc truyền thông giữa lớp trên và lớp dưới nó.

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

###Tầng1: *Tầng vật lí (Physical Player)*
**Tầng vật lý** định nghĩa tất cả các đặc tả về điện và vật lý cho các thiết bị. Trong đó bao gồm bố trí của các chân cắm (pin), các hiệu điện thế, và các đặc tả về cáp nối (cable). Các thiết bị tầng vật lý bao gồm Hub, bộ lặp (repeater), thiết bị tiếp hợp mạng (network adapter) và thiết bị tiếp hợp kênh máy chủ (Host Bus Adapter)- (HBA dùng trong mạng lưu trữ (Storage Area Network)). Chức năng và dịch vụ căn bản được thực hiện bởi tầng vật lý bao gồm:
- <ul>Thiết lập hoặc ngắt mạch kết nối điện (electrical connection) với một môi trường truyền dẫn phương tiện truyền thông (transmission medium).</ul>

- <ul>Tham gia vào quy trình mà trong đó các tài nguyên truyền thông được chia sẻ hiệu quả giữa nhiều người dùng. Chẳng hạn giải quyết tranh chấp tài nguyên (contention) và điều khiển lưu lượng.</ul>

- <ul>Điều chế (modulation), hoặc biến đổi giữa biểu diễn dữ liệu số (digital data) của các thiết bị người dùng và các tín hiệu tương ứng được truyền qua kênh truyền thông (communication channel).</ul>

###Tầng2: *Tầng liên kết dữ liệu (Data Link Layer)*
**Tầng liên kết dữ liệu** cung cấp các phương tiện có tính chức năng và quy trình để truyền dữ liệu giữa các thực thể mạng, phát hiện và có thể sửa chữa các lỗi trong tầng vật lý nếu có. Cách đánh địa chỉ mang tính vật lý, nghĩa là địa chỉ (địa chỉ MAC) được mã hóa cứng vào trong các thẻ mạng (network card) khi chúng được sản xuất. Hệ thống xác định địa chỉ này không có đẳng cấp (flat scheme). Chú ý: Ví dụ điển hình nhất là [Ethernet](https://vi.wikipedia.org/wiki/Ethernet). Những ví dụ khác về các giao thức liên kết dữ liệu (data link protocol) là các giao thức HDLC; ADCCP dành cho các mạng điểm-tới-điểm hoặc mạng chuyển mạch gói (packet-switched networks) và giao thức Aloha cho các mạng cục bộ. Trong các mạng cục bộ theo tiêu chuẩn [IEEE 802](https://vi.wikipedia.org/wiki/IEEE_802), và một số mạng theo tiêu chuẩn khác, chẳng hạn FDDI, tầng liên kết dữ liệu có thể được chia ra thành 2 tầng con: tầng MAC (Media Access Control - Điều khiển Truy nhập Đường truyền) và tầng LLC (Logical Link Control - Điều khiển Liên kết Lôgic) theo tiêu chuẩn [IEEE 802.2](https://vi.wikipedia.org/w/index.php?title=IEEE_802.2&action=edit&redlink=1).

**Tầng liên kết dữ liệu** chính là nơi và các thiết bị chuyển mạch ([switches](https://vi.wikipedia.org/wiki/Switch)) hoạt động. Kết nối chỉ được cung cấp giữa các nút mạng được nối với nhau trong nội bộ mạng. Tuy nhiên, có lập luận khá hợp lý cho rằng thực ra các thiết bị này thuộc về tầng 2,5 chứ không hoàn toàn thuộc về tầng 2.
###Tầng 3: *Tầng mạng (Network Layer)*
**Tầng mạng** cung cấp các chức năng và qui trình cho việc truyền các chuỗi dữ liệu có độ dài đa dạng, từ một nguồn tới một đích, thông qua một hoặc nhiều mạng, trong khi vẫn duy trì chất lượng dịch vụ (quality of service) mà tầng giao vận yêu cầu. Tầng mạng thực hiện chức năng định tuyến,.Các thiết bị định tuyến ([router](https://vi.wikipedia.org/wiki/Router)) hoạt động tại tầng này — gửi dữ liệu ra khắp mạng mở rộng, làm cho liên mạng trở nên khả thi (còn có thiết bị chuyển mạch (switch) tầng 3, còn gọi là chuyển mạch IP). Đây là một hệ thống định vị địa chỉ lôgic (logical addressing scheme) – các giá trị được chọn bởi kỹ sư mạng. Hệ thống này có cấu trúc phả hệ. Ví dụ điển hình của giao thức tầng 3 là [giao thức IP](https://vi.wikipedia.org/wiki/IP).
###Tầng 4: *Tầng giao vận (Transport Layer)*
**Tầng giao vận** cung cấp dịch vụ chuyên dụng chuyển dữ liệu giữa các người dùng tại đầu cuối, nhờ đó các tầng trên không phải quan tâm đến việc cung cấp dịch vụ truyền dữ liệu đáng tin cậy và hiệu quả. Tầng giao vận kiểm soát độ tin cậy của một kết nối được cho trước. Một số giao thức có định hướng trạng thái và kết nối (state and connection orientated). Có nghĩa là tầng giao vận có thể theo dõi các gói tin và truyền lại các gói bị thất bại. Một ví dụ điển hình của giao thức tầng 4 là TCP. Tầng này là nơi các thông điệp được chuyển sang thành các gói tin [TCP hoặc UDP](https://vi.wikipedia.org/wiki/UDP). Ở tầng 4 địa chỉ được đánh là address ports, thông qua address ports để phân biệt được ứng dụng trao đổi.
###Tầng 5: *Tầng phiên (Session layer)*
**Tầng phiên* kiểm soát các (phiên) hội thoại giữa các máy tính. Tầng này thiết lập, quản lý và kết thúc các kết nối giữa trình ứng dụng địa phương và trình ứng dụng ở xa. Tầng này còn hỗ trợ hoạt động song công (duplex) hoặc bán song công (half-duplex) hoặc đơn công (Single) và thiết lập các qui trình đánh dấu điểm hoàn thành (checkpointing) - giúp việc phục hồi truyền thông nhanh hơn khi có lỗi xảy ra, vì điểm đã hoàn thành đã được đánh dấu - trì hoãn (adjournment), kết thúc (termination) và khởi động lại (restart). Mô hình OSI uỷ nhiệm cho tầng này trách nhiệm "ngắt mạch nhẹ nhàng" (graceful close) các phiên giao dịch (một tính chất của giao thức kiểm soát giao vận TCP) và trách nhiệm kiểm tra và phục hồi phiên, đây là phần thường không được dùng đến trong bộ giao thức TCP/IP.
###Tầng 6: *Tầng trình diễn (Presentation layer)*
**Lớp trình diễn** hoạt động như tầng dữ liệu trên mạng. lớp này trên máy tính truyền dữ liệu làm nhiệm vụ dịch dữ liệu được gửi từ tầng Application sang dạng Fomat chung. Và tại máy tính nhận, lớp này lại chuyển từ Fomat chung sang định dạng của tầng Application. Lớp thể hiện thực hiện các chức năng sau: - Dịch các mã kí tự từ ASCII sang EBCDIC. - Chuyển đổi dữ liệu, ví dụ từ số interger sang số dấu phảy động. - Nén dữ liệu để giảm lượng dữ liệu truyền trên mạng. - Mã hoá và giải mã dữ liệu để đảm bảo sự bảo mật trên mạng.
###Tầng 7: *Tầng ứng dụng (Application layer)*
**Tầng ứng dụng** là tầng gần với người sử dụng nhất. Nó cung cấp phương tiện cho người dùng truy nhập các thông tin và dữ liệu trên mạng thông qua chương trình ứng dụng. Tầng này là giao diện chính để người dùng tương tác với chương trình ứng dụng, và qua đó với mạng. Một số ví dụ về các ứng dụng trong tầng này bao gồm [Telnet](https://vi.wikipedia.org/wiki/Telnet), Giao thức truyền tập tin [FTP](https://vi.wikipedia.org/wiki/FTP) và Giao thức truyền thư điện tử [SMTP](https://vi.wikipedia.org/wiki/SMTP), [HTTP](https://vi.wikipedia.org/wiki/Hypertext_Transfer_Protocol), [X.400 Mail](https://vi.wikipedia.org/w/index.php?title=X.400_Mail&action=edit&redlink=1) remote
##Cơ chế làm việc
Mỗi lớp chỉ nói chuyện được với lớp trên và lớp dưới kế với nó . Khi máy tính của bạn đang truyền dữ liệu , luồng thông tin là xuất phát từ chương trình tới mạng ( có nghĩa là đường dữ liệu đi từ đỉnh tới đáy ) , do đó chương trình nói chuyện với lớp thứ bảy , tiếp theo truyền tới lớp thứ sáu và cứ như vậy . Khi máy tính của chúng ta đang nhận dữ liệu , thì luồng thông tin sẽ từ mạng tới chương trình ( có nghĩa là đường dữ liệu sẽ từ đáy đi tới đỉnh ) , do đó mạng sẽ nói chuyện với lớp thứ nhất sau đó truyền tới lớp thứ hai và cứ như vậy .
Khi dữ liệu được truyền , mỗi lớp thêm một vài thông tin điều khiển tới dữ liệu mà nó được nhận từ lớp trên , và khi dữ liệu được nhận thì quá trình xảy ra ngược lại ; mỗi lớp sẽ gỡ những thông tin điều khiển từ dữ liệu nhận được từ lớp bên dưới .
Do vậy khi dữ liệu được gửi tới mạng , lớp thứ bảy nhận dữ liệu do chương trình gửi tới và thêm những thông tin điều khiển của riêng nó và gửi gói dữ liệu mới này tới lớp thứ sáu . Lớp thứ sáu sẽ thêm dữ liệu điều khiển riêng của nó vào gói dữ liệu đã nhận được ở lớp thứ bảy và gửi gói dữ liệu sau khi thêm dữ liệu điều khiển tới lớp thứ năm . Như vậy lớp thứ năm nhận được dữ liệu lúc này là dữ liệu ban đầu đã được thêm những thông tin điều khiển dữ liệu của lớp thứ bảy và lớp thứ sáu  . Và cứ như vậy . Khi nhận dữ liệu quá trình diễn ra ngược lại , mỗi lớp sẽ gỡ dữ liệu điều khiển của nó khỏi dữ liệu nhận được .
Mỗi lớp chỉ hiểu dữ liệu điều khiển mà nó nhận trách nhiệm . Khi lớp nhận dữ liệu từ lớp trên nó không hiểu dữ liệu điều khiển được thêm vào từ lớp trên , do đó nó chỉ hiểu dữ liệu mà nó nhận được chỉ là một gói dữ liệu đơn lẻ .
Trong hình dưới đây mô tả cho chúng ta thấy thấy khi máy tính gửi dữ liệu đi như thế nào tới mạng . Mỗi số thêm vào tới dữ liệu ban đầu đại diện cho dữ liệu điều khiển được thêm vào từ lớp đó . Mỗi lớp xử lí gói mà nó nhận được từ lớp trên như là một gói dữ liệu đơn lẻ mà nó không cần phân biệt dữ liệu trong đó gồm những gì.

<a href="http://imgur.com/efXr3uZ"><img src="http://i.imgur.com/efXr3uZ.gif" title="source: imgur.com" /></a>

Chúng ta cũng có thể nói rằng mỗi lớp của máy tính truyền sẽ nói chuyện trực tiếp với cùng lớp của máy tính nhận . Ví dụ : lớp thứ tư của máy nhận dữ liệu sẽ nói chuyện trực tiếp tới lớp thứ tư của máy truyền dữ liệu  . Chúng có có thể nói được như vậy bởi vì dữ liệu điều khiển được thêm vào từ mỗi lớp thì chỉ có cùng lớp của máy nhận mới có thể hiểu được.

#Bộ giao thức TCP/IP
**Bộ giao thức TCP/IP**, (*tiếng Anh: Internet protocol suite hoặc IP suite hoặc TCP/IP protocol suite - bộ giao thức liên mạng*), là một bộ các giao thức truyền thông cài đặt chồng giao thức mà Internet và hầu hết các mạng máy tính thương mại đang chạy trên đó. Bộ giao thức này được đặt tên theo hai giao thức chính của nó là *TCP* (Giao thức Điều khiển Giao vận) và *IP* (Giao thức Liên mạng). Chúng cũng là hai giao thức đầu tiên được định nghĩa.

Như nhiều bộ giao thức khác, *bộ giao thức TCP/IP* có thể được coi là một tập hợp các tầng, mỗi tầng giải quyết một tập các vấn đề có liên quan đến việc truyền dữ liệu, và cung cấp cho các giao thức tầng cấp trên một dịch vụ được định nghĩa rõ ràng dựa trên việc sử dụng các dịch vụ của các tầng thấp hơn. Về mặt lôgic, các tầng trên gần với người dùng hơn và làm việc với dữ liệu trừu tượng hơn, chúng dựa vào các giao thức tầng cấp dưới để biến đổi dữ liệu thành các dạng mà cuối cùng có thể được truyền đi một cách vật lý.

##Các tầng trong Bộ giao thức TCP/ IP

###*Tầng liên kết*
**Tầng liên kết** - phương pháp được sử dụng để chuyển các gói tin từ tầng mạng tới các máy chủ (host) khác nhau - không hẳn là một phần của bộ giao thức TCP/IP, vì giao thức IP có thể chạy trên nhiều tầng liên kết khác nhau. Các quá trình truyền các gói tin trên một liên kết cho trước và nhận các gói tin từ một liên kết cho trước có thể được điều khiển cả trong phần mềm điều vận thiết bị (device driver) dành cho [modem](https://vi.wikipedia.org/wiki/Modem), cũng như trong phần sụn (firmware) hay các chipset chuyên dụng. Những thứ đó sẽ thực hiện các chức năng liên kết dữ liệu chẳng hạn như bổ sung một tín đầu (packet header) để chuẩn bị cho việc truyền gói tin đó, rồi thực sự truyền frame dữ liệu qua một môi trường vật lý.

Đối với truy nhập Internet qua [modem](https://vi.wikipedia.org/wiki/Modem) quay số, các gói IP thường được truyền bằng cách sử dụng giao thức PPP. Đối với truy nhập Internet băng thông rộng (broadband) như [ADSL](https://vi.wikipedia.org/wiki/ADSL) hay modem cáp, [giao thức PPPoE](https://vi.wikipedia.org/w/index.php?title=PPPoE&action=edit&redlink=1) thường được sử dụng. Mạng dây cục bộ (local wired network') thường sử dụng [Ethernet](https://vi.wikipedia.org/wiki/Ethernet), còn mạng không dây cục bộ thường dùng chuẩn [IEEE 802.11](https://vi.wikipedia.org/wiki/IEEE_802.11). Đối với các mạng diện rộng [WAN]ư(https://vi.wikipedia.org/wiki/WAN) (wide-area network), các giao thức thường được sử dụng là [PPP](https://vi.wikipedia.org/wiki/PPP_(giao_th%E1%BB%A9c)) đối với các đường [T-carrier](https://vi.wikipedia.org/w/index.php?title=T-carrier&action=edit&redlink=1) hoặc [E-carrier](https://vi.wikipedia.org/w/index.php?title=E-carrier&action=edit&redlink=1), [Frame relay](https://vi.wikipedia.org/w/index.php?title=Frame_relay&action=edit&redlink=1), [ATM](https://vi.wikipedia.org/wiki/ATM_(giao_th%E1%BB%A9c)) (Asynchronous Transfer Mode), hoặc giao thức [packet over SONET/SDH](https://vi.wikipedia.org/w/index.php?title=Packet_over_SONET/SDH&action=edit&redlink=1) (POS].

**Tầng liên kết** còn có thể là tầng nơi các gói tin được chặn (intercepted) để gửi qua một mạng riêng ảo (virtual private network). Khi xong việc, dữ liệu tầng liên kết được coi là dữ liệu của ứng dụng và tiếp tục đi xuống theo chồng giao thức TCP/IP để được thực sự truyền đi. Tại đầu nhận, dữ liệu đi lên theo chồng TCP/IP hai lần (một lần cho mạng riêng ảo và lần thứ hai cho việc định tuyến).

Tầng liên kết còn có thể được xem là bao gồm cả tầng vật lý - tầng là kết hợp của các thành phần mạng vật lý thực sự (hub, các bộ lặp (repeater), cáp mạng, cáp quang, cáp đồng trục (coaxial cable), cạc mạng, cạc HBA (Host Bus Adapter) và các thiết bị nối mạng có liên quan: RJ-45, BNC, etc), và các đặc tả mức thấp về các tín hiệu (mức hiệu điện thế, tần số, v.v..).
###*Tầng mạng*
**Tầng mạng** giải quyết các vấn đề dẫn các gói tin qua một mạng đơn. Một số ví dụ về các giao thức như vậy là [X.25](https://vi.wikipedia.org/w/index.php?title=X.25&action=edit&redlink=1), và giao thức [Host/IMP](https://vi.wikipedia.org/w/index.php?title=Giao_th%E1%BB%A9c_Host/IMP&action=edit&redlink=1) của mạng [ARPANET](https://vi.wikipedia.org/wiki/ARPANET).

Với sự xuất hiện của khái niệm [liên mạng](https://vi.wikipedia.org/wiki/Li%C3%AAn_m%E1%BA%A1ng), các chức năng mới đã được bổ sung cho tầng này, đó là chức năng dẫn đường cho dữ liệu từ mạng nguồn đến mạng đích. Nhiệm vụ này thường đòi hỏi việc định tuyến cho gói tin quan một mạng lưới của các mạng máy tính, đó là liên mạng.

Trong bộ giao thức liên mạng, giao thức [IP](https://vi.wikipedia.org/wiki/IP) thực hiện nhiệm vụ cơ bản dẫn đường dữ liệu từ nguồn tới đích. IP có thể chuyển dữ liệu theo yêu cầu của nhiều giao thức tầng trên khác nhau; mỗi giao thức trong đó được định danh bởi một số hiệu giao thức duy nhất: giao thức ICMP (Internet Control Message Protocol) là giao thức 1 và giao thức IGMP (Internet Group Management Protocol) là giao thức 2.
###*Tầng giao vận*
Trách nhiệm của **tầng giao vận** là kết hợp các khả năng truyền thông điệp trực tiếp (end-to-end) không phụ thuộc vào mạng bên dưới, kèm theo kiểm soát lỗi (error control), phân mảnh (fragmentation) và [điều khiển lưu lượng](https://vi.wikipedia.org/wiki/%C4%90i%E1%BB%81u_khi%E1%BB%83n_l%C6%B0u_l%C6%B0%E1%BB%A3ng). Việc truyền thông điệp trực tiếp hay kết nối các ứng dụng tại tầng giao vận có thể được phân loại như sau:

1. định hướng kết nối (connection-oriented), ví dụ TCP
2. phi kết nối (connectionless), ví dụ UDP
Tầng giao vận có thể được xem như một cơ chế vận chuyển thông thường, nghĩa là trách nhiệm của một phương tiện vận tải là đảm bảo rằng hàng hóa/hành khách của nó đến đích an toàn và đầy đủ.

Tầng giao vận cung cấp dịch vụ kết nối các ứng dụng với nhau thông qua việc sử dụng các cổng TCP và UDP. Do IP chỉ cung cấp dịch vụ phát chuyển nỗ lực tối đa (best effort delivery), tầng giao vận là tầng đâu tiên giải quyết vấn đề độ tin cậy.

Ví dụ, TCP là một giao thức định hướng kết nối. Nó giải quyết nhiều vấn đề độ tin cậy để cung cấp một dòng byte đáng tin cậy (reliable byte stream):

- Dữ liệu đến đích đúng thứ tự
- Sửa lỗi dữ liệu ở mức độ tối thiểu
- Dữ liệu trùng lặp bị loại bỏ
- Các gói tin bị thất lại/loại bỏ được gửi lại
- Có kiểm soát tắc nghẽn giao thông dữ liệu

Tuy các giao thức định tuyến động (dynamic routing protocol) khớp về kỹ thuật với tầng giao vận trong bộ giao thức TCP/IP (do chúng chạy trên IP), nhưng chúng thường được xem là một phần của tầng mạng. Một ví dụ là giao thức OSPF (số hiệu giao thức IP là 89).

Giao thức mới hơn, [SCTP](https://vi.wikipedia.org/wiki/SCTP) (Stream Control Transmission Protocol|), cũng là một cơ chế giao vận định hướng kết nối "đáng tin cậy". Giao thức này định hướng dòng (stream-oriented), chứ không định hướng byte như TCP, và cung cấp nhiều dòng đa công (multiplexed) trên một kết nối. Nó còn hỗ trợ multi-homed, trong đó một đầu của kết nối có thể được đại diện bởi nhiều địa chỉ IP (đại diện cho nhiều giao diện vật lý), sao cho, nếu một giao diện vật lý thất bại thì kết nối vẫn không bị gián đoạn. Giao thức này ban đầu được phát triển dành cho các ứng dụng điện thoại (để vận chuyển SS7 trên giao thức IP), nhưng nó cũng có thể được sử dụng cho các ứng dụng khác.

UDP là một giao thức datagram phi kết nối. Cũng như IP, nó là một giao thức nỗ lực tối đa hay "không đáng tin cậy". Vấn đề duy nhất về độ tin cậy mà nó giải quyết là sửa lỗi dữ liệu (dù chỉ bằng một thuật toán tổng kiểm yếu). UDP thường được dùng cho các ứng dụng như các phương tiện truyền thông theo dòng (streaming media) chứa âm thanh và hình ảnh, v.v.., trong đó, vấn đề gửi đến đúng giờ có vai trò quan trọng hơn độ tin cậy, hoặc cho các ứng dụng truy vấn/đáp ứng đơn giản như tra cứu tên miền, trong đó, phụ phí của việc thiết lập một kết nối đáng tin cậy lớn một cách không cân xứng.

Giao thức DCCP hiện đang được phát triển bởi IETF (Internet Engineering Task Force). Nó cung cấp nội dung điều khiển lưu lượng của TCP, trong khi đối với người dùng, nó giữ bề ngoài như mô hình dịch vụ datagram của UDP.

Cả TCP và UDP được dùng cho một số ứng dụng bậc cao (high-level). Các ứng dụng tại các địa chỉ mạng cho trước được phân biệt bởi cổng TCP hay UDP của nó. Theo quy ước, các cổng "nổi tiếng" được liên kết với một số ứng dụng cụ thể. (Xem Danh sách cổng TCP và UDP.)

RTP (Real-time Transport Protocol - giao thức giao vận thời gian thực) là một giao thức datagram được thiết kế cho dữ liệu thời gian thực (real-time), chẳng hạn hình và tiếng được truyền theo dòng ('streaming audio and video'). RTP là một giao thức tầng phiên sử dụng định dạng gói tin UDP làm căn bản. Tuy nhiên, nó được đặt vào tầng giao vận của chồng giao thức TCP/IP.

Một số giao thức truyền bởi IP, chẳng hạn ICMP (dùng để gửi thông tin chẩn đoán về truyền dữ liệu bằng IP) và IGMP (dùng để quản lý dữ liệu đa truyền (multicast)), được đặt lên trên IP nhưng thực hiện các chức năng của tầng liên mạng, điều này minh họa một sự bất tương thích giữa liên mạng và chồng TCP/IP và mô hình OSI. Tất cả các giao thức định tuyến, chẳng hạn giao thức BGP (Border Gateway Protocol), giao thức OSPF, và giao thức RIP (Routing information protocol|), đều thực sự là một phần của tầng mạng, mặc dù chúng có thể có vẻ thuộc về phần trên của chồng giao thức.
###*Tầng ứng dụng*
**Tầng ứng dụng** là nơi các chương trình mạng thường dùng làm việc nhất nhằm liên lạc giữa các nút trong một mạng.

Giao tiếp xảy ra trong tầng này là tùy theo các ứng dụng cụ thể và dữ liệu được truyền từ chương trình, trong định dạng được sử dụng nội bộ bởi ứng dụng này, và được đóng gói theo một giao thức tầng giao vận.

Do chồng TCP/IP không có tầng nào nằm giữa ứng dụng và các tầng giao vận, tầng ứng dụng trong bộ TCP/IP phải bao gồm các giao thức hoạt động như các giao thức tại tầng trình diễn và tầng phiên của mô hình OSI. Việc này thường được thực hiện qua các thư viện lập trình.

Dữ liệu thực để gửi qua mạng được truyền cho tầng ứng dụng, nơi nó được đóng gói theo giao thức tầng ứng dụng. Từ đó, dữ liệu được truyền xuống giao thức tầng thấp tại tầng giao vận.

Hai giao thức tầng thấp thông dụng nhất là TCP và UDP. Mỗi ứng dụng sử dụng dịch vụ của một trong hai giao thức trên đều cần có cổng. Hầu hết các ứng dụng thông dụng có các cổng đặc biệt được cấp sẵn cho các chương trình phục vụ (server)(HTTP - Giao thức truyền siêu văn bản dùng cổng 80; FTP - Giao thức truyền tệp dùng cổng 21, v.v..) trong khi các trình khách (client) sử dụng các cổng tạm thời (ephemeral port).

Các thiết bị định tuyến và thiết bị chuyển mạch không sử dụng tầng này nhưng các ứng dụng điều chỉnh thông lượng (bandwidth throttling) thì có dùng.
####Một số giao thức
#####FTP (File Transfer Protocol):
- Là dịch vụ tạo cầu nối tin cậy.
- Sử dụng giao thức TCP để truyền các tập tin.
- Hỗ trợ truyền file nhị phân.

#####TFPT(Trivial File Transfer Protocol):
- Khác với FTP là một dịch vụ không tạo cầu nối sử dụng giao thức UDP.
- DÙng trên router để truyền các file cấu hình.

#####SMTP (Simple Mail Transfer Protocol):
<ul>SMTP quản lý hoạt động truyền e-mail qua mạng máy tính.</ul>
#####Telnet (Terminal emulation):
<ul>Cung cấp khả năng truy cập từ xa vào một thiết bị đầu cuối khác. Cho phép người khác đăng nhập và thực thi các lệnh từ xa.</ul>
#####SNMP (Simple Network Management Protocol):
<ul>Là một giao thức cung cấp một phương pháp để giám sát và điều khiển các thiết bị mạng và để quản lý các cấu hình, thu thập thống kê, hiệu suất và bảo mật.</ul>
