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
