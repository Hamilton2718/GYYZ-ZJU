<!--
 * @Author: Hamilton2718 3054970772@qq.com
 * @Date: 2024-06-30 15:07:20
 * @LastEditors: Hamilton2718 3054970772@qq.com
 * @LastEditTime: 2024-07-04 14:31:50
 * @FilePath: \test_1d:\my-wiki\docs\other\mkdocs.md
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
# 发布网站
### 一、安装：
在cmd中执行
```
pip install mkdocs
```

和
```
pip install mkdocs-material
```
### 二、创建
在D盘中输入
```
mkdocs new myproject
```
这里的`myproject`是你的文件夹名字(下面都用my-wiki代替)

mkdocs.yml是你的你的配置文件，在里面修改好之后，cd my-wiki
输入
```
mkdocs serve
```
会跳出：

这个网址点进去之后可以本地预览

### 三、更改主题：
在mkdocs.yml里输入：
```
site_name: My site
site_url: https://mydomain.org/mysite
theme:
  name: material
```
再重新serve即可

### 四、部署
在github上创建仓库，权限设为public，然后依次
```
git init
git add .
git commit -m"..."
git remote add origin https://github.com/Hamilton2718/GYYZ-ZJU.git
git branch -M main
git push -u origin main 
```
然后在仓库里的settings->page把分支改为gh-pages
如下：![..](/docs/mkdocs/githubpages.png)
之后输入
```
mkdocs gh-deploy
```
点击它给你的网站就行了

### 五、problems
**1. 如果遇到`fatal: unable to access 'https://github.com/Hamilton2718/GYYZ-ZJU.git/': Recv failure: Connection was reset`的报错
输入**
```
git config --global --unset http.proxy 
git config --global --unset https.proxy
```

# 操作
### 一、多级目录
我们也可以根据需要生成多级目录，多级目录也要在 mkdocs.yml 中配置。多级目录的语法格式如下：
```
- [一级目录名称]:
    - [子目录名称]:[文件路径/文件名.md]
    ...
```
**注意：** 其中 [子目录名称] 可以省略，如果省略，那么当前页面名称即显示为该 markdown 文件的一级标题。
*实例*：
```
nav:
- Home: index.md
- User Guide:
    - Writing your docs: user-guide/writing-your-docs.md
    - Styling your docs: user-guide/styling-your-docs.md
- About:
    - License: about/license.md
    - Release Notes: about/release-notes.md
```
![运行结果](https://mkdocs-like-code.readthedocs.io/zh-cn/latest/MkDocs-advanced-operations/multi-dir.png)