# Linux常用命令--基本文件管理（上）

文件/文件夹是我们最经常打交道的对象，也是存放、管理数据重要工具。最基本的文件/文件夹无外乎增、删、查、改，接下来介绍常用的命令。

## 1.创建

创建文件夹

`mkdir [-p|-m] dirName`

- p：若要创建的目录的上级目录不存在，则一并创建上级目录；

- m：设置目录的权限；

- dirName：目录名，多个则用空格隔开；

- 例子： 在home文件夹下创建abc文件夹，并且给与abc文件夹可读、可写、可执行权限  `mkdir -p -m 777 /home/abc`


  

创建文件

`touch fileName`

- fileName：文件名，多个则用空格隔开；
- 例子：创建空文件a.txt和b.txt  `touch a.txt b.txt`

  

## 2.删除

删除文件/文件夹

`rm [-i|-f|-r] name `

- i：交互方式，删除前询问确认；
- f：强制删除；
- r：递归处理，删除目录的时候需要，表示删除目录及目录以下的文件；
- name：删除文件/目录名，多个则用空格隔开；
- 例子： 强制删除当前目录下的所有文件或文件夹 `rm -rf ./*` （注意这个命令很危险）

  

## 3.查找

显示指定文件夹下的内容

`ls [-a|-l|-r|-t|R] [name]`

- a：显示所有文件及文件夹；
- l：显示文件权限、拥有者等详细信息；
- r：英文字母逆序排列；
- t：按照文件创建时间排序；
- R：递归展示文件夹下的文件/文件夹；
- name：指定的文件/文件夹
- 例子：递归的、详细的显示home文件夹下的内容，并且按照首字母逆序排序 `ls -lrR /home`/

  

指定目录下查找文件。这个命令功能比较复杂和强大，在另一个文档里详细描述。

`find`

  

## 4.移动

移动文件/文件夹。

`mv [-i|-f] source target`

- i：交互提醒，文件同名时询问是否覆盖；
- f：强制覆盖，遇到同名时直接覆盖，不给与提示；
- source：想要移动的文件/文件夹；
- target：想要移动到的文件夹；
- 例子：把test.txt移动到/home/b下面  `mv -i test.txt /home/b`

  

## 5.改名

通过移动实现文件改名

`mv fileA fileB  `

- fileA：改名前的文件；
- fileB：改名后的文件；

- 例子：将文件aaa更名为bbb `mv a.txt b.txt`

  

为文件/文件夹建立同步链接，管理大数据文件时候常用。

`ln [-s|-n|-i|-f] sourceFile/sourceDir targetFile/targetDir`

- s：软连接，相当于windows上的快捷方式。如果sourceFile/sourceDir删除了，那么targetFile/targetDir失效；
- n：硬链接，删除source不会影响target；
- i：交互模型，文件存在是询问是否覆盖；
- f：强制执行覆盖；
- 例子：为文件log123.log创建一个软链接log123lnk `ln -s log123.log log123lnk`



