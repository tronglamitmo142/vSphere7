# Ghi chép về VSphere

- Virtualization là công nghệ chuyển đổi các thành phần vật lý của compute thành 
những thành phần ảo hoá. 
- Các thành phần của 1 VM bao gồm:  
  - Guest OS 
  - Các thành phần ảo hoá:
    - CPU, memory: Hệ điều hành giả định có quyền sở hữu tất cả tài nguyên CPU trong hệ thống
    - Network adapter
    - Disk
    - Ports
- Các loại ảo hoá:
  - Ảo hoá server (server virtualization)
  - Ảo hoá network
  - Ảo hoá Storage
  - Ảo hoá Desktop 
- Software-defined data center (SDDC): là một hệ thống hạ tầng được ảo hoá hoàn toàn,
quyền kiểm soát được tự động thực hiện bởi phần mềm. **Vsphere là nền tảng của SDCC**
- Trong Vshphere, hyperviser là ESXi 
- VMware Host Client: là UI để quản lí ESXI 

# Virtual Machine hardware 
- VSphere đóng gói mỗi VM thành 1 VM file và lưu tại Datastore như VMFS, NFS,
vSAN, Vsphere Virtual Volume
![](images/Screen%20Shot%202022-10-30%20at%2022.18.37.png)

# Container
- Container: 1 ứng dụng với những dependencies được cài đặt cùng
- Container host: 1 VM hoặc máy chủ vật lý nơi container chạy
- Container engine: Phần quản lý containers trên container host 
- Docker: container engine phổ biến nhất hiện nay 
- Kubenetes: 1 tool để quản lí container 

![](images/Screen%20Shot%202022-10-30%20at%2022.34.42.png)

# VMware VSphere ESXI
- Là 1 hệ điều hành (linux customized) có chức năng duy nhất là tạo và quản lý máy ảo - Type 1 Hypervisor 
- Với ESXI UI, ta chỉ quản lý được 1 host duy nhất (tương ứng với IP của host). Để quản lý nhiều host, ta cần sử dụng vCenter. 

# vCenter 
- vCenter được cài đặt như một Appliance VM hoặc trên Window VM machine trên ESXI hosts 
- vCenter cung cấp giao diện quản lý tập trung của tất cả các ESXI hosts và VMs 
- Cho phép sử dụng các tính năng nâng cao như VM Cloning, vMotion, HA, Fault Tolerance, DRS. 
![](images/Screen%20Shot%202022-10-31%20at%2019.43.17.png)

# vSphere Standard Switches
- Standard Switches cung cấp khả năng kết nối giữa host và VMs (vLAN) và với mạng bên ngoài. 
- Để cung cấp kết nối, ta thực hiện kết nối giữa NIC của host tới uplink ports của switch. VM sử dụng vNIC để kết nối tới port group trên switch. Nếu port group không có physical NIC kết nối đến, VM trong group đó chỉ có thể liên lạc được với nhau và không giao tiếp được với bên ngoài.
- Port group được định danh bởi 1 network label duy nhất trên host. 
![](images/Screen%20Shot%202022-11-01%20at%2014.17.25.png)

