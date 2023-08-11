# vue项目中配置本地跨域调试接口

```javascript
// vue.config.js
module.exports = {
    ...
    devServer: {
        proxy: {
      
            // 1. 用通配符(*)可以将所有接口代理到配置的 target
            '*': {
                target: 'http://192.168.xx.xx:xxxx', //服务器api地址
                changeOrigin: true, //是否跨域
            },
            // 2. 可以匹配以 '/api' 标识开头的接口, 对这部分接口进行代理
            //    若去掉 '^' 则会匹配所有 存在 '/api' 标识的接口
            '^/api': {
                target: 'http://192.168.xx.xx:xxxx', // 调试服务器api地址
                changeOrigin: true,
                pathRewrite: {
                    // 重写路径, 修正接口, 移除开头的 '/api' 标识
                    '^/api': '',
                },
            },
        }
    }
}
```
