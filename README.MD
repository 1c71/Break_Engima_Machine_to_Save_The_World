
py-enigma




暂时还不知道的：


        1 那3个轮子，拿出来轮子是可以转动的，不是死的
        怎么转？？为啥要转？
        2 那 5 个轮子是不是排线不一样，我觉得是
        3 图片里的最后一列，是什么？






说白了就是 plugboard  rotor  reflexter 三个，里面都有26个字母一一对应的变换

5个rotor里有不同的配线，26个字母的对应不一样，
然后抽3个出来，以不同的顺序排，所以就有不同的结果了


你会拿到英格玛模拟器和一大段密文，
然后还有一小段密文，是100%对应的


先设定好 engima，自己加密一段东西，
然后才能试着去解密


先了解了写出来再说，那么多废话干吗
要写两个版本吗？中文 + 英文？


你要在不知道密码 sheet 的情况下破解出答案



============================

## 破解英格玛密码机 ( Crack Engima Machine to save the world )
![1.Enigma-machine.jpg](Image of a Enigma Machine)
这里有一个英格玛模拟器,
而你要做的就是 写一个程序, 作用和阿兰图灵的 Bomba 机器一样
破解德国人用 Enigma 加密的密文
帮助同盟国击败纳粹德国


<br/>
### 1. 简单介绍 (包括这段, 共x段)
英格玛密码机 (Engima Machine) 是德国在二战期间用的机器
作用是加密信息, 然后把加密后的信息通过无线电发出去,
这样只有友军才知道是什么意思.
其他人即便通过无线电收到了信息也没法知道是什么.

Enigma 机器的使用方法和原理不是这里几句话能写清楚的,
所以请看简单易懂的视频:

1 [數字狂 非官方繁體中文字幕]_Enigma Machine 數字狂
https://www.youtube.com/watch?v=J46hu4RMB5I

2 [數字狂 非官方繁體中文字幕]_Engima 的缺陷 Flaw in the Enigma Code 數字狂
https://www.youtube.com/watch?v=Sqpe5vZoKTo

注: 只看完这2个视频你是没法写代码实现 Enigma 的，有些细节视频里没说.
比如

1 从5个转轮里抽3个是什么意思，为什么要抽3个？(00:00)
转轮上面不都是01~26吗？

2，字母怎么经过3个轮子然后又绕回来再次经过3个轮子？具体怎么弄的？
比如到了第3个轮子，数字是37，然后视频说又回去，那不是回到第1个轮子的时候，数字和一开始进第1个轮子的时候一样了吗？

3. 按键是字母，轮子是数字，这之间的对应关系是什么？
因为比如你按下了P，经过插线板变成了M，下一步就应该去轮子那边了，但是M这个数字到了轮子那边怎么办？

4. PlugBoard 有10组，一组2个字母，也就是20个字母之间的对应关系，
那么还有6个字母没有连线的字母怎么弄？

这几个我们后面说，这里写就太长了。

<br/>
### 玩法介绍



<br/>
### 任务


<br/>
### 补充视频
补充视频存在的意义是:
光看前2个视频只能了解一些大概, 还有几个问题没解决，如果你想要完全理解，
那么

http://red-badger.com/blog/2015/02/23/understanding-the-enigma-machine-with-30-lines-of-ruby-star-of-the-2014-film-the-imitation-game/


Enigma Extra Footage - Numberphile
https://www.youtube.com/watch?annotation_id=annotation_509771&feature=iv&src_vid=V4V2bpZlqx8&v=BdrrJ7qd4HA

<br/>
#### 补充信息:
1 你不知道字母和数字之间的关系




4 字母轮子和数字轮子有不同的表


-1 Engima 里，字母和数字的对应方式是 A1 B2 C3 这样到Z26
0 有 Reflecter
1 轮子不只是能转, 还能拿出来调换顺序(N多视频都有说这一点)
1 转轮不只是有数字的, 也有字母的
2 转轮有的有4个(M4型号), 并不是所有型号都是3个
3 有其他国家觉得 Enigma 不错的, 了解之后改进了一下自己用


<br/>
### 我为啥写这个
好玩



<br/>
##### 资料来源





<br/>
### 我的完全总结

1 Enigma 的主要部分: keyboard(键盘), plugboard(插线板), 亮灯区域, rotor(转子)

1. 理解 Enigma 的重点是这个机器里字母和数字的对应关系
A 对应 1
B 对应 2
...
Z 对应 26


2. Enigma 最简单的破解法是拿到密码本, 可惜不是总是能拿到

3. 整个破解的突破点之一是德军每天会以固定格式发送天气,
这样我们就知道某段密文，对应一段明文. 可以以此基础上进行破解

4. 如果没插插线板, 那么就不对应字母, 直接送到 rotor
26个字母如果全部要一一对应那么是13组，但是一般都是只插10组
那么剩下6个会原样送到 rotor

5. 怎么绕回来 Refleter

<br/>
### 再深入一点
英文和德文里都有空格, 但是 Enigma 里很明显不能发空格,
那么空格问题到底怎么办??



<br/>
### 其他推荐 (可看可不看, 对于理解这里的代码影响不大)
图灵 1912-1954



艾倫・圖靈：生平與功績簡介（中文字幕） Alan Turing: biography and achievements
https://www.youtube.com/watch?v=ANK8-poUDiI

WWII Enigma Machine: The Enigma Project
https://www.youtube.com/watch?v=elYw4Ve4F-I


Bletchley Park: The Enigma Machine
https://www.youtube.com/watch?v=faRfab9Yyk8


Imitation Game: how did the Enigma machine work?  (2分钟26秒)
https://www.youtube.com/watch?v=TYX691q2J2c
推荐理由: 这个视频里介绍了其他视频都跳过不讲的 Reflecter


Enigma - The True Story (6分49秒)(UnknownHistory - BitmapAxis)
https://www.youtube.com/watch?v=2OcC-8zUUEc


Lorenz: Hitler's "Unbreakable" Cipher Machine (11分钟42秒)(singingbanana)
https://www.youtube.com/watch?v=GBsfWSQVtYA
推荐理由: 这个不是讲 Enigma, 是讲 Lorenz



Turing's Enigma Problem (Part 1) - Computerphile (18分钟59秒)
https://www.youtube.com/watch?v=d2NWPG2gB_A
推荐理由:
1 插线板部分, 字母和数字的对应, 拍摄的很清晰
2 讲清楚了如果插线板没插线, 那么字母不会变, 原样送到 rotor, 以及一般是插10组，而不是13组全部插满.












