---
title: Github静态站点子路径部署项目
---

### github站点包含多个子项目

> 希望通过github部署的个人站点，能够支持不同目录访问到不同的项目。
> 例如: https://tang-jianchao.github.io/ 首页
> https://tang-jianchao.github.io/blog/ 博客
> https://tang-jianchao.github.io/projectA 项目A
> https://tang-jianchao.github.io/projectB 项目B

1. ### xxx.github.io 根路径

   https://github.com/Tang-jianchao/Tang-jianchao.github.io 仓库中仅仅保留一个index.html文件用于  https://tang-jianchao.github.io/  根路径访问 展示。

   

2. ### blog子路径

   新建一个用于存放blog静态文件的仓库 https://github.com/Tang-jianchao/blog 

   在hexo搭建的博客项目中, 修改  _config.yml 文件中的内容:

   ```xml
   # URL
   # 这里的url是要访问blog的地址
   url: https://tang-jianchao.github.io/blog 
   # 这里需要设置hexo的根路径 构建之后 项目引用的资源才能正确找到
   root: /blog/
   permalink: :year/:month/:day/:title
   
   ......
   
   deploy:
     type: git
   	# 这里把 npm run deploy 命令一键部署的仓库设置为上面创建用来存放blog的仓库
     repo: https://github.com/Tang-jianchao/blog.git #https://bitbucket.org/JohnSmith/johnsmith.bitbucket.io
     branch: main
     message: init
   ```

   这一步很重要!!!  *其他路径的仓库也需要开启才能正确访问到* 

   **blog- setting - pages**  设置 **github Page** 选择当前的分支  **Save**

   ![image-20220401153559499](/Users/admin/Library/Application Support/typora-user-images/image-20220401153559499.png)

   验证: https://github.com/Tang-jianchao/blog 

3. Project

   







### blog   一键部署  安装插件 推送的repo为站点的子目录





project

静态资源public 设置