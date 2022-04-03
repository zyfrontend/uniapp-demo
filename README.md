# uniapp demo

# 环境信息

全局需要安装vue-cli，而且版本不能太高，不然运行时会报错，具体错误请看下面的疑难杂症

```shell
npm install -g @vue/cli@4
```
# 我安装的vue-cli版本

![](http://image.zyfullstack.top/20220403111758.png)

# 使用本项目
```shell
git clone https://github.com/zyfrontend/uniapp-demo.git

cd uniapp-demo
# 安装依赖
npm install
# 运行
npm run serve
# 编译 H5 其他请看 package.json 文件
npm run build
```

# 命令行创建和`Hbuilder` 创建的 `uniapp` 项目的区别
- 命令行创建的 `uniapp` 项目的目录
![](http://image.zyfullstack.top/20220403113627.png)
- `Hbuilder` 创建的 `uniapp` 项目的目录
![](http://image.zyfullstack.top/20220403113753.png)

### 好处
- 方便了之后直接做自动化部署,直接git提交代码就好了
- 由于个人原因，觉得`Hbuilder`用不习惯


# 命令行创建项目

```shell
# 正式版
vue create -p dcloudio/uni-preset-vue my-project

# alpha版
vue create -p dcloudio/uni-preset-vue#alpha my-alpha-project

# Vue3 Vite版
npx degit dcloudio/uni-preset-vue#vite my-vue3-project

# TS Vue3 Vite版
npx degit dcloudio/uni-preset-vue#vite-ts my-vue3-project
```
# 项目运行方式

和普通vue项目一样`package.json`文件里面有详细的配置

- h5

运行
```shell
yarn serve 
# 或者
npm run serve
```
编译
```shell
yarn build 
# 或者
npm run build
```

# 项目配置

### Hbuilder 的图形化配置文件所在
> 下面图片这个图形化配置就是 `manifest.json` 文件了，如果不使用 `Hbuilder` 的话，直接在这配置就好了

![](http://image.zyfullstack.top/20220403113332.png)

### 使用命令行创建的项目直接去配置`manifest.json`就好了

# 一些疑难杂症

#### 1.vscode 中编写 `uniapp` 命令行创建的代码，可能会有下面的问题

![](http://image.zyfullstack.top/20220403112436.png)

- 解决方案

```json
{
  "compilerOptions": {
    "allowJs": true, // 添加这个就好了
    "types": [
      "@dcloudio/types",
      "miniprogram-api-typings",
      "mini-types"
    ]
  }
}
```

- 为什么会这样

> 应该是因为在vue项目中使用了 `typescript`模板的问题.(查到的答案)



#### 2.环境造成的运行不成功问题

- 如果`vue-cli`的版本过高会在运行的时候出现下面这个报错信息

```shell
Cannot find module 'webpack/lib/RuleSet'
```

- 解决方案

降低全局安装的 `vue-cli`版本

```shell
# 卸载原有的 vue-cli
npm uninstall -g @vue/cli
# 安装旧版本的
npm install -g @vue/cli@4
```



# 关于sass

命令行创建的`uniapp`项目需要自行手动安装sass

```shell
npm install --save-dev sass sass-loader
npm install --save uview-ui
```

