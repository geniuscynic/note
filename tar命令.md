#tar 解压缩命令详解
- 以下是对tar命令的一些总结：
```
1. tar -cvf test.tar test 仅打包，不压缩 
2. tar -zcvf test.tar.gz test 打包后，以gzip压缩 在参数f后面的压缩文件名是自己取的，习惯上用tar来做，如果加z参数，
3. 则以tar.gz 或tgz来代表gzip压缩过的tar file文件
```

- 解压操作
```
1 #tar -zxvf /usr/local/test.tar.gz
```

- tar 解压缩命令详解
```
1 -c: 建立压缩档案
2 -x：解压
3 -t：查看内容
4 -r：向压缩归档文件末尾追加文件
5 -u：更新原压缩包中的文件
```

- 这五个是独立的命令，压缩解压都要用到其中一个，可以和别的命令连用但只能用其中一个。下面的参数是根据需要在压缩或解压档案时可选的。
```
1 -z：有gzip属性的
2 -j：有bz2属性的
3 -J：具有xz属性的（注3）
4 -Z：有compress属性的
5 -v：显示所有过程
6 -O：将文件解开到标准输出
```

- 下面的参数-f是必须的 
-f: 使用档案名字，切记，这个参数是最后一个参数，后面只能接档案名。
```
1 # tar -cf all.tar *.jpg 
2 
3 # tar -rf all.tar *.gif 
```
```
1 这条命令是将所有.gif的文件增加到all.tar的包里面去。-r是表示增加文件的意思。
2 
3 # tar -uf all.tar logo.gif 
4 
5 
6 
7 这条命令是更新原来tar包all.tar中logo.gif文件，-u是表示更新文件的意思。
8 
9 # tar -tf all.tar 
```
```
 1 这条命令是列出all.tar包中所有文件，-t是列出文件的意思
 2 
 3 # tar -xf all.tar 
 4 这条命令是解出all.tar包中所有文件，-x是解开的意思
 5 
 6 压缩
 7 
 8 tar –cvf jpg.tar *.jpg //将目录里所有jpg文件打包成tar.jpg
 9 tar –czf jpg.tar.gz *.jpg //将目录里所有jpg文件打包成jpg.tar后，并且将其用gzip压缩，生成一个gzip压缩过的包，命名为jpg.tar.gz
10 tar –cjf jpg.tar.bz2 *.jpg //将目录里所有jpg文件打包成jpg.tar后，并且将其用bzip2压缩，生成一个bzip2压缩过的包，命名为jpg.tar.bz2
11 tar –cZf jpg.tar.Z *.jpg //将目录里所有jpg文件打包成jpg.tar后，并且将其用compress压缩，生成一个umcompress压缩过的包，命名为jpg.tar.Z
12 rar a jpg.rar *.jpg //rar格式的压缩，需要先下载rar for linux
13 zip jpg.zip *.jpg //zip格式的压缩，需要先下载zip for linux
14 
15 
16 解压
17 
18 tar –xvf file.tar //解压 tar包
19 tar -xzvf file.tar.gz //解压tar.gz
20 tar -xjvf file.tar.bz2   //解压 tar.bz2
21 tar –xZvf file.tar.Z   //解压tar.Z
22 unrar e file.rar //解压rar
23 unzip file.zip //解压zip
```
- **总结**
```
(1) *.tar 用 tar –xvf 解压
(2) *.gz 用 gzip -d或者gunzip 解压
(3) *.tar.gz和*.tgz 用 tar –xzf 解压
(4) *.bz2 用 bzip2 -d或者用bunzip2 解压
(5) *.tar.bz2用tar –xjf 解压
(6) *.Z 用 uncompress 解压
(7) *.tar.Z 用tar –xZf 解压
(8) *.rar 用 unrar e解压
(9) *.zip 用 unzip 解压
(10) *.xz 用 xz -d 解压
(11) *.tar.xz 用 tar -zJf 解压
```
