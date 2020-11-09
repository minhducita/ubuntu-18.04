# Hướng dẫn cài đặt Ubuntu Server 18.04 LTS
Như các bạn đã biết Ubuntu là hệ điều hành mã nguồn mở Linux phổ biến và nối tiếng, phiên bản Ubuntu Server 18.04 LTS là phiên bản mới nhất (Cho tới thời điểm này) dành cho các hệ thống máy chủ. Bài viết nãy sẽ hướng dẫn các bạn cài đặt Ubuntu Server từng bước bằng hình ảnh minh họa.
### Giới thiệu về Ubuntu Server 18.04 LTS
Ubuntu Server là một phiên bản biến thể của Ubuntu, được điều chỉnh phục vụ cho các máy chủ và dịch vụ. Nó không chỉ có khả năng chạy 1 máy chủ tệp đơn lẻ mà nó còn hoạt động trong một hệ thống máy chủ đám mây. Không giống như cài đặt Ubuntu Desktop, Ubuntu Server không có chương trình cài đặt đồ họa.

- **Nhà phát triển**: Canonical Ltd. / Quỹ Ubuntu
- **Loại hệ điều hành**: Linux/Unix
- **Kiểu mã nguồn**: Phần mềm tự do
- **Phát hành lần đầu**: 20 tháng 10, 2004
- **Quản lý gói**: dpkg
- **Nền tảng hỗ trợ**: IA-32, x86-64, lpia, SPARC, PowerPC, ARM, IA-64
- **Giao diện mặc định**: Unity trên nền GNOME 3
- **Giấy phép**: GNU GPL
- **Website**: www.ubuntu.com
### Các bước chuẩn bị
1. File iso của Ubuntu Server 18.04. Link download tại đây: http://releases.ubuntu.com/18.04/
2. Máy ảo VirtualBox, VMWare hoặc có thể ghi file iso ra đĩa và cài trên máy tính thật.

### Tạo máy ảo Ubuntu trên VirtualBox
VirtualBox hỗ trợ cực kỳ đầy đủ cho một máy ảo Ubuntu như tính năng copy paste, shared folder thông qua Guest Additions.

Đầu tiên là bạn cần phải tạo ra một máy ảo mới trên VirtualBox. Mở VirtualBox, nhấn vào New để tạo máy ảo mới.

Trong cửa sổ Name and Operating system, đặt tên cho máy ảo ở mục Name (ví dụ Ubuntu 14.04), Type là Linux và Version là Ubuntu (32-bit). Nếu bạn muốn dùng phiên bản Ubuntu (64-bit) thì bạn phải bật Intel VT-x hoặc AMD-V, tất nhiên là máy tính cũng phải hỗ trợ hai cái này rồi.

![alt text](https://static.sitecuatui.com/wp-content/uploads/2015/10/tao-may-ao-virtualbox1.jpg?raw=true)

Nhấn Next để qua phần Memory size.

VirtualBox khuyến nghị thiết lập RAM tối thiểu cho Ubuntu phiên bản 64 bit là 768MB. Nhưng nếu máy tính bạn có nhiều RAM, bạn có thể chia sẽ cho máy ảo nhiều RAM một chút. Bởi vì càng nhiều RAM thì chạy càng nhanh, để dư RAM không dùng cũng phí.


![alt text](https://static.sitecuatui.com/wp-content/uploads/2015/10/memory-size-virtualbox.jpg?raw=true)

Nhấn Next. Trong phần Hard disk, chọn Create a virtual hard disk now và nhấn Create để tạo ổ đĩa ảo mới cho máy ảo Ubuntu.

### Hard disk file type
Chọn VDI theo mặc định là tốt nhất. VDI là định dạng ổ đĩa ảo của VirtualBox, VMDK là định dạng ổ đĩa ảo của VMware và nó tương thích với hầu hết các nền tảng ảo hóa. Bạn có thể chọn định dạng VMDK nếu như sau này bạn muốn sử dụng ổ đĩa ảo này cho các phần mềm ảo hóa khác như VMware Workstation. Tuy nhiên, bạn vẫn có thể chuyển định dạng VDI sang VMDK bất cứ lúc nào. Nhấn Next.

### Storage on physical hard disk
Khuyến nghị chọn Dynamically allocated thay vị Fixed size. Nếu bạn chọn Fixed size thì dung lượng của file ổ đĩa ảo được tạo ra sẽ cố định trên ổ cứng của bạn, tuy nhiên định dạng này sẽ nhanh hơn so với Dynamically allocated. Ví dụ bạn tạo ra ổ đĩa ảo Fixed size 20Gb thì ổ cứng của bạn sẽ mất 20Gb mặc dù máy ảo của bạn có sử dụng hết số đó hay không. Nhấn Next.

### File location and size
Bạn cần thiết lập dung lượng ổ đĩa ảo phù hợp cho máy ảo của bạn. Khuyến nghị cho máy ảo Ubuntu là 8Gb, tuy nhiên mình sẽ cho nó lên 12Gb cũng tốt. Nếu như bạn sử dụng Dynamically allocated thì phần này thiết lập dung lượng cao lên một chút cũng không sao cả.
