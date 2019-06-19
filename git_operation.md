# Windows下生成ssh
### 查看是否有ssh key存在
    ls -al ~/.ssh
### 创建一个SSH key
    ssh-keygen -t rsa -C "zhangsaiyx@163.com"
### 测试一下该SSH key
    ssh -T git@github.com
![测试结果](image/001_测试SSH_key.PNG "测试结果")