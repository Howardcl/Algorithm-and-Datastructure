# 1.常用文件管理命令

操作服务器的话，跟本地的操作系统环境没有任何关系。

未来工作方式：只要有一个终端就可以

![image-20211029091604383](https://raw.githubusercontent.com/Howardcl/MyImage/main/img/image-20211029091604383.png)

``` c++
(1) ctrl c: 取消命令，并且换行
(2) ctrl u: 清空本行命令
(3) tab键：可以补全命令和文件名，如果补全不了快速按两下tab键，可以显示备选选项
(4) ls: 列出当前目录下所有文件，蓝色的是文件夹，白色的是普通文件，绿色的是可执行文件
(5) pwd: 显示当前路径
(6) cd XXX: 进入XXX目录下, cd .. 返回上层目录
(7) cp XXX YYY: 将XXX文件复制成YYY，XXX和YYY可以是一个路径，比如../dir_c/a.txt，表示上层目录下的dir_c文件夹下的文件a.txt
(8) mkdir XXX: 创建目录XXX
(9) rm XXX: 删除普通文件;  rm XXX -r: 删除文件夹
(10) mv XXX YYY: 将XXX文件移动到YYY，和cp命令一样，XXX和YYY可以是一个路径；重命名也是用这个命令
(11) touch XXX: 创建一个文件
(12) cat XXX: 展示文件XXX中的内容
(13) 复制文本
    windows/Linux下：Ctrl + insert，Mac下：command + c
(14) 粘贴文本
    windows/Linux下：Shift + insert，Mac下：command + v

rm *.txt 删掉所有的txt
rm a -r 删文件夹
```

# 2.tmux和vim

**1.tmux教程**

```c++
功能：
    (1) 分屏。
    (2) 允许断开Terminal连接后，继续运行进程。
结构：
    一个tmux可以包含多个session，一个session可以包含多个window，一个window可以包含多个pane。
    实例：
        tmux:
            session 0:
                window 0:
                    pane 0
                    pane 1
                    pane 2
                    ...
                window 1
                window 2
                ...
            session 1
            session 2
            ...
操作：
    (1) tmux：新建一个session，其中包含一个window，window中包含一个pane，pane里打开了一个shell对话框。
    (2) 按下Ctrl + a后手指松开，然后按%：将当前pane左右平分成两个pane。
    (3) 按下Ctrl + a后手指松开，然后按"（注意是双引号"）：将当前pane上下平分成两个pane。
    (4) Ctrl + d：关闭当前pane；如果当前window的所有pane均已关闭，则自动关闭window；如果当前session的所有window均已关闭，则自动关闭session。
    (5) 鼠标点击可以选pane。
    (6) 按下ctrl + a后手指松开，然后按方向键：选择相邻的pane。
    (7) 鼠标拖动pane之间的分割线，可以调整分割线的位置。
    (8) 按住ctrl + a的同时按方向键，可以调整pane之间分割线的位置。
    (9) 按下ctrl + a后手指松开，然后按z：将当前pane全屏/取消全屏。
    (10) 按下ctrl + a后手指松开，然后按d：挂起当前session。
    (11) tmux a：打开之前挂起的session。
    (12) 按下ctrl + a后手指松开，然后按s：选择其它session。
        方向键 —— 上：选择上一项 session/window/pane
        方向键 —— 下：选择下一项 session/window/pane
        方向键 —— 右：展开当前项 session/window
        方向键 —— 左：闭合当前项 session/window
    (13) 按下Ctrl + a后手指松开，然后按c：在当前session中创建一个新的window。
    (14) 按下Ctrl + a后手指松开，然后按w：选择其他window，操作方法与(12)完全相同。
    (15) 按下Ctrl + a后手指松开，然后按PageUp：翻阅当前pane内的内容。
    (16) 鼠标滚轮：翻阅当前pane内的内容。
    (17) 在tmux中选中文本时，需要按住shift键。（仅支持Windows和Linux，不支持Mac，不过该操作并不是必须的，因此影响不大）
    (18) tmux中复制/粘贴文本的通用方式：
        (1) 按下Ctrl + a后松开手指，然后按[
        (2) 用鼠标选中文本，被选中的文本会被自动复制到tmux的剪贴板
        (3) 按下Ctrl + a后松开手指，然后按]，会将剪贴板中的内容粘贴到光标处

```

**2.vim教程**

```c++
功能：
    (1) 命令行模式下的文本编辑器。
    (2) 根据文件扩展名自动判别编程语言。支持代码缩进、代码高亮等功能。
    (3) 使用方式：vim filename
        如果已有该文件，则打开它。
        如果没有该文件，则打开个一个新的文件，并命名为filename
模式：
    (1) 一般命令模式
        默认模式。命令输入方式：类似于打游戏放技能，按不同字符，即可进行不同操作。可以复制、粘贴、删除文本等。
    (2) 编辑模式
        在一般命令模式里按下i，会进入编辑模式。
        按下ESC会退出编辑模式，返回到一般命令模式。
    (3) 命令行模式
        在一般命令模式里按下:/?三个字母中的任意一个，会进入命令行模式。命令行在最下面。
        可以查找、替换、保存、退出、配置编辑器等。
操作：
    (1) i：进入编辑模式
    (2) ESC：进入一般命令模式
    (3) h 或 左箭头键：光标向左移动一个字符
    (4) j 或 向下箭头：光标向下移动一个字符
    (5) k 或 向上箭头：光标向上移动一个字符
    (6) l 或 向右箭头：光标向右移动一个字符
    (7) n<Space>：n表示数字，按下数字后再按空格，光标会向右移动这一行的n个字符
    (8) 0 或 功能键[Home]：光标移动到本行开头
    (9) $ 或 功能键[End]：光标移动到本行末尾
    (10) G：光标移动到最后一行
    (11) :n 或 nG：n为数字，光标移动到第n行
    (12) gg：光标移动到第一行，相当于1G
    (13) n<Enter>：n为数字，光标向下移动n行
    (14) /word：向光标之下寻找第一个值为word的字符串。
    (15) ?word：向光标之上寻找第一个值为word的字符串。
    (16) n：重复前一个查找操作
    (17) N：反向重复前一个查找操作
    (18) :n1,n2s/word1/word2/g：n1与n2为数字，在第n1行与n2行之间寻找word1这个字符串，并将该字符串替换为word2
    (19) :1,$s/word1/word2/g：将全文的word1替换为word2
    (20) :1,$s/word1/word2/gc：将全文的word1替换为word2，且在替换前要求用户确认。
    (21) v：选中文本
    (22) d：删除选中的文本
    (23) dd: 删除当前行
    (24) y：复制选中的文本
    (25) yy: 复制当前行
    (26) p: 将复制的数据在光标的下一行/下一个位置粘贴
    (27) u：撤销
    (28) Ctrl + r：取消撤销
    (29) 大于号 >：将选中的文本整体向右缩进一次
    (30) 小于号 <：将选中的文本整体向左缩进一次
    (31) :w 保存
    (32) :w! 强制保存
    (33) :q 退出
    (34) :q! 强制退出
    (35) :wq 保存并退出
    (36) :set paste 设置成粘贴模式，取消代码自动缩进
    (37) :set nopaste 取消粘贴模式，开启代码自动缩进
    (38) :set nu 显示行号
    (39) :set nonu 隐藏行号
    (40) gg=G：将全文代码格式化
    (41) :noh 关闭查找关键词高亮
    (42) Ctrl + q：当vim卡死时，可以取消当前正在执行的命令
异常处理：
    每次用vim编辑文件时，会自动创建一个.filename.swp的临时文件。
    如果打开某个文件时，该文件的swp文件已存在，则会报错。此时解决办法有两种：
        (1) 找到正在打开该文件的程序，并退出
        (2) 直接删掉该swp文件即可

```

![image-20220817143421048](https://raw.githubusercontent.com/Howardcl/MyImage/main/image-20220817143421048.png)

**移动光标**

1、左移h、右移l、下移j、上移k

2、向下翻页ctrl + f，向上翻页ctrl + b

3、向下翻半页ctrl + d，向上翻半页ctrl + u

4、移动到行尾$，移动到行首0（数字），移动到行首第一个字符处^

5、移动光标到下一个句子），移动光标到上一个句子（

6、移动到段首{，移动到段尾}

7、移动到下一个词w，移动到上一个词b

8、移动到文档开始gg，移动到文档结束G

9、移动到匹配的{}.().[]处%

10、跳到第n行ngg或nG或 :n

11、移动光标到屏幕顶端H，移动到屏幕中间M，移动到底部L

12、读取当前字符，并移动到本屏幕内下一次出现的地方*

13、读取当前字符，并移动到本屏幕内上一次出现的地方#

**查找替换**
1、光标向后查找关键字#或者g#

2、光标向前查找关键字或者g

3、当前行查找字符fx/Fx/tx/Tx

4、基本替换:s/s1/s2（将下一个s1替换为s2）

5、全部替换:%s/s1/s2

6、只替换当前行:s/s1/s2/g

7、替换某些行:n1,n2 s/s1/s2/g

8、搜索模式为/string，搜索下一处为n，搜索上一处为N

9、制定书签mx，但是看不到书签标记，而且只能用小写字母

10、移动到某标签处`x

11、移动到上次编辑文件的位置`.

. 代表一个任意字符
* 代表一个或多个字符的重复

**编辑操作**
1、光标后插入a, 行尾插入A

2、后插一行插入o，前插一行插入O

3、删除字符插入s， 删除正行插入S

4、光标前插入i，行首插入I

5、删除一行dd，删除后进入插入模式cc或者S

6、删除一个单词dw，删除一个单词进入插入模式cw

7、删除一个字符x或者dl，删除一个字符进入插入模式s或者cl

8、粘贴p，交换两个字符xp，交换两行ddp

9、复制y，复制一行yy

10、撤销u，重做ctrl + r，重复.

11、智能提示ctrl + n或者ctrl + p

12、删除motion跨过的字符，删除并进入插入模式c{motion}

13、删除到下一个字符跨过的字符，删除并进入插入模式，不包括x字符ctx

14、删除当前字符到下一个字符处的所有字符，并进入插入模式，包括x字符，cfx

15、删除motion跨过的字符，删除但不进入插入模式d{motion}

16、删除motion跨过的字符，删除但不进入插入模式，不包括x字符dtx

17、删除当前字符到下一个字符处的所有字符，包括x字符dfx

18、如果只是复制的情况时，将12-17条中的c或d改为y

19、删除到行尾可以使用D或C

20、拷贝当前行yy或者Y

21、删除当前字符x

22、粘贴p

23、可以使用多重剪切板，查看状态使用:reg，使用剪切板使用”，例如复制到w寄存器，”wyy或者使用可视模式v”wy

24、重复执行上一个作用使用.

25、使用数字可以跨过n个区域，如y3x，会拷贝光标到第三个x之间的区域，3j向下移动3行

26、在编写代码的时候可以使用]p粘贴，这样可以自动进行代码缩进

27、 >>缩进所有选择的代码

28、 <<反缩进所有选择的代码

29、gd移动到光标所处的函数或变量的定义处

30、K在man里搜索光标所在的词

31、合并两行J

32、若不想保存文件，而重新打开:e!

33、若想打开新文件:e filename，然后使用ctrl + ^进行文件切换

**窗口操作**
1、分隔一个窗口:split或者:vsplit

2、创建一个窗口:new或者:vnew

3、在新窗口打开文件:sf {filename}

4、关闭当前窗口:close

5、仅保留当前窗口:only

6、到左边窗口ctrl + w,h

7、到右边窗口ctrl + w,l

8、到上边窗口ctrl + w,k

9、到下边窗口ctrl + w,j

10、到顶部窗口ctrl + w,t

11、到底部窗口ctrl + w,b

**宏操作**
1、开始记录宏操作q[a-z]，按q结束，保存操作到寄存器[a-z]中

2、@[a-z]执行寄存器[a-z]中的操作

3、@@执行最近一次记录的宏操作

**可视操作**
1、进入块可视模式ctrl + v

2、进入字符可视模式v

3、进入行可视模式V

4、删除选定的块d

5、删除选定的块然后进入插入模式c

6、在选中的块同是插入相同的字符I[HTML_REMOVED]ESC

**跳到声明**
1、[[向前跳到顶格第一个{

2、[]向前跳到顶格第一个}

3、]]向后跳到顶格的第一个{

4、]]向后跳到顶格的第一个}

5、[{跳到本代码块的开头

6、]}跳到本代码块的结尾

**挂起操作**
1、挂起Vim ctrl + z或者:suspend

2、查看任务，在shell中输入jobs

3、恢复任务fg [job number]（将后台程序放到前台）或者bg [job number]（将前台程序放到后台）

4、执行shell命令:!command

5、开启shell命令:shell，退出该shell exit

6、保存vim状态:mksession name.vim

7、恢复vim状态:source name.vim

8、启动vim时恢复状态vim -S name.vim



# 3.shell语法

# 4.ssh

# 5.git

# 6.thrift

# 7.管道、环境变量与常用命令

# 8.租云服务器及配docker环境