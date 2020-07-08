



# shell-终端命令



### 库的分析：

* nm
* file
* objdump
* readelf
* c++filt
* ldd



### 性能分析：

* top/htop

* perf
* mtrace











# shell

---

>* [shell/c语言中文网](http://c.biancheng.net/shell/)

### 字符串操作：

* 截取

  ```shell
  web="http://google.com/hello_shell"
  
  a1=${web#*/}
  a2=${web##*/}
  left=${web%shell}
  ```

  | 格式                       | 说明                                                         |
  | -------------------------- | ------------------------------------------------------------ |
  | ${string: start :length}   | 从 string 字符串的左边第 start 个字符开始，向右截取 length 个字符。 |
  | ${string: start}           | 从 string 字符串的左边第 start 个字符开始截取，直到最后。    |
  | ${string: 0-start :length} | 从 string 字符串的右边第 start 个字符开始，向右截取 length 个字符。 |
  | ${string: 0-start}         | 从 string 字符串的右边第 start 个字符开始截取，直到最后。    |
  | ${string#*chars}           | 从 string 字符串第一次出现 *chars 的位置开始，截取 *chars 右边的所有字符。 |
  | ${string##*chars}          | 从 string 字符串最后一次出现 *chars 的位置开始，截取 *chars 右边的所有字符。 |
  | ${string%*chars}           | 从 string 字符串第一次出现 *chars 的位置开始，截取 *chars 左边的所有字符。 |
  | ${string%%*chars}          | 从 string 字符串最后一次出现 *chars 的位置开始，截取 *chars 左边的所有字符。 |

