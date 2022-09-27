### singularity run cpp application

演示如何将一个 CPP 应用发布打包成为一个容器，
singularity 其本质是一个先进的发布方式，帮助解决并行计算环境隔离问题

_优势_：

- 无系统依赖，无 GCC 版本依赖，不会污染宿主机的运行环境
- 运行方便，和命令行运行完全一致
- 支持 HPC MPI 并行计算

##### 1 singularity 容器命令行安装

详细见官方文档

编译安装（推荐）：

https://docs.sylabs.io/guides/3.10/user-guide/quick_start.html

其他二进制安装包 :

https://github.com/sylabs/singularity/releases

##### 2 打包 singularity 镜像

通过 def 文件生成 sif 文件

```bash
$ sudo singularity build cppdemo.sif cppdemo.def
```

##### 3 运行镜像

运行 sif 文件，和直接运行 cppdemo 完全一致

```bash
$ singularity run cppdemo.sif 9 16
sqrt(9.000000) + sqrt(16.000000) = 7.000000
```
