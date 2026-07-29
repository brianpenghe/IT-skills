---
title: '怎样链接MIDI键盘到OVERTURE'
date: 2015-10-01T00:55:00.000-07:00
draft: false
url: /2015/10/midioverture.html
---

> **Archived note — originally created: 2015-10-01 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


**(a)、检查MIDI设备是否被正常使用**

 **![](http://www.popiano.org/ove_ch33.jpg)** 

在上图中我们可以在右边的“输出设备”中一一单击所对应的“测试”按钮，直到测试到能够发出声音的设备，并在“所选项移至顶端”按钮将能够发声的这个设备，调整到最上端，指定为OVE提供的默认MIDI设备即可。

如果你在电脑上连接了MIDI键盘，那么需要将左边的“激活MIDI Thru”前的对勾也打上，以方便使用键盘输入音符来打谱。

啊！什么？还是不响！如果按照上述操作还是没有声音，那么继续往下看吧！

**（b）、检查软件的参数设置项**

在OVE工具栏——〉选项——〉参数设置，打开该窗口。

 ![](http://www.popiano.org/ove_ch34.jpg) 

**（c）、由于安装了第三方声卡驱动，而造成的MIDI不发生情况也是不可忽视的。**

我们知道，现在的板载声卡仅仅能够在音频格式（MIDI不是音频格式）的回放上做得非常出色了，但是由于其使用的MIDI软波表，仍然离不开微软所提供的标准波表序列。所以很多比较挑剔的朋友们毫不客气地摒弃系统自带的MIDI音色库，而使用较为优秀的YAMAHA XG SoftSynthesizer系列，以使的MIDI回放得到较理想的效果。事实上，这个音色库软件的确比Windows自带的以及创新声卡的MIDI支持上强了许多。

正是由于安装了YAMAHA XG SoftSynthesizer的软件合成器，所以势必对原来的MIDI驱动加以更改了，由此带来的情况是：过去用得挺好的OVE突然之间罢工了！其实解决这个问题也是非常简单的：安装第三方驱动程序后，系统会要求重新启动以使得改进的驱动生效，如果驱动本身产生了错误，那么重新启动后系统会提示的，并要求重新安装驱动程序。如果没有提示，那就不用担心我们的系统因为安装第三方驱动而产生问题了。解决方法是：

**第一步：重新进行参数设置**

在OVE工具栏中——〉选项——〉MIDI设备中，检查第三方MIDI设备能否发声？如果你能够听到声音，那就恭喜啦！你没有遇到大问题。

 **![](http://www.popiano.org/ove_ch35.jpg)** 

将这个MIDI设备设为OVE的首选项并移至顶端，然后关闭。

**第二步：重新设置音频轨的device项**

在OVE工具栏上——〉窗口——〉打开音频窗口，重新设定音频窗口中device的MIDI设备即可。

 ![](http://www.popiano.org/ove_ch36.jpg) 

看到上图了，如果两者之间没有选择相同的设备，那么肯定就不能够使乐谱上的MIDI事件得到回放。

好！大功告成。

原文地址：http://www.popiano.org/ove\_check.htm

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
