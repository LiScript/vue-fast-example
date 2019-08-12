[ 开发规范 ](./README.Poli.md)
## fast-vue
- 前后端分离，通过token进行数据交互，可独立部署
- 主题定制，通过scss变量统一一站式定制
- 动态菜单，通过菜单管理统一管理访问路由
- 数据切换，通过mock配置对接口数据／mock模拟数据进行切换
- 发布时，可动态配置CDN静态资源／切换新旧版本
## 关闭本地mock（数据交互）
- src/mock/index.js 文件  将fnCreate的isOpen参数设置为false（关闭）
- config/index.js 文件  target转发代理设置为服务地址
## 配置后台访问地址（数据交互）
- static/config/ 文件夹下面的不同文件中的 window.SITE_CONFIG['baseUrl']  参数
## 配置后台token验证（数据交互）
- src/utils/httpRequest 文件下面的 请求拦截里面的 config.headers