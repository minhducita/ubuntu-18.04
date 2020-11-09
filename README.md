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
