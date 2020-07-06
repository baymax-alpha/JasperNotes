# MainPage Tools

---

[Ros melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)

[docker installation](https://stackoverflow.com/questions/30379381/docker-command-not-found-even-though-installed-with-apt-get)

```sh
$ sudo curl -sSL https://get.docker.com/ | sh
  sudo usermod -aG docker jasper
  logout 
  
  docker: Error response from daemon: Unknown runtime specified nvidia.
  $ sudo apt install -y nvidia-docker2 //
  $ sudo systemctl daemon-reload      
  $ sudo systemctl restart docker                       
```

[nvidia-docker2: Add_keys](https://nvidia.github.io/nvidia-docker/)

## 养成记

--------



### Shell 养成

[linux命令 — lsof 查看进程打开那些文件 或者 查看文件给那个进程使用](https://www.cnblogs.com/bonelee/p/7735479.html)

### Vscode养成：

1. 安装 vscode-remote

   https://code.visualstudio.com/docs/remote/ssh



## Tools:TinyProject



* [undone]C++函数trace

  [A function (graph) tracer for C/C++ userspace programs](https://uftrace.github.io/slide/#1)



* 实现文档管理： 

  [done]sphinx+readthedocs+git :  [Personal Blog|使用ReadtheDocs托管文档](https://www.xncoding.com/2017/01/22/fullstack/readthedoc.html)  

  [wiki|ReadtheDocs](https://docs.readthedocs.io/en/stable/index.html)

  [rst仿写](https://raw.githubusercontent.com/readthedocs/readthedocs.org/master/docs/index.rst)

  [wiki| sphinx](http://azuwis.github.io/sphinx_demo/)

  ```shell
  #step1: 安装 sphinx
  
  #step2: 更改配置 conf.py index.rst 笔记
  
  #step3: Upload Git respo
  
  #step4: inport project and build on ReadtheDocs
  ```

  

* [undone]实现两个文件夹自动同步：

  `[undone]inotify + rsync`  

* ###### [undone]配置AWS云计算平台

  [github|code_of_learn_deep_learning_with_pytorch](https://github.com/L1aoXingyu/code-of-learn-deep-learning-with-pytorch/blob/master/aws.md)





Mac清单： 

* terminal(pro.terminal), brew, oh_my_zsh, [spf-13/vim](https://github.com/spf13/spf13-vim)

* vscode， typora(github.user.css)， onenote ， 网易云

* 让终端走代理的几种方式：[hhh](https://zhuanlan.zhihu.com/p/46973701)

  ```sh
  export http_proxy="socks5://127.0.0.1:1086"
  export https_proxy="socks5://127.0.0.1:1086"
  export ALL_PROXY=socks5://127.0.0.1:1086
  #set alias
  alias setproxy="export ALL_PROXY=socks5://127.0.0.1:1086" alias unsetproxy="unset ALL_PROXY"
  
  #change apt config to use proxy
  sudo vim /etc/apt/apt.conf
  Acquire::http::Proxy "http://proxyAddress:port"
  
  #change git config to use proxy 
  git config --global http.proxy 'socks5://127.0.0.1:1080' 
  git config --global https.proxy 'socks5://127.0.0.1:1080'
  
  ```


* 