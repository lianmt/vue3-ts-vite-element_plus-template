# Vue 3 + Typescript + Vite + element-plus 脚手架

最近尝试搭建新出的框架，分享出来。

### 安装运行

```
git clone git@github.com:lianmt/vue3-ts-vite-element_plus-template.git

cd vue3-ts-vite-element_plus-template

cnpm i

npm run dev
```

gitee 仓库
```
git@gitee.com:lianmt/vue3-ts-vite-element_plus-template.git
```

### 功能

css 预处理器

 Vite 也同时提供了对 .scss, .sass, .less, .styl 和 .stylus 文件的内置支持。没有必要为它们安装特定的 Vite 插件，但必须安装相应的预处理器依赖：

 ```
# .scss and .sass
npm install -D sass

# .less
npm install -D less

# .styl and .stylus
npm install -D stylus
```

### 多个仓库

先删除远程，再切换。

好吧，这样似乎不行。

发现，gitee 可以直接导入 github 仓库，添加仓库时有这个选项。

gitee 还有同步代码的功能。在仓库名称右侧，点击刷新按钮即可。

### 踩坑

1、

安装 element-plus，官网安装 `unplugin-vue-components` 走不通，各种版本依赖问题，弃坑。

后面发现一个优雅的方案，引入两个插件，自行按需导入使用的组件，`vite-plugin-style-import` 和 `vite-plugin-components`。

vite.config.ts 配置

```
import styleImport from 'vite-plugin-style-import'
import ViteComponents, { ElementPlusResolver } from 'vite-plugin-components'

plugins: [
  ViteComponents({
    customComponentResolvers: [ElementPlusResolver()],
  }),
  //按需导入element-plus的css样式
  styleImport({
    libs: [
      {
        libraryName: 'element-plus',
        esModule: true,
        // 注意，不是引用 lib/theme-chalk 目录，其实在对应 element-plus 里找不到，直接放在外面了
        resolveStyle: (name) => {
          return `element-plus/theme-chalk/${name}.css`
        },
      },
    ],
  }),
],
```

### 我的账号

Github：[github.com/lianmt](https://github.com/lianmt)
Gitee：[gitee.com/lianmt](https://gitee.com/lianmt)
