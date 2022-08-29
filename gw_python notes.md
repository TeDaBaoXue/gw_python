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















































