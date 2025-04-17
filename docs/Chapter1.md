# 部署Keil C51开发环境

Keil C51是美国Keil软件公司（现已被ARM收购）出品的一款支持8051系列单片机的IDE（集成开发环境）

本次PE项目采用的MCU为STC89C52RC，需要用到Keil C51进行工程的创建和编译.

请在[教学资源](http://suat.ysyx.org:81/download.html)下载安装包keil5并解压.

本小节需要用到的程序包括:

- /keil MDK V5.18/c51v959.exe
- /STC-ISP/stc-isp-15xx-v6.88.exe
- /破解程序/Keil MDK V5注册机(2032).exe

Keil C51安装步骤如下：
- 双击安装包c51v959.exe，进入安装向导界面，点击“Next”  
<img src="../public/Chapter1/Figure1.png" alt="安装向导" width="400"/>

- 勾选"I agree to… ", 点击"Next"

- 选择路径（可以使用默认），点击"Next"

- 填写信息（可以随便填写），点击"Next"  
<img src="../public/Chapter1/Figure2.png" alt="填写信息" width="400"/>

等待安装过程结束，安装完成后，点击"Finish"，安装完成（弹出C51介绍页面可以关闭）

由于免费版有各种限制，需要使用注册机生成注册码，在本项目中我们使用学习版Keil.

注册机的使用步骤如下：
- 首先启动安装好（默认会在桌面创建快捷方式）的Keil uVision5  
注意：**右键点击快捷方式，选择“以管理员身份运行”**
<img src="../public/Chapter1/Figure3.png" alt="以管理员身份运行" width="400"/>  

- 点击"File - License Management..."  
<img src="../public/Chapter1/Figure4.png" alt="License Management" width="400"/>  

- 复制右侧的"Computer ID - CID"  
<img src="../public/Chapter1/Figure5.png" alt="Computer ID" width="400"/>  

- 接下来启动之前下载的Keil MDK V5注册机(2032).exe，注意该注册机启动时会有一阵强劲的电吉他，记得提前把音量调小（课堂上最好静音）  
如果出现下图所示的恶意文件提示，点击“更多信息” - “仍要运行”  
<img src="../public/Chapter1/Figure6.png" alt="恶意文件提示" width="400"/>  
同时可能还会出现Microsoft Defender的提示，点击“开始菜单” - “设置”  
<img src="../public/Chapter1/Figure7.png" alt="提示" width="400"/>  
<img src="../public/Chapter1/Figure8.png" alt="运行" width="400"/>  
搜索“安全中心”  
<img src="../public/Chapter1/Figure9.png" alt="安全中心" width="400"/>  
点击“保护历史记录”，应该能看到时间最接近的一次“已隔离威胁”，展开后选择“操作” - “还原”
<img src="../public/Chapter1/Figure10.png" alt="还原" width="400"/>  
这时注册机程序应该已经被还原到解压缩的目录下.

- 启动注册机（再次提醒一下音量控制）  
粘贴刚才复制的CID到注册机中的CID一栏去，其他部分不用修改，单击Generate即可。
<img src="../public/Chapter1/Figure11.png" alt="注册机" width="400"/>  
下面生成的一行就是注册码，复制下来。

- 回到Keil的注册界面：(1)粘贴上面生成的“注册码”，(2)点击“Add LIC”，(3)看见显示信息说明注册成功。
<img src="../public/Chapter1/Figure12.png" alt="注册成功" width="400"/>  

Keil的安装和破解到这里就结束，由于Keil C51并不官方支持STC系列芯片，我们需要通过刚刚解压的第三个工具为其添加STC89C52RC的配套文件：

- 双击解压的stc-isp-15xx-v6.88.exe，进入界面后在右上角找到“Keil仿真设置”  
<img src="../public/Chapter1/Figure13.png" alt="ISP" width="400"/>  

- 点击“添加型号和头文件到Keil中”，选择Keil安装路径，默认为C:/Keil_v5，单击确定即可.
<img src="../public/Chapter1/Figure14.png" alt="添加" width="300"/>  

安装成功后重新启动Keil, 点击Project - Create New Project，应该能在Select Device for Target界面选择STC MCU Database了.  
<img src="../public/Chapter1/Figure15.png" alt="STC" width="400"/>  

