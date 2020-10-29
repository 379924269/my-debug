## 我的docker学习笔记
docker核心：镜像、容器、库
### 学习
#### 我参考的书籍
《docker技术入门和实战》
### 我遇到的问题
#### 库上传不了镜像
- 库1.3以后要求安全，配置一下就可以了。[参考](https://blog.csdn.net/caohongshuang/article/details/85320939)
- 没启动库镜像，所以上传不了，启动库 docker run -d -p 5000:5000 registry:2

### Java开发提升十倍生产力:Idea远程一键部署springboot到Docker
[参考地址](https://juejin.im/post/6844903865192562696)