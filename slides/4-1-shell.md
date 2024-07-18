class: middle, center

# 命令行工具

---
# 文件系列命令

- ls：列出目录下文件
- cd：进入目录
- pwd：显示当前目录
- find: 迭代访问目录下所有目录和文件
- grep: 搜索文件内容
- cp：copy 复制
- rm：remove 删除
- unzip：解压 zip 文件

---
# 语法

command -options arg1 arg2

例

      ls -l -h figures/
      ls -lh figures/
- options，可以组合
   -  -l 提供有关每个文件的额外信息
   -  -h 以更易于理解的格式提供文件大小
- Jupyter里，用 ！（感叹号）运行 Shell 命令

---
# 查看文件大小

      wc data/DAWN-Data.txt

      229211 22695570 280095842 data/DAWN-Data.txt
      行数 单词数 字符数

---
# 查看磁盘使用

disk usage

      du -Lsh data/*

      267M	data/DAWN-Data.txt
      648K	data/businesses.csv
-s 显示文件和文件夹大小

-h 以标准 KiB、MiB 或 GiB 格式显示大小

---
# head

显示文件开头的几行

    head -4 data/inspections.csv
    head -n 4 data/inspections.csv
默认显示 10 行

---
# cat 

打印整个文件

大文件会导致系统崩溃哦

最好用 head 或者 tail

---
# file 得到文件编码

      file -I data/*

      data/DAWN-Data.txt:   text/plain; charset=us-ascii
      data/businesses.csv:  application/csv; 
                                charset=iso-8859-1

---
class: middle, center

# vi 文本编辑

---
# vi 三种状态

- 命令
- 插入
- 底行命令

---
class: middle, center
# 课后练习

---
# 课后练习

进入 https://www.marscode.cn/dashboard

启动项目，进入 Terminal，练习 ls、wc、du、head、tail、cat、file 等命令

练习 vi

---
# 课后练习

- 打开 [Linux 命令参考表](https://www.jianshu.com/p/2c40cf0f9f9e)，练习里面提到的命令，不理解之处，咨询 AI。