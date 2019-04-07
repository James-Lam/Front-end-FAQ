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
