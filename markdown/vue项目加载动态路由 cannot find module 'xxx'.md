# vue项目加载动态路由 cannot find module 'xxx'
原因：webpack 编译es6 动态引入 import() 时不能传入变量，因此webpack目前不能做到完全的动态加载路由
```javascript
  temp.component = () => import(menu.menuVueComponent) // 不能加载
  temp.component = () => import(`${menu.menuVueComponent}`) // 不能加载
  temp.component = () => import(`@/${menu.menuVueComponent}`) // sass报错
  temp.component = () => import(`@/views/${menu.menuVueComponent}`) // 正确
```
