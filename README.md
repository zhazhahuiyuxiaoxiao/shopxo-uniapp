## 个人维护入口（2026-10-29）

本仓是 `gongfuxiang/shopxo-uniapp` 的个人副本，保留 ShopXO 上游署名、说明与 `LICENSE`。本仓承载 uni-app 移动端页面和组件，业务数据由对应 ShopXO 服务端提供；不能将本仓单独运行等同于完整商城上线或个人原创开发。

当前能力、启动条件和验证边界以 [工程基线](docs/engineering-baseline.md) 为准。后文保留原有项目介绍和上游署名；其中宣传性描述不代表本副本已经完成运行验收。

- [开发约定](AGENTS.md)
- [OpenSpec 使用流程](openspec/README.md)
- [核心行为基线](openspec/specs/)

最短启动路径：准备独立 ShopXO 测试后端，用 HBuilderX 导入本仓，核对自己的请求/静态资源地址，然后运行到目标平台。根 package.json 没有 npm scripts；本次未做平台编译或业务验收。

本次仅补文档与规范，没有改变业务实现，也没有部署服务。

---

<p align="center">
<img src="https://shopxoserver.oss-cn-beijing.aliyuncs.com/demo/system/logo.jpg" width="360" />
</p>

<h3 align="center">ShopXO企业级免费开源电商系统 - uniapp手机端</h3>

<div align="center">

```shell
如果对您有帮助，您可以点右上角 “Star” 收藏一下 ，获取第一时间更新，谢谢！
```

</div>

------------------------------------------------------------------------

#### 项目介绍
* 后端支持依托于ShopXO免费开源电商系统开发的uniapp端主题源码
* 支持可视化DIY拖拽装修，内置几十种标准组件，商品、文章、图片魔方、热区、视频、轮播、自定义等等...
* 默认内置8中搭配主色(可自行扩展更多配色、自由快捷切换)，商店提供海量适配各行业的DIY模板
* 已支持小程序（微信、QQ、百度、支付宝、头条&抖音、快手）+ H5 + APP

#### 使用教程
`程序打包操作需要有一定的编程技术基础、如需帮助请到git平台提issues寻求帮助`
* 打包教程 [http://uniapp.shopxo.net/](http://uniapp.shopxo.net/)

1. 先安装ShopXO免费开源系统 [http://install.shopxo.net/](http://install.shopxo.net/)
2. 将该源码导入HBuilderX开发工具、顶部工具栏 `运行->运行到小程序模拟器->(根据支持平台自行选择、如 微信开发者工具)`
3. App.vue中修改 request_url 和 static_url 地址为自己的商城地址即可使用
4. 主题默认为红色(red)，如更改主题 App.vue文件中修改 default_theme 默认主题标识，也可以到商店搜索【默认主题样式】远程控制主题配色
5. 发布、HBuilderX开发工具、顶部工具栏 `发行->(根据支持平台自行选择、如 微信开发者工具)`

#### 官方QQ群、答案`shopxo.net`
* 官方uniapp群：679303149

#### 体验码
![二维码.jpg](https://shopxoserver.oss-cn-beijing.aliyuncs.com/demo/system/demo-qrcode.jpg)


#### 当前项目源代码平台
* Gitee：[https://gitee.com/zongzhige/shopxo-uniapp](https://gitee.com/zongzhige/shopxo-uniapp)
* GitHub：[https://github.com/gongfuxiang/shopxo-uniapp](https://github.com/gongfuxiang/shopxo-uniapp)
* Coding：[https://zongzhige.coding.net/public/shopxo/uniapp/git](https://zongzhige.coding.net/public/shopxo/uniapp/git)
* GitCode：[https://gitcode.com/zongzhige/shopxo-uniapp](https://gitcode.com/zongzhige/shopxo-uniapp)
* uni-app：[https://ext.dcloud.net.cn/plugin?id=6380](https://ext.dcloud.net.cn/plugin?id=6380)

#### ShopXO后端源代码平台
* Gitee：[https://gitee.com/zongzhige/shopxo](https://gitee.com/zongzhige/shopxo)
* GitHub：[https://github.com/gongfuxiang/shopxo](https://github.com/gongfuxiang/shopxo)
* Coding：[https://zongzhige.coding.net/public/shopxo/shopxo/git](https://zongzhige.coding.net/public/shopxo/shopxo/git)
* GitCode：[https://gitcode.com/zongzhige/shopxo](https://gitcode.com/zongzhige/shopxo)

#### DIY装修源代码平台
* Gitee：[https://gitee.com/zongzhige/shopxo-diy](https://gitee.com/zongzhige/shopxo-diy)
* GitHub：[https://github.com/gongfuxiang/shopxo-diy](https://github.com/gongfuxiang/shopxo-diy)
* GitCode：[https://gitcode.com/zongzhige/shopxo-diy](https://gitcode.com/zongzhige/shopxo-diy)

#### Form表单源代码平台
* Gitee：[https://gitee.com/zongzhige/shopxo-form](https://gitee.com/zongzhige/shopxo-form)
* GitHub：[https://github.com/gongfuxiang/shopxo-form](https://github.com/gongfuxiang/shopxo-form)
* GitCode：[https://gitcode.com/zongzhige/shopxo-form](https://gitcode.com/zongzhige/shopxo-form)

#### API接口文档
* [https://doc.shopxo.net/article/2.html](https://doc.shopxo.net/article/2.html)

#### 小程序支持多种配色
![多种配色](https://shopxoserver.oss-cn-beijing.aliyuncs.com/demo/app/color.png "配色.jpg")

#### 小程序效果图片
![小程序页面](https://shopxoserver.oss-cn-beijing.aliyuncs.com/demo/app/page.png "小程序页面.jpg")

#### 小程序DIY装修
![DIY图片](https://shopxoserver.oss-cn-beijing.aliyuncs.com/demo/diy/diy.jpg "DIY图片")