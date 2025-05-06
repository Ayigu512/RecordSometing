# Vite配置路径别名

1、通过Vite脚手架初始化项目文件

`pnpm create vite`

一路回车完成安装

2、安装node类型声明文件

`pnpm i -D @types/node`

3、配置vite.config.js文件

```js
import { resolve } from 'path'

export default defineConfig({

  plugins: [react()],

  resolve: {

​    alias: {

​      "@": resolve(__dirname, './src/')

​    }

  }

})
```

4、配置tsconfig.json，在compilerOptions节点新增`"baseUrl": "."`和`"paths": { "@/*": ["src/*"]}`两项：

```json
{
	"compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  }
}
```

<!--如果提示没有生效，请在tsconfig.app.json中将上述两项添加上-->