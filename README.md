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


![alt text](https://static.sitecuatui.com/wp-content/uploads/2015/10/dung-luong-o-cung-virtualbox.jpg?raw=true)

Nhấn Create để kết thúc quá trình tạo máy ảo Ubuntu trên VirtualBox.

Bạn có thể cài Ubuntu trên UEFI trong VirtualBox bằng cách vào Settings > System, sau đó bật tùy chọn Enable EFI (special OSes only) và nhấn OK để lưu lại.

### Cài đặt Ubuntu trên VirtualBox
Không giống như việc cài đặt Ubuntu bằng USB hay DVD, bạn có thể boot vào Ubuntu trên VirtualBox trực tiếp từ file iso mà không cần phải burn ra đâu cả.

Để bắt đầu, chọn tên máy ảo trong cửa sổ Oracle VM VirtualBox Manager và nhấn Start để khởi động máy ảo. Nếu như đây là lần đầu tiên bạn khởi động máy ảo Ubuntu, bạn sẽ nhìn thấy cửa sổ Select start-up disk. Tại đây bạn cần phải chọn file iso Ubuntu mà bạn vừa download ở trên bằng cách nhấn vào mũi tên ở bên phải.

![alt text](https://static.sitecuatui.com/wp-content/uploads/2015/10/select-start-up-disk.jpg?raw=true)

![alt text](https://static.sitecuatui.com/wp-content/uploads/2015/10/chon-file-iso-cho-virtualbox.jpg?raw=true)

Nhấn Start để boot vào Ubuntu bằng file iso đã chọn.

Nếu đây không phải là lần đầu tiên bạn khởi động máy ảo, có thể bạn sẽ gặp lỗi “FATAL: No bootable medium found! System halted.” Đây là lỗi không tìm được thiết bị nào để boot. Nhấn chuột phải vào biểu tượng CD/DVD dưới màn hình đen và chọn Choose disk image…, sau đó chọn file iso mà bạn đã download ở trên.

![alt text](https://static.sitecuatui.com/wp-content/uploads/2015/10/FATAL-No-bootable-medium-found.-System-halted..jpg?raw=true)

Sau khi boot vào máy chủ với file iso hoặc đĩa cài đặt Ubuntu Server, chúng ta thực hiện các bước cài đặt như sau:

### Lựa chọn ngôn ngữ

=> Chọn ngôn ngữ mặc định là “English” hoặc ngôn ngữ nào mà bạn mong muốn.

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-1.png?raw=true)

### Kiểu bàn phím

=> Chọn mặc định là English US

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-2.png?raw=true)

### Ubuntu Platform

Chọn “Install Ubuntu”

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-3.png?raw=true)

### Cấu hình Network

Để mặc định => Bấm [ Done ] để tiếp tục

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-4.png?raw=true)

### Cấu hình Proxy Server

=> Bỏ trống

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-5.png?raw=true)

### Cấu hình Ubuntu Mirror

Đây là dường dẫn tên miền đặt máy chủ có chứa các package của Ubuntu, phục vụ cho việc cài đặt, nâng cấp Ubuntu.

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-6.png?raw=true)

Vì mình ở Việt Nam nên muốn cài đặt và nâng cấp các package của Ubuntu được nhanh chóng nên mình thay đổi bằng địa chỉ Server đặt ở VN là http://opensource.xtdv.net/ubuntu

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-7.png?raw=true)

### Phân vùng ổ địa và hệ thống tệp tin

Chọn “Use An Entire Disk” nếu bạn là người mới bắt đầu, còn nếu bạn là 1 Linux System Professional  thì có thể lựa chọn tùy chọn “Manual” để phân vùng ổ đĩa.

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-8.png?raw=true)

### Chọn ổ đĩa để cài đặt

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-9.png?raw=true)

Thông tin phân vùng ổ đĩa => Chọn [ Done ] để tiếp tục

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-10.png?raw=true)

Một cảnh báo sẽ hiển thị, xác nhận ổ đĩa sẽ được format => Chọn [ Continue ] để tiếp tục

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-11.png?raw=true)

### Cấu hình thông tin đăng nhập vào hệ thống bao gồm:

- **Your name**: Tên của bạn
- **Your server’s name**: Tên Server
- **Pick a username**: Tên đăng nhập
- **Choose a password**: Mật khẩu
- **Confirm your password**: Nhập lại mật khẩu của bạn

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-12.png?raw=true)

### Cài đặt OpenSSH để có thể đăng nhập vào Server bằng giao thức SSH

Tích vào ô “Install OpenSSH server” bằng cách sử dụng phím [ Space ]

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-13.png?raw=true)

Một số loại phần mềm có sẵn để bạn có thể cài đặt, ở đây mình ko có nhu cầu cài đặt cài nào trong đây. Các bạn có thể chọn nếu muốn cài, sử dụng phím [ Space ] để lựa chọn.

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-14.png?raw=true)

### Quá trình cài đặt sẽ được bắt đầu.

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-15.png?raw=true)

Sau khi cài đặt xong => Chọn [ Reboot Now ] để reboot lại máy chủ

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-16.png?raw=true)

Gỡ bỏ đĩa cài đặt => bấm phím [ Enter ] để boot vào HDH

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-17.png?raw=true)

Kết quả sau khi reboot, chúng ta thực hiện login vào Server bằng tài khoản đã tạo ở các bước trên

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-18.png?raw=true)

Sau khi đăng nhập thành công vào Server

![alt text](https://vinasupport.com/uploads/bai-viet/Ubuntu/Server-1804/Huong-Dan-Cai-Dat-Ubuntu-Server-18-04-Step-19.png?raw=true)

Như vậy quá trình cài đặt Ubuntu Server 18.04 LTS đã kết thúc. Nếu trong quá trình cài đặt theo hướng dẫn bên trên mà gặp khó khăn gì thì vui lòng để lại comment bên dưới. Mình rất vui lòng được support các bạn.

### Cấu hình địa chỉ ip tĩnh cho Ubuntu server 18.04

File cấu hình IP cho các card mạng của Ubuntu Server nằm tại /etc/netplan/50-cloud-init.yaml
Nội dung ban đầu sẽ như sau:

```sh
# This file is generated from information provided by
# the datasource.  Changes to it will not persist across an instance.
# To disable cloud-init's network configuration capabilities, write a file
# /etc/cloud/cloud.cfg.d/99-disable-network-config.cfg with the following:
# network: {config: disabled}
 network:
     ethernets:
        eth0:
           dhcp4: true
```

Ví dụ ta muốn cấu hình địa chỉ IP tĩnh, ta sửa file cấu hình như sau:

```sh
# This file is generated from information provided by
# the datasource.  Changes to it will not persist across an instance.
# To disable cloud-init's network configuration capabilities, write a file
# /etc/cloud/cloud.cfg.d/99-disable-network-config.cfg with the following:
# network: {config: disabled}
network:
    ethernets:
        eth0:
            dhcp4: false
            addresses:
              - 10.6.169.252/24
            gateway4: 10.6.169.3
            nameservers:
                addresses: [8.8.8.8, 1.1.1.1]
```

Giải thích file cấu hình:

Phần cấu hình IP tĩnh cho interface eth0:

```sh
 eth0:
            dhcp4: false
            addresses:
              - 10.6.169.252/24
            gateway4: 10.6.169.3
            nameservers:
                addresses: [8.8.8.8, 1.1.1.1]
```

- **Dòng 1**: Cấu hình trên interface eth0
- **Dòng 2**: Vì cấu hình ip tĩnh nên set dhcp4 là false
- **Dòng 3,4**: Addresses: nhập địa chỉ ip và subnetmark
- **Dòng 5**: Nhập địa chỉ gateway của mạng
- **Dòng 6,7**: Cấu hình DNS dùng để phân giải internet

Sau khi sửa file cài đặt ta lưu lại thiết lập và sử dụng câu lệnh sau để khởi động lại card mạng ta vừa thiết lập:

Với ví dụ trên ta sẽ chạy lệnh

```sh
sudo netplan apply
ip addr show dev eth0
```

