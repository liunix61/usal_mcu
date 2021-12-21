# usal_mcu  
===========================  
usal_mcu  
###########简单说明  
  
实现仿linux分层架构实现mcu通用系统,方便芯片级切换以及多产品线开发  
  
主要特点:  
1.代码风格采用c语言的面向对象写法,支持跨平台  
2.分层架构,驱动层，系统层，应用层，三者清晰独立  
2.驱动和内核独立出简单配置文件,切换外设只需要修改对应配置文件即可  
2.所有设备均为注册挂载式,方便剪裁,并且模仿linux vfs接口统一为open,close,write,read等接口  
3.接口统一，应用使用接口为kfc头文件,简单清晰  
3.整体结构清晰,预留多产品线应用支持  
  
注:整体代码风格采用c语言面向对象写法参照鸿泉沈工和陆工并引用其个别文件，内存分配引用鸿泉叶工,其他整体架构和代码为个人完成  
  
###########部署步骤  
keil  
mcu:stm32f4  
###########目录结构描述  
├── doc					  	  ///< 说明文档  
├── public					  ///< 公共头文件  
├── lib					  	  ///< 通用库  
├── arch              ///< 芯片层接口  
│      └── stm32f4                         ///< stm32f4芯片支持  
│        -  -  - ├── cfg                         ///< 驱动配置文件  
│        -  -  - ├── drv                         ///< drv驱动程序  
│        -  -  - └── hal                         ///< 芯片厂家程序  
├── bootldr					  ///< bootldr引导启动文件  
├── kernel					  ///< 内核层  
│      ├── kfc                         	///< 应用使用所有内核接口  
│      ├── cfg                         	///< 内核配置  
│      ├── dev                         	///< 内核设备注册  
│      ├── mem                         	///< 内核内存管理  
│      ├── rtos                         ///< 内核操作系统(cmsis-rtx)  
│      ├── vfs                         	///< 内核虚拟文件系统  
│      ├── srt                         	///< 内核共享内存  
│      ├── fatfs                        ///< 内核文件系统  
│      ├── thread                       ///< 内核线程实现  
│      ├── per_can_mcp2515              ///< 内核外设spican  
│      └── per_ext_flash                ///< 内核外设外部flash存储  
├── app             ///< 应用目录  
│      └── app_test                  		///< 接口使用测试程序  
└── usr						  ///< app启动文件  
└── sln					    ///< 工程文件  
  
  
###########V1.0.0 版本内容更新  
1. 新功能 基本内核功能  
  
