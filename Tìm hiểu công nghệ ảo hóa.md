# Tìm hiểu về công nghệ ảo hóa #

## 1. Ảo hóa là gì ##

- Ảo hóa là công nghệ mà máy chủ được tạo ra bằng cách phân chia máy chủ vật lý thành nhiều máy chủ nhỏ khác nhau. Các máy ảo tạo ra mang đầy đủ các tính chất, chức năng của một máy chủ riêng biệt, chạy dưới dạng chia sẻ tài nguyên từ máy chủ ban đầu. Có nhiều công nghệ ảo hóa tùy thuộc vào nhu cầu và điều kiện sử dụng của từng người có thể lựa chọn sử dụng công nghệ ảo hóa nào đó.

- Ý tưởng của công nghệ ảo hóa máy chủ là từ một máy vật lý đơn lẻ có thể tạo thành nhiều máy ảo độc lập. Mỗi một máy ảo đều có một thiết lập nguồn hệ thống riêng rẽ, hệ điều hành riêng và các ứng dụng riêng.

- Ưu điểm của việc sử dụng công nghệ ảo hóa:

+Linh hoạt trong việc thiết lập môi trường hoạt động đa nền tảng (tạo ra các máy sử dụng tài nguyên chia sẻ và độc lập hệ điều hành).

+Tiết kiệm chi phí so với việc triển khai server vật lý -> Giảm thiểu chi phí đầu tư ban đầu.

+Tận dụng tối đa tài nguyên, năng lực xử lý phần cứng -> Khai thác triệt để khả năng làm việc của một máy chủ vật lý.

+Có một môi trường quản lý tập trung các máy khi số lượng máy tăng lên cao.

+Hỗ trợ cho việc backup và restore

+Khả năng mở rộng, co dãn tốt.

## 2. Các công nghệ ảo hóa phổ biến ##

OpenVZ VPS

XEN VPS

VMWare VPS

KVM (Kernel-based Virtual Machine)

**Phân loại theo cách thức quản lý tài nguyên**

- Đối với cách phần chia công nghệ ảo hóa có 2 loại chính đó là:

+Dedicated virtualization (Bare-Metal Hypervisor): Hypervisor tương tác trực tiếp với phần cứng của máy chủ để quản lý, phân phối và cấp phát tài nguyên. Loại ảo hóa này bao gồm các giải pháp như Vmware ESXi, Microsoft Hyper-V, Xen Server, KVM.

+Hosted Architecture: Đây là loại ảo hóa Hypervisor giao tiếp với phần cứng thông qua hệ điều hành. Hypervisor lúc này được xem như một ứng dụng của hệ điều hành và các phương thức quản lý, cấp phát tài nguyên đều phải thông qua hệ điều hành. Loại ảo hóa này bao gồm các giải pháp như Vmware WorkStation, Oracle VirtualBox, Microsoft Virtual PC, …

![](https://i.imgur.com/sqjPESN.png)

--> Vì ở loại thứ 1, Hypervisor tương tác trực tiếp với phần cứng nên việc quản lý và phân phối tài nguyên được tối ưu và hiệu quả hơn so với loại 02, vì vậy khi triển khai trong thực tế, ảo hóa Loại 01 (Bare-Metal Hypervisor) được sử dụng, loại 02 chỉ sử dụng trong các trường hợp thử nghiệm, hoặc mục đích học tập. 

## 3. Đặc điểm của từng loại ảo hóa phổ biến ##

**3.1. OpenVZ**

- OpenVZ (Open Virtuozzo) là một hệ thống cấp công nghệ ảo hóa hoạt động dựa trên nhân Linux. OpenVZ cho phép một máy chủ vật lý để chạy nhiều trường hợp hệ điều hành riêng biệt.


- OpenVZ không thực sự ảo hóa, nó sử dụng chung 1 nhân Linux đã được sửa đổi và do đó chỉ có thể chạy duy nhất hệ điều hành Linux, như vậy tất cả các máy chủ ảo VPS cũng chỉ có thể chạy được Linux với chung 1 công nghệ và phiên bản Kenel. Tuy nhiên, do không có nhân riêng nên nó rất nhanh và hiệu quả, nhưng đó cũng chính là nhược điểm của nó khi tất cả các máy chủ phải sử dụng chung 1 nhân duy nhất.



- Đối với phiên bản cũ cấp phát bộ nhớ không được tách biệt, nghĩa là bộ nhớ được cấp phát cho 1 máy chủ VPS này lại có thể bị sử dụng bởi VPS khác trong trường hợp VPS kia yêu cầu.

- Đối với phiên bản mới của OpenVZ cho phép mỗi VPS có thể có hệ thống file system riêng của chính nó. Với việc “ảo hóa” thư mục thành VPS như vậy, có thể copy 1 VPS bằng cách copy thư mục, rồi thay đổi cấu hình phù hợp và start nó lên như 1 VPS mới.

**3.2. XEN**

XEN là công nghệ ảo hóa thực sự cho phép chạy cùng lúc nhiều máy chủ ảo VPS trên 1 máy chủ vật lý. Công nghệ ảo hóa XEN cho phép mỗi máy chủ ảo chạy nhân riêng của nó, do đó VPS có thể cài được cả Linux hay Windows Operating system, mỗi VPS có hệ thống File System riêng và hoạt động như 1 máy chủ độc lập.

Tài nguyên cung cấp cho máy chủ VPS XEN cũng độc lập, nghĩa là mỗi máy chủ XEN được cấp 1 lượng RAM, CPU và Disk riêng, nó đảm bảo rằng máy chủ VPS của bạn sẽ được cung cấp đủ tài nguyên như lúc đăng ký với nhà cung cấp dịch vụ.

-> Công nghệ XEN yêu cầu tài nguyên vật lý đầy đủ cho mỗi VPS, do đó nhà cung cấp dịch vụ cũng phải tăng cường tài nguyên vật lý trên máy chủ thật, dẫn đến máy chủ VPS sử dụng công nghệ XEN thường có giá đắt hơn công nghệ OpenVZ.

**3.3. VMWare**

Công nghệ ảo hóa Vmware hỗ trợ ảo hóa từ phần cứng, phần mềm, ứng dụng cho đến hệ điều hành và máy ảo. Một số ưu điểm nổi bật:



**3.4. KVM (Kernel-based Virtual Machine)**

KVM là công nghệ ảo hóa mới cho phép ảo hóa thực sự trên nền tảng phần cứng. Do đó máy chủ KVM giống như XEN được cung cấp riêng tài nguyên để sử dụng, tránh việc tranh chấp tài nguyên với máy chủ khác trên cùng node. Máy chủ gốc được cài đặt Linux, nhưng KVM hỗ trợ tạo máy chủ ảo có thể chạy cả Linux, Windows. Nó cũng hỗ trợ cả x86 và x86-64 system.



Link tham khảo

http://www.thanhnhantn.com/cong-nghe-ao-hoa-openvz-xen-vmware-la-gi/