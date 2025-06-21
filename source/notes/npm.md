---
wiki: notes # 这个跟上面的 /wiki/notes.yml 关联起来
menu_id: notes # 这个跟配置文件中的 `menubar.items.notes` 关联起来，这很重要，如果没有这个，就像普通的wiki项目一样了
title: npm 插件
# 横幅
banner: /images/covers/java1.jpg 
---

# 🌉项目工程化插件

## Prettier

{% link https://www.prettier.cn/ Prettier | 文档 icon:https://www.prettier.cn/icon.png %}

{% folding Prettier.js在项目中配置无效，如何解决？ %} 

{% box 问题描述 color:red %}

- 编译器：Cursor 0.49.6
- Prettier版本：3.0.0

项目根目录下配置的.prettierrc.js如下
```js .prettierrc.js
module.exports = {
  semi: false, // 无分号
  printWidth: 100, // 每行最多宽度
  singleQuote: true, // 单引号
  endOfLine: 'auto', // 保持现有的行尾
  importOrder: ['^@/(.*)$', '^@yige/(.*)$', '^[./]'],
  importOrderSeparation: true,
  importOrderSortSpecifiers: true,
  plugins: [
    require('@trivago/prettier-plugin-sort-imports'),
    require('prettier-plugin-tailwindcss'),
  ],
  tailwindConfig: './tailwind.config.js',
}
```

发现当格式化的时候，Prettier的控制台报错：

```shell
Prettier Error resolving prettier configuration for x:\xxx\.prettierrc.js
```

根据报错信息可以看出格式化时，配置文件确实使用的是根目录下的.prettierrc.js文件，
但是文件的配置内容似乎不对。

{% endbox %}

{% box 解决方法 color:green %}

导致Prettier格式化失效+报错，一共有两个原因：

- 原因1：**prettier版本与plugin配置的语法不匹配**

主要是其中有个配置项plugins，在prettier 3.x.x版本中和2.x.x版本中的语法是不同的，
3.x.x中，使用字符串进行定义：
```js
module.exports = {
  // ...
  plugins: ['@trivago/prettier-plugin-sort-imports', 'prettier-plugin-tailwindcss'],
}
```
2.x.x中，使用引用方式进行定义：
```js
module.exports = {
  // ...
  plugins: [
      require('@trivago/prettier-plugin-sort-imports'),
      require('prettier-plugin-tailwindcss'),
  ],
}
```

- 原因2：**{% mark .prettierrc.js %} 修改后需要重启编译器才能生效** （<a href="https://segmentfault.com/q/1010000044571262">参考来源</a>）

prettier提供很多种配置模式：
- .prettierrc.json/yaml/yml/json5/toml
- .prettierrc.js/ts/mjs/mts/cjs/cts/
- prettier.config.js/ts/mjs/mts/cjs/cts

但是不同配置文件，修改后生效的方式不同：
- _.prettierrc.json_：无需重启编译器就能重新生效
- _.prettierrc.js/cjs/mjs/ts_：必须重启编译器才能生效

这个项目的 prettier 版本是3.0.0，对应的plugins不应该使用require引入，因此导致报错，
再加上一直都没发现必须要重启编译器配置才能生效，所以一直没法解决这个问题😭
最终有2种解决方式：
- 方式1：将prettier版本退回到2.x.x版本（比如2.8.8）
- 方式2：使用字符串的方式引入plugins

{% endbox %}

{% endfolding %}
