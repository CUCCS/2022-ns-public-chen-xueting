
# 第一次实验

### 实验目的

- 掌握 VirtualBox 虚拟机的安装与使用；
- 掌握 VirtualBox 的虚拟网络类型和按需配置；
- 掌握 VirtualBox 的虚拟硬盘多重加载；

### 实验环境

- VirtualBox 虚拟机
- 攻击者主机（Attacker）：Kali Rolling 2019.2
- 网关（Gateway, GW）：Debian Buster
- 靶机（Victim）：From Sqli to shell / xp-sp3 / Kali

### 完成以下网络连通性测试；

- [x] 靶机可以直接访问攻击者主机
- [x] 攻击者主机无法直接访问靶机
- [x] 网关可以直接访问攻击者主机和靶机
- [x] 靶机的所有对外上下行流量必须经过网关
- [x] 所有节点均可以访问互联网

### 实验过程

- **拓扑结构**

<img src="img\vb-exp-layout.png" alt="tuopu" style="zoom:50%;" />

- 环境

  - ![](img\target.bmp)
  - <img src="img\interfaces.bmp" style="zoom: 25%;" />

- 拓扑图对应设备一览

  - <img src="img\struct.bmp" alt="tuopu" style="zoom: 25%;" />

- 网关网卡设置一览

  - <img src="img\gw_interner.bmp" alt="gw" style="zoom: 50%;" />

- 网络联通测试(所有节点可以访问互联网)

  - Debian2![](img\Debian2_net.bmp)

  - XP2

    <img src="img\xp2_net.bmp" style="zoom:25%;" />

  - XP1

    <img src="img\xp1_net.bmp" style="zoom:25%;" />

  - Kali1

    ![](img\kali1_net.bmp)

  - kali-attacker

    ![](F:\A_homework\2022-ns-public-chen-xueting\2022-ns-public-chen-xueting\第一次实验\img\attacker_net.bmp)

  - gateway

    <img src="img\xp2_net.bmp" style="zoom:25%;" />

- 靶机访问攻击者主机联通测试

  攻击者主机IP`10.0.2.4`

  ![](img\xp2_attacker.bmp)

  ![](img\kali_attacker.bmp)

- 攻击者主机无法直接访问靶机

  xp-victim IP地址`172.16.111.119`

  kali-victim IP地址`172.16.111.124`

  ![](img\attacker_kali.bmp)

  

  ![](F:\A_homework\2022-ns-public-chen-xueting\2022-ns-public-chen-xueting\第一次实验\img\attacker_xp.bmp)

  

- 网关可以直接访问攻击者主机和靶机

  - 访问攻击者主机 IP `10.0.2.4`

  - 访问靶机 IP `172.16.111.124`

    <img src="F:\A_homework\2022-ns-public-chen-xueting\2022-ns-public-chen-xueting\第一次实验\img\gw.bmp" style="zoom:50%;" />

- 靶机的所有对外上下行流量必须经过网关

  ![](img\pcap.bmp)

  ## 注意事项

  - 在使用tcodump命令时需要在root下进行下载，当下载完成后仍然出现command not found时，需要将添加环境变量，可以执行以下语句：

    - `export PATH=$PATH:$HOME/bin:/usr/sbin`

    

