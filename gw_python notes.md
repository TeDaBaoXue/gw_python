# gw_python notes

## 配置python和pycharm

我以前不经意间已经配置python3.8了，现在用的是python3.10。

一开始遇到小插曲，我删了3.8下载3.10之后我安装pycharm，但是我的pycharm显示无法连接至python3.8，弄得我莫名其妙。后来我把`Python interpreter`里改成了`Project Default (Python 3.10 (gw_python)) ~/Desktop/Personal_Workspace/Study/CS Tool/gw_python/venv/bin/python`，就稀里糊涂地解决了😄。

`Jet Brains`出品，必为精品！总的来说配置不麻烦！

### Pycharm初始代码

Pycharm默认的`main.py`是：

```py
# This is a sample Python script.

# Press ⌃R to execute it or replace it with your code.
# Press Double ⇧ to search everywhere for classes, files, tool windows, actions, and settings.


def print_hi(name):
    # Use a breakpoint in the code line below to debug your script.
    print(f'Hi, {name}')  # Press ⌘F8 to toggle the breakpoint.


# Press the green button in the gutter to run the script.
if __name__ == '__main__':
    print_hi('PyCharm')

# See PyCharm help at https://www.jetbrains.com/help/pycharm/
```

```
Hi, PyCharm

```

凭借学过C语言的直觉，我感觉`print_hi`是一个函数。`'PyCharm'`用来填充`{name}`。

### My first python file

```py
print("Hello world!\nHaHa!\tFinally I get to use python!\n想不到和C语言相通挺多，而且竟然在输出的末尾会自动换行")
```

```
Hello world!
HaHa!	Finally I get to use python!
想不到和C语言相通挺多，而且竟然在输出的末尾会自动换行

```



## python初探

### 郭炜python课任务分析

| 内容                             | 时长             |
| -------------------------------- | ---------------- |
| python初探                       | 1h27min          |
| 基本运算、条件分支和输出格式控制 | 1h28min          |
| 循环语句                         | 1h28min          |
| 函数和递归                       | 1h28min          |
| 字符串和元组                     | 1h34min          |
| 列表                             | 1h34min          |
| 字典和集合                       | 56min            |
| 文件读写和文件夹操作和数据库     | 1h44min          |
| ★正则表达式                      | 1h46min          |
| 玩转Python生态                   | 1h34min          |
| 数据分析和展示                   | 1h26min          |
| 面向对象程序设计                 | 1h5min           |
| ★网络爬虫设计                    | 2h2min           |
| ★tkinter图形界面程序设计         | 1h45min          |
| 总时长                           | 1h33min*14=21.7h |

> 我应该会在学习这门课上花130～220h，大概是视频时间的6～10倍，不知最糟的情况是否会更糟。
>
> 每周花15h学习比较合适，平均每天2h+，争取在14周内学完。确保每天解决的视频时长达到13min。



### Python语言的基本要素

#### 符号和注释

* 符号

  * 只有字符串和注释内才可以出现中文全角字符，其他情况下都必须使用半角字符。

* 注释

  * 单行注释，用`#`开头

    ```py
    print("Oh,yes sir♂︎") # ♂Ah♂
    ```

  * 多行注释

    * 把很多行代码变成注释：`command`+`/`

      * ```py
        # print("Oh,yes sir♂︎")
        # print("Ah♂︎that's good♂︎")
        print("顺便验证print语句是否会自动换行")
        print("如果我再换行一次，那么会不会留下两行空行呢？\n")
        print("----------")
        ```

      * ```
        顺便验证print语句是否会自动换行
        如果我再换行一次，那么会不会留下两行空行呢？
        
        ----------
        
        ```

        * 顺便验证了python每个语句是否会自动换行,且加上`\n`并不会换2行，因此`\n`在末尾几乎无效果

    * 类似C语言`/*...*/`的操作:`'''....'''`或`"""..."""`

      * ```py
        print("如果我再换行一次，那么会不会留下两行空行呢？\n")'''感觉python包办的内容也过多了'''
        ```

      * ```
        Error:End of statement expected
        ```

        * 看来多行注释不能跟在一个句子末尾

          > 这是python便利的代价，C语言每个语句后面都有`;`，所以语句后面加上`//`或者`/*...*/`就没有关系。

      * ```py
        print("顺便验证print语句是否会自动换行")
        print("如果我再换行一次，那么会不会留下两行空行呢？\n")
        '''感觉python包办的内容也过多了
               　   ▃▆█▇▄▖
        　 　 　 ▟◤▖　　　◥█▎
           　 ◢◤　 ▐　　　 　▐▉
        　 ▗◤　　　▂　▗▖　　▕█▎
        　◤　▗▅▖◥▄　▀◣　　█▊
        ▐　▕▎◥▖◣◤　　　　◢██
        █◣　◥▅█▀　　　　▐██◤
        ▐█▙▂　　     　◢██◤
        ◥██◣　　　　◢▄◤
         　　▀██▅▇▀
        
        '''
        print("----------")
        ```

        * 独立的、不杂糅的多行注释没毛病

      * 但是像C语言一样与代码杂糅的注释是不可行的

        * ```py
          print("顺便验证print语句是否会自动换行")
          '''感觉python包办的内容也过多了
                 　  　▃▆█▇▄▖
          　 　 　 ▟◤▖　　　◥█▎
             　 ◢◤　 ▐　　　 　▐▉
          　 ▗◤　　　▂　▗▖　　▕█▎
          　◤　▗▅▖◥▄　▀◣　　█▊
          ▐　▕▎◥▖◣◤　　　　◢██
          █◣　◥▅█▀　　　　▐██◤
          ▐█▙▂　　     　◢██◤
          ◥██◣　　　　◢▄◤
           　　▀██▅▇▀
          
          '''print("如果我再换行一次，那么会不会留下两行空行呢？\n")
          print("----------")
          ```

        * ```
          在倒数第二行的print前面出现：
          Error:End of statement expected
          ```



#### 变量

##### 先感受一波

```py
a=114514
b=1919810
print(a+b)
a="Oh♂︎Yeah"
print(a)
print("感觉python对变量的处理真的非常灵活啊")
```

```
2034324
Oh♂︎Yeah
感觉python对变量的处理真的非常灵活啊

```

> 显然`print(a+b)`中`a`和`b`得是同一数据类型，这我已经实验过了。



##### 变量的命名方法

1. 由字母、数字、下划线组成

   1. 中间不能有空格
   2. 不能以数字开头

2. 变量名最好能体现变量的含义

   > gw认为多单词的变量名，最好第一个单词首字母小写，后面几个单词首字母大写。这似乎是公认的好习惯。

3. 大小写是相关的（人话：大小写有区别

4. python有保留字，不能用作变量名



#### 赋值语句

```py
a = 11
b = "Ah"
print("a=", a, "b=", b)
print("赋值语句就是 `变量 = 表达式`，这个表达式可以是数字、变量、字符串")
a, b = b, a
print("a=", a, "b=", b, "a和b是不同的数据类型，但是他们竟然可以互换存储对象！")
b = a
print("如果我需要输出不同数据类型的变量，我只需要用英文逗号隔开,最终效果是中间隔了一个空格")
print("类似 `a,b,c=c,a,a` 的赋值语句也是可以的，对应地更改数值,而且并不会从左到右有一个先后顺序")
c = 114514
a = 1919
b = 810
a, b, c = c, a, a
print(a, b, c)
```

```markdown
a= 11 b= Ah
赋值语句就是 `变量 = 表达式`，这个表达式可以是数字、变量、字符串
a= Ah b= 11 a和b是不同的数据类型，但是他们竟然可以互换存储对象！
如果我需要输出不同数据类型的变量，我只需要用英文逗号隔开,最终效果是中间隔了一个空格
类似 `a,b,c=c,a,a` 的赋值语句也是可以的，对应地更改数值,而且并不会从左到右有一个先后顺序
114514 1919 1919

```



> 此外有一些细节：
>
> * pycharm喜欢赋值符号旁边有空格，可以通过`⌥`+`⌘`+`L`实现
> * 每行代码开头不能有空格





















## 基本运算、条件分支和输出格式控制



















## 循环语句















## 函数和递归

















## 字符串和元组



















## 列表



















## 字典和集合



















## 文件读写和文件夹操作和数据库

















## ★正则表达式











## 玩转Python生态













## 数据分析和展示













## 面向对象程序设计













## ★网络爬虫设计













## ★tkinter图形界面程序设计









