# os

### 在python中执行shell脚本

---



* `os.system("cmd")`

  ```python
  import os 
  print(os.system("touch aaa.txt"))
  # os.system("") 返回0 表执行成功
  ```

* `os.popen("cmd")`

  ```python
  # os.popen("cmd") 返回一个文件对象，可查看执行的输出
  f = os.popen("ls -l)
  print(f.read())
  ```

* `subprocess`  模块

  >subprocess模块是python从2.4版本开始引入的模块，也是系统自带的，不需要再额外安装了。主要用来取代 一些旧的模块方法，如os.system、os.spawn*、os.popen*、commands.*等。subprocess通过子进程来执行外部指令，并通过input/output/error管道，获取子进程的执行的返回信息。

  ```python
  subprocess.call()
  subprocess.check_call()
  
  import subprocess.popen()
  ```

* `pip install sh`  [sh 库](http://amoffat.github.io/sh/)

  ```python
  import sh 
  sh.pwd()
  sh.mkdir(aaa)
  sh.whoami
  sh.df("-h")
  sh.du("-h", "-d 1")
  ```

  

