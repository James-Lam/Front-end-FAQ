## VS code go to definition not working with imports using webpack's alias
- You need to setup path-mapping in jsconfig.json or tsconfig.json, for example:
  ```
  // Webpack
  module.exports = {
    resolve: {
        alias: {
        '@': 'src'
      }
    }
  }
  ```
  ```
    // jsconfig.json
  {
    "compilerOptions": {
      "baseUrl": ".",
      "module": "commonjs",
     "paths": {
       "@/*": ["src/*"]
      }
    }
  }
  ```
  __NOTE: After completing the above configuration, you must relaunch VS code! I wasted hours on configuration before I found out that it was correct for the first time.__

## 开发Vue.js项目，打开devtools会导致页面卡顿并且内存占用过高
- 关闭vuex recording即可解决问题，[更多内容](https://github.com/vuejs/vue-devtools/issues/539#issuecomment-359361573)

## vs code插件vetur无法跳转到定义处(go to definition)
- 拓展名不能忽略，如果引入组件的话`import { BaseComponent } from "@/path/to/BaseComponrnt"`，必须写成`import { BaseComponent } from "@/path/to/BaseComponrnt.vue"`，[更多内容](https://github.com/vuejs/vetur/issues/423#issuecomment-340235722)
