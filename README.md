* 参考

学习 vuex 源码整体架构，打造属于自己的状态管理库 - 若川的文章 - 知乎 https://zhuanlan.zhihu.com/p/92906380



本次调试的是 vue2.6 的代码

1. 从 vue 的 repo 中 clone 对应分支代码

   ```
   git clone -b 2.6 https://github.com/vuejs/vue.git
   ```

2. 安装依赖

   ```
   cd vue
   yarn
   ```

3.  在 dist/vue.js 最后一行追加一行 `//# sourceMappingURL=vue.js.map`

4. 安装 http-server

   ```
   yarn add -D http-server
   ```

5. 生成 build 后的代码

   ```
   yarn dev
   ```

6.  在examples 文件夹中把引用的vuejs的index.html 文件 vue.min.js 改为 vue.js

7. 启动服务器（如果报错就`npx hs -p 8100`）

   ```
   hs -p 8100 
   ```

8. 浏览器打开后，输入`http://localhost:8100/examples/1120`（1120是我自建的demo目录）

9. 打开控制面板 source 在左侧找到  src 目录 即vue.js源码文件 根据自己需求断点调试即可。

10. 控制面板->Network->勾选 Disable cache，之后在IDE上修改`js/html`代码，chrome 就会同步更新了
11. 怎么`debug`呢？先加断点，再**刷新页面**，就进入`debug`环境了。



#### debug tip

* step into

  执行下一句代码

* step out

  跳到上一句代码/函数（当前函数过深时，及时跳出）

* step over

  跳过当前函数（直接跳到执行完毕处）

* 连续断点

  在 debug 环境下，如果想跳过一段代码，只看自己感兴趣的某句代码，就在那句代码前加断点，然后`resume script execution`，就会直接跳到执行该句话的地方。

* 条件断点

* 取消断点

[![DDJesO.png](https://s3.ax1x.com/2020/11/27/DDJesO.png)](https://imgchr.com/i/DDJesO)



