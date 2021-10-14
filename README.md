# Vue 3 + Typescript + Vite + element-plus 脚手架

## 多个仓库

先删除，再切换。
好吧，这样似乎不行，不纠正，过。

删除
```
git remote rm origin
```

github
```
git remote add origin git@github.com:lianmt/vue3-ts-vite-element_plus-template.git
git push -u origin master
```

gitee
```
git remote add origin git@gitee.com:lianmt/vue3-ts-vite-element_plus-template.git
git push -u origin master
```

## 功能

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