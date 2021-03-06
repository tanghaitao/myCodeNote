- Video25: 对应视频:`025. 13 QuickTime mp4容器分析_recv.ev4`
- Video26: 对应视频:`026. 14 AAC 音频格式_recv.ev4`
- Video27: 对应视频:`027.15 AAC实时转换 1_recv.ev4`
- Video28: 对应视频:`028. 16 AAC实时转换 2_recv.ev4`




# Video25

## 1.  MP4格式(H. 264+AAC)

1. MP4格式对应标准为ISO/IEC 14496-12(信息技术 视听对象编码的第12部分: IS0 基本媒体文件格式 /Information technology Coding of audio-visual objects Part 12: ISO base media file format) 附--标准免费下载: Freely Available

2. MP4封装格式是基于QuickTime容器格式定义，媒体描述与媒体数据分开，目前被广泛应用于封装h.264视频和ACC音频，是高清视频/HDV的代表。

3. MP4文件中所有数据都封装在`box`中(对应QuickTime中的`atom`),即MP4文件是由若干个box组成，每个box有`长度`和`类型`，每个box中还可以包含另外的`子bo`x (称`container box`) 。

4. MP4中box存储方式为`大端模式`。一般，标准的`box开头`会有四个字节的`box size`.

- 一个MP4 文件**首先**会`有且只有`**一个**“**ftyp**” 类型的**box**,作为MP4格式的标志并包含关于文件的一些信息;
- **之后**会`有且只有`一个“**moov**”`类型`的`box` (`Movie Box`),它是一种`container box`,`子box`包含了媒体的`metadata信息`;
- MP4文件的`媒体数据`包含在“**mdat**” `类型`的box (`Midia Data Box`) 中，该类型的box也是`container box`, `可以有多个`，`也可以没有`(当媒体数据全部引用其他文件时)，媒体数据的结构由`metadata` 进行描述。


---

- **track**: 表示一些`sample`的集合，对于媒体数据来说，`track`表示一个`视频`或`音频`**序列**。

- **hint track**: **特殊的**`track`, `并不包含`**媒体数据**，包含的是一些`将``其他数据track` **打包**成`流媒体`的`指示信息`。

- **sample**: 对于`非hint track`来说， `video sample`即为`一帧视频`，**或**`一组`**连续**`视频帧`， `audio sample`即为`一段`**连续**的`压缩音频`，它们**统称**`sample`.对于`hint track,` **sample**定义`一个`或`多个`**流媒体包**的格式。

- **sample table**:  指明`sample`**时序**和**物理布局**的表。

- **chunk** :一个**track**`的`几个**sample** **组成**的**单元**。


## mp4 Info 工具

![mp4aac001](images/mp4aac001.png)


![mp4aac002](images/mp4aac002.png)



# 2. AAC


AAC (Advanced Audio Coding) , 中文名: `高级音频编码`，出现于1997年，**基于**`MPEG- 2`的音频编码技术。由Fraunhofer IIS、杜比实验室、AT&T、Sony等公司共同开发，目的是取代MP3格式。2000年，MPEG-4标准出现后，AAC 重新集成了其特性，加入了`SBR`技术和`PS`技术，为了区**别于**传统的`MPEG-2 AAC`又称为`MPEG-4 AAC`。


- `优点`: 相对于mp3，AAC格式的`音质更佳`，`文件更小`。

- `不足`: AAC属于`有损压缩`的格式，与时下流行的APE、FL AC等无损格式相比音质存在“本质上”的差距。加之，传输速度更快的USB3.0和16G以上大容量MP3正在加速普及，也使得AAC头.上“小巧”的光环不复存在了。

## 2.2 音频采样率

`音频采样率` 是指录音设备在`一秒钟内`对声音信号的`采样次数`，采样频率越高声音的还原就越真实越自然。在当今的主流采集卡上，采样频率一般共分为22.05KHz、44. 1KHz、48KHz三个等 级，22.05KHz只能达到FM广播的声音品质，44. 1KHz则是理论.上的CD音质界限，48KHz则更加精确些.。

## 2.3 比特率

- `比特率`是指`每秒`传送的`比特(bit)数`。单位为 `bps` (`Bit Per Second`), 比特率越高，传送数据速度越快。**声音中**的比特率是指将`模拟声音信号`转换成`数字声音信号`后，单位时间内的`二进制数据量`，是间接衡量音频质量的一个指标。**视频中**的比特率(码率) 原理与声音中的相同，都是指由**模拟**信号**转换**为**数字**信号后，单位时间内的二进制数据量。

- 信道编码中，`K符号`大小的信源数据块通过编码映射为`N符号`大小的码字，则`K/N` 成为码率，其中假设编码前后的符号表没有变化。

## 2.3 采样精度

`采样精度`决定了记录声音的`动态范围`，它以位(`Bit`)为 **单位**，比如`8位`、 `16位`。`8位`可以把声波分成`256级`，`16位`可以把同样的波分成`65`, `536级`的信号。可以想象，位数越高，声音的保真度越高。

- 采样精度`样本大小`是用每个声音样本的`位数bit/s`(`即bps`)表示的，它反映`度量`**声音波形**`幅度`的精度。例如，每个声音样本用`16位(2字节)`表示，测得的声音样本值是在`0~ 65535`的范围里，它的精度就是输入信号的1/65536. 样本位数的大小影响到声音的质量，位数越多，声音的质量越高，而需要的存储空间也越多; 位数越少，声音的质量越低，需要的存储空间越少。

- `采样精度`的另一种`表示方法`是**信号噪声比**，简称为`信噪比`(**signal-to-noise ratio,SNR**)，并用下式计算:
  - SNR= 10 log [(Vsignal)2 / (Vnoise)2]=20 log (Vsignal / Vnoise)

  - `Vsignal`表示信号`电压`，`Vnoise`表示噪声 `电压`; SNR的单位为`分贝(dB)`。

  - 例1:假设Vnoise=1, 采样精度为1位表示Vsignal=2的1次方，它的信噪比SNR=6分贝。

  - 例2:假设Vnoise=1, 采样精度为16位表示Vsignal=2的16次方，它的信噪比SNR=96分贝。



