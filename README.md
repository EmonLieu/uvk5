# 全新的中文固件
该固件基于多个开源固件修改合并，拥有最多样性的功能，更适合中国宝宝体质！
* **更大容量的Eeprom芯片**
* **GB22312中文界面、信道**
* **频谱图**
* **MDC1200信令、联系人**
* **短信**
* **信号强度指示器（ S表 ）**
* **一键扫频**
* **收音机**
* **AM 修复**
* **SSB 解调**


# 操作说明(必读！！)

| 按键                                   | 功能                                                   |
|--------------------------------------|------------------------------------------------------|
| 🐤 **主界面下**                            |                                                      |
|**单按`上/下`**| 调整频率（步长为菜单1项`步进频率`）                                  |
|**单按`数字`**| 在频率模式下快捷输入频率                                         |
|**单按`*`**| 输入要发送的DTMF(`A、B、C、D、*、#`对应`M、上、下、*、F`键侧键1退格,按PPT键发送) |
|**长按`F`**| 锁定键盘                                                 |
|**长按`M`**| 切换调制模式                                               |
|**长按`*`**| 信道模式下是搜索列表,多次长按可切换(列表1/2/全部)，频率模式下,从当前频率开始搜索         |
|**长按`0`/`F+0`**| 打开/关闭收音机                                             |
|**长按`1`/`F+1`**| 在信道模式下将当前信道复制到另一个VFO                                 |
|**长按`2`/`F+2`**| 切换A/B通道                                              |
|**长按`3`/`F+3`**| 切换频率/信道                                              |
|**长按`4`/`F+4`**| 一键对频                                                 |
|**长按`5`**| 信道模式下切换搜索列表                                          |
|**长按`5`**| 频率模式下设置搜索频率范围(从通道A到通道B频率),按*键开始搜索                    |
|**`F+5`**| 频谱                                                   |
|**长按`6`/`F+6`**| 切换发射功率                                               |
|**长按`7`/`F+7`**| 声控发射开关                                               |
|**长按`8`/`F+8`**| 一键倒频                                                 |
|**长按`9`/`F+9`**| 一键即呼                                                 |
|**`F+M`**| 打开短信                                                 |
|**`F+UP`**| 按键音开关                                                |
|**`F+*`**| 扫描(数字/模拟)亚音                                          |
|**短按`侧键1`**| 监听                                                   |
|**长按`侧键1`**| DTMF解码开关                                             |
|**短按`侧键2`**| 设置宽窄带                                                |
|**长按`侧键2`**| 手电筒                                                  |







# Eeprom分布说明

| Eeprom地址                               | 描述                                                      |
|----------------------------------------|---------------------------------------------------------|
| 😭 **通用**                              | 版本号：LOSEHUxxx                                           |
| 0X01D00~0x02000                        | 基本不变                                                    |
| 0X01D00 ~ 0X01E00<br/>0X1F90 ~ 0X01FF0 | 22个MDC联系人<br/>每个联系人占用16B，前2B为MDC ID，后14B为联系人名           |
| 0X01FFF                                | MDC联系人数量                                                |
| 0x01FFD~0x01FFE                        | MDC ID                                                  |
| 0x01FF8~0x01FFC                        | 侧键功能                                                    |
| 0x01FFD~0x01FFE                        | MDC ID                                                  |
| 😱 **扩容版(K、H)**                        | 版本号：LOSEHUxxxK、LOSEHUxxxH                               |
| 0x02000~0x02012                        | 开机字符1                                                   |
| 0x02012~0x02024                        | 开机字符2                                                   |
| 0x02024~0x02025                        | 开机字符1、2的长度                                              |
| 0x02080~0x02480                        | 开机画面，长度128（宽）*64/8=1024=0x400                           |
| 0x01FFD~0x01FFE                        | MDC ID                                                  |
| 0x02480~0x0255C                        | gFontBigDigits，长度11*20=220=0XDC                         |
| 0x0255C~0x0267C                        | gFont3x5，长度96*3=288=0X120                               |
| 0x0267C~0x028B0                        | gFontSmall，长度96*6=564=0X234                             |
| 0x028B0~0x02B96                        | 菜单编码，长度53*14=742=0X2E6                                  |
| 0x02C00~0x02C64                        | CTCSS_Options,长度50*2=100=0x64                           |
| 0x02C64~0x02D34                        | DCS_Options,长度104*2=208=0xD0                            |
| 😨 **1Mib扩容版（K）**                      | 版本号：LOSEHUxxxK                                          |
| 0x02E00~0x1E1E6                        | GB2312中文字库,共6763*11*12/8=111590=0x1B3E6 |
| 😰 **2Mib扩容版（H）**                      | 版本号：LOSEHUxxxH                                          |
| 0x02E00~0x27332                        | GB2312中文字库,共6763*22=148786=0x24532                      |


# 示例

<p float="left">
  <img src="/images/c1.JPG" width=300 />
  <img src="/images/c2.JPG" width=300 />
  <img src="/images/c3.JPG" width=300 />
  <img src="/images/c4.JPG" width=300 />
</p>


# 用户功能自定义

你可以通过启用/禁用各种编译选项来定制固件

| 编译选项                                   | 描述                                                   |
|----------------------------------------|------------------------------------------------------|
| 🧰 **泉盛基本功能**                          |  https://github.com/egzumer/uv-k5-firmware-custom                                                    |
| ENABLE_UART                            | 串口，没有这个,你就不能通过PC配置无线电！                               |
| ENABLE_AIRCOPY                         | AirCopy无线复制                                          |
| ENABLE_FMRADIO                         | 收音机功能                                                |
| ENABLE_NOAA                            | NOAA功能 (只有在美国有用)                                     |
| ENABLE_VOICE                           | 语音播报                                                 |
| ENABLE_VOX                             | VOX声控发射                                              |
| ENABLE_ALARM                           | TX 警报                                                |
| ENABLE_PWRON_PASSWORD                  | 开机密码                                                 |
| ENABLE_DTMF_CALLING                    | DTMF拨号功能，呼叫发起，呼叫接收，群组通话，联系人列表等                       |
| ENABLE_FLASHLIGHT                      | 启用顶部手电筒LED灯（开启，闪烁，SOS）                               |
| ⌚ **自定义模组**                            |                                                      |
| ENABLE_BIG_FREQ                        | 大号字体的频率显示（类似官方泉盛固件）                                  |
| ENABLE_KEEP_MEM_NAME                   | 在重新保存内存频道时保持频道名称                                     |
| ENABLE_WIDE_RX                         | 全频18MHz至1300MHz接收（尽管前端/功率放大器未设计用于整个范围）               |
| ENABLE_TX_WHEN_AM                      | 当RX设置为AM时允许TX（始终为FM）                                 |
| ENABLE_F_CAL_MENU                      | 启用收音机的隐藏频率校准菜单                                       |
| ENABLE_CTCSS_TAIL_PHASE_SHIFT          | 使用标准CTCSS尾部相移，而不是QS独有的55Hz音调方法                       |
| ENABLE_BOOT_BEEPS                      | 在启动时为用户提供音频反馈，指示音量旋钮的位置                              |
| ENABLE_SHOW_CHARGE_LEVEL               | 在收音机充电时显示电池充电水平                                      |
| ENABLE_REVERSE_BAT_SYMBOL              | 在状态栏上镜像电池符号（正极在右侧）                                   |
| ENABLE_NO_CODE_SCAN_TIMEOUT            | 禁用32秒CTCSS/DCS扫描超时（按退出按钮而不是等待超时结束扫描                  |
| ENABLE_AM_FIX                          | 在AM模式下动态调整前端增益，以帮助防止AM解调器饱和，暂时忽略屏幕上的RSSI级别           |
| ENABLE_SQUELCH_MORE_SENSITIVE          | 将静噪电平稍微调敏感一些                                         |
| ENABLE_FASTER_CHANNEL_SCAN             | 增加频道扫描速度，但静噪调敏度也增加了                                  |
| ENABLE_RSSI_BAR                        | 启用以dBm/Sn为单位的RSSI条形图水平，取代小天线符号                       |
| ENABLE_AUDIO_BAR                       | 发送时显示音频条级别                                           |
| ENABLE_COPY_CHAN_TO_VFO                | 将当前频道设置复制到频率模式。在频道模式下长按  `1 BAND`                    |
| ENABLE_SPECTRUM                        | fagci 频谱分析仪，`F` + `5 NOAA`激活                         |
| ENABLE_REDUCE_LOW_MID_TX_POWER         | 使中等和低功率设置更低                                          |
| ENABLE_BYP_RAW_DEMODULATORS            | 额外的BYP（旁路？）和RAW解调选项，被证明并不十分有用，但如果你想实验的话，它是存在的        |
| ENABLE_SCAN_RANGES                     | 频率扫描的扫描范围模式                                          |
| ENABLE_BLOCK                           | Eeprom上锁                                             |
| ENABLE_WARNING                         | 	    BEEP提示音                                         |
| ENABLE_CUSTOM_SIDEFUNCTIONS            | 自定义侧键功能                                              |
| ENABLE_SIDEFUNCTIONS_SEND              | 自定义侧键功能（侧键发射功能）                                      |
| ENABLE_AUDIO_BAR_DEFAULT               | 默认语音条样式                                              |
| 🤖 **短信**                              | https://github.com/joaquimorg/uv-k5-firmware-custom  |
| ENABLE_MESSENGER                       | 发送和接收短文本消息（按键 = `F` + `MENU`）                        |
| ENABLE_MESSENGER_DELIVERY_NOTIFICATION | 如果收到消息，则向发送方发送通知                                     |
| ENABLE_MESSENGER_NOTIFICATION          | 在收到消息时播放声音                                           |
| 🌀 **MDC1200**                         | https://github.com/OneOfEleven/uv-k5-firmware-custom |
| ENABLE_MDC1200                         | MDC1200发送功能                                          |
| ENABLE_MDC1200_SHOW_OP_ARG             | MDC显示首尾音参数                                           |
| ENABLE_MDC1200_SIDE_BEEP               | MDC侧音                                                |
| ENABLE_MDC1200_CONTACT                 | MDC联系人                                               |
| 🎛️ **DOCK**                           | https://github.com/nicsure/QuanshengDock             |
| ENABLE_DOCK                            | 允许通过电脑控制手台，无屏幕显示！                                    |
| 🚫 **调试**                              |                                                      |
| ENABLE_AM_FIX_SHOW_DATA                | 显示AM修复的调试数据                                          |
| ENABLE_AGC_SHOW_DATA                   | 显示ACG参数                                              |
| ENABLE_UART_RW_BK_REGS                 | 添加了两个额外的命令，允许读取和写入BK4819寄存器                          |
| ⚠️ **编译选项**                            |                                                      |
| ENABLE_CLANG                           | 实验性质，使用clang而不是gcc构建（如果启用此选项，LTO将被禁用）                |
| ENABLE_SWD                             | 使用CPU的SWD端口，调试/编程时需要                                 |
| ENABLE_OVERLAY                         | CPU FLASH相关内容，不需要                                    |
| ENABLE_LTO                             | 减小编译固件的大小，但可能会破坏EEPROM读取（启用后OVERLAY将被禁用）             |



# 打赏

如果这个项目对您有帮助,可以考虑赞助来支持开发工作。

这是：[打赏名单](https://github.com/losehu/uv-k5-firmware-chinese/blob/main/payment/sponsors.md) 非常感谢各位对汉化工作的支持！！！

打赏码：

[![打赏码](https://github.com/losehu/uv-k5-firmware-chinese/blob/main/payment/show.png)](https://github.com/losehu/uv-k5-firmware-chinese/blob/main/payment/payment-codes.md)



# 免责声明：
* 本固件仅供技术交流和个人学习使用。任何个人或组织在使用本固件时必须**遵守中华人民共和国相关法律法规及无线电管理条例**。
* 作者对于他人使用本固件所产生的任何违法行为**概不负责**,包括但不限于未经授权擅自修改、使用本固件进行非法活动等行为。
* 如因使用本固件造成的损失,**作者不承担任何法律责任**。
* 使用者在下载、安装和使用本固件时,默认已经阅读、理解并同意本免责声明的所有内容。**如有异议,请立即停止使用本固件**。
* 作者保留在法律允许范围内对本免责声明进行解释和修改的权利。**任何未经授权的固件修改、传播所造成的违法行为,一概与作者无关**。

