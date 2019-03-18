### DUET
DUET(Developer's UEFI Emulation)，开发者的UEFI模拟.

虽然现在已经进入了UEFI时代，但是因为UEFI刚刚开始取代BIOS，目前依然有很多运行着的BIOS系统。为了方便开发者从BIOS转移到UEFI，EDK2提供了DUET，用于在BIOS系统上模拟UEFI执行环境。  
DUET（Developer's UEFI Emulation）是基于Legacy BIOS系统的UEFI模拟器，主要为UEFI开发者提供一个在传统BIOS系统上的UEFI运行环境。DUET支持基于MBR的启动方式，从MBR启动后进入UEFI执行环境。  
### EDK  
EDK全称EFI Developer Kit，它实际上是一套实现了UEFI标准的开源代码，开发者可以在此基础上开发UEFI下的设备驱动或者其它应用。

EDK发展到现在已经经历了几代了，早期有EFK，后来是EDK，到现在的EDKII。EDKII兼容EDK，目前这两者都有使用，并且通常会混合使用。

https://github.com/tianocore/edk2

config.plist:
是放在EFI引导盘下的一个配置文件，这个配置文件将决定很多东西；
它将决定是否能引导成功，进不了系统八层都是这个问题；

kext
以这个结尾的文件都是驱动文件，能否驱动成功发挥正常功能就看这个了；
和Win不同的是，Mac的驱动只是一个编译的文件，所以都很小;
你在决定装黑苹果前，可以先搜罗一批你硬件的对应Kext;
建议放在EFI盘:\EFI\CLOVER\Kext\Other下，这样如果你需要通过修改必要Config配置文件进入Mac的也方便

### nouncement
ACPI:Advanced Configuration and Power Management Interface
Incluing:  
	System power management（系统电源管理）
	Device power management（设备电源管理）
	Processor power management（处理器电源管理）
	Device and processor performance management（设备及处理器性能管理）
	Configuration / Plug and Play（配置/即插即用）
	System Events（系统事件）
	Battery management（电池管理）
	Thermal management（温度管理）
	Embedded Controller（嵌入式控制器）
	SMBus Controller（SMBus控制器）
	ACPI由很多表组成,包括：RSDP，SDTH，RSDT，FADT，FACS，DSDT，SSDT，MADT，SBST，XSDT，ECDT，SLIT，SRAT  
	Mac OS X不完整支持ACPI规范，仅支持它的子集DSDT。  
SSDT:
	CPU配置文件，和DSDT在一个地方，用于配置CPU降频等功能；
	这个文件只要有和你相同的CPU就能用了，适应性很强；
	其实功能就这么一点。

LPC
SMBUS


EIST:Enhanced Intel SpeedStep Technology，GV3
	https://zhuanlan.zhihu.com/p/25675218

DSDT:The Differentiated System Description Table
	 主板BIOS控制文件，硬件配置文件；
	 希望实现BIOS功能，高级硬件功能，比如睡眠（很多人都会告诉你黑苹果不能睡眠，但很多人睡的很好）；
	 一些快捷功能键，比如屏幕亮度，音量控制，在PC下的Fn+F1-F12的功能，都必须通过这个调整实现；
	 如果是Clover引导（本帖只推荐Clover引导），这个文件在 EFI盘：\EFI\CLOVER\ACPI\patched下；  

HDAU:High Definition Audio
HDEF:
APIC:Advanced Programmable Interrupt Controller	
NMI:Non Maskable Interrupt
PCI:Peripheral Component Interconnect
NvRAM:Non-Volatile Random Access Memory
FSB:Front Side Bus

### 硬件组装
Haswell架构是英特尔第四代CPU架构
[Intel CPU系列发展史](ttps://wenku.baidu.com/view/e465434b2b160b4e767fcf44.html)
[Intel CPU命名规则](https://www.cnblogs.com/LvBaiYang/p/6930989.html)

Intel主板芯片组：Intel 200系列(Z270\H270\B250) Intel 100系列(Z170\H170\B150\H110)
