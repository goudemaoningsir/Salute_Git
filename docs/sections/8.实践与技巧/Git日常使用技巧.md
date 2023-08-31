# Git日常使用技巧

## 给git clone提提速

国内使用 Git Clone 的速度问题。有时候因为网络的问题，克隆一个 GitHub 项目可能要花费很长时间，这对于开发者来说无疑是一种痛苦。下面介绍几种git clone加速的方法。



### 使用码云 Gitee

[码云 Gitee](https://gitee.com/) 是一个基于 Git 的代码托管平台，它在国内访问速度相当快。我们可以利用码云做一次中转，从而加速 Git Clone。

- 首先，登录或注册一个码云账号，然后在码云上创建一个新的仓库。
- 然后，点击 "从 GitHub/GitLab 导入仓库"，将 GitHub 项目导入到新创建的码云仓库中。
- 最后，直接克隆这个码云仓库到本地，速度会有显著提升。



### 使用国内镜像

有一些公司或组织提供了 GitHub 的镜像服务，我们也可以使用这些镜像来加速 Git Clone。例如：

- [FastGit](https://hub.fastgit.org/)

  

只需要把克隆命令中的 github.com 替换成对应的镜像网址即可。

比如原本的克隆命令是：

```bash
git clone https://github.com/username/repo.git
```

使用 FastGit 镜像后，命令变为：

```bash
git clone https://hub.fastgit.org/username/repo.git
```

### 使用 SSH 代理

如果你有一个稳定的代理服务器，也可以通过设置 Git 的 SSH 代理来加速 Clone。首先，需要在 ~/.ssh/config 文件中添加如下配置：

```text
Host github.com
  User git
  ProxyCommand nc -x localhost:1080 %h %p
```

这里的 localhost:1080 是你的本地代理服务器地址和端口，需要替换为实际的值。然后就可以直接使用 SSH 方式克隆 GitHub 项目了，速度会得到一定提升。