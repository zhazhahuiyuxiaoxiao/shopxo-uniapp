# ShopXO uni-app 移动端个人副本：工程基线

- 核对日期：2026-10-29。
- 基线分支：`master`；完整提交：`e0a492284090cf190cb6911957c3a23fa2cf472d`。
- 文档工作分支：`codex/openspec-docs-20261029`。
- 本文为源码现状记录，不代表线上版本、生产可用性或独立开发贡献。

## 用途与来源

本仓是 `gongfuxiang/shopxo-uniapp` 的个人副本，保留 ShopXO 上游署名、说明与 `LICENSE`。本仓承载 uni-app 移动端页面和组件，业务数据由对应 ShopXO 服务端提供；不能将本仓单独运行等同于完整商城上线或个人原创开发。

## 源码与能力映射

| 能力 | 源码依据 | 服务端对应点 |
| --- | --- | --- |
| 请求 URL、客户端与用户参数 | `App.vue::get_request_url`、`request_params_handle` | `api.php`、`app/api/controller/Common.php` |
| 商品详情及错误提示 | `pages/goods-detail/goods-detail.vue::init` | `Goods.php::Detail` |
| 购物车列表、数量更新与删除 | `components/cart/cart.vue`、`pages/cart/cart.vue` | `Cart.php`、`GoodsCartService.php` |
| 购买页与结算入口 | `pages/buy/buy.vue`、`components/cart/cart.vue` | `Buy.php` |
| 平台页面注册与依赖元数据 | `pages.json`、`package.json` |

服务端已按 `master@aad87b5874023f0b7d207e86227214e45ede7cf9` 核对；表中服务端文件位于配对 shopxo 仓库。当前补录仅覆盖普通商品/购物车路径，不声称各插件或所有平台均联调通过。

## 最短本地启动路径

首先准备独立的 ShopXO 测试服务端和测试账号，避免将客户端指向默认远程演示站或生产商城。

1. 使用 HBuilderX 导入仓库根目录。
2. 在自己的本地副本核对 `App.vue` 中 `request_url` 和 `static_url` 字段，指向 `<YOUR_TEST_SHOP_URL>/`；不在文档复制真实配置值。
3. 核对所选平台的应用标识及网络要求，用测试应用标识 `<YOUR_TEST_APP_ID>`，不要提交真实发布配置。
4. 在 HBuilderX 选择“运行”到目标小程序模拟器或 H5，并验证首页、商品详情和购物车错误状态。

根 `package.json` 没有 scripts，不能虚构 `npm run dev`、`npm run build` 或 `npm test`。依赖/SDK 安装和平台构建应先审阅并授权；本次未安装工具、修改平台配置或运行发布。

## 验证与验收

当前没有仓库级 npm 测试/构建脚本；使用 HBuilderX 的目标平台编译和手动验收。最低检查为：有效商品、无效商品 ID、空购物车、登录失效、网络失败、数量更新和删除反馈。联调必须同时记录服务端与客户端提交，不能将一个平台编译成功泛化到全部平台。

本次已完成：核对 Git 基线、阅读上述源码和命令定义；OpenSpec 1.14.2 严格校验 2/2 通过，`git diff --check` 通过，本次新增/改写文档的 11 个本地相对链接检查无缺失（保留的上游原文不计入）。
本次未运行：依赖安装、应用启动、构建、业务测试、真实平台/外部服务集成及生产部署。原因是本次范围仅限文档与流程，不写运行数据、不调用收费服务。

- [ ] 在隔离环境按上面的路径启动。
- [ ] 按每个 [核心 spec](../openspec/specs/) 验收正常、空输入/不存在和失败场景。
- [ ] 变更身份、权限或数据语义时核对所有消费者，补充原行为与失败路径验证。
- [ ] PR 记录实际命令、结果与未覆盖项，不将“可运行命令”写成“已通过”。

## 已知边界与重新评估条件

- `App.vue` 使用 `api.php?s=<controller>/<action>`，并追加 token、客户端类型等参数；服务端的 `code`/`msg`/`data` 是现有契约，不在文档任务重构。
- `package.json` 名称/描述为视频播放组件元数据，不能据此认定项目是完整 CLI 工程；实际主工作流为上游说明中的 HBuilderX。
- 登录缓存不能代替服务端授权。购物车 `code=-400` 进入既有登录检查逻辑；页面错误处理和服务端状态必须共同验收。
- 第三方插件、支付、物流、用户位置、平台发布及隐私流程未实测。本次仅选普通路径补录，未审计所有组件。
- 若更改 API 参数、购物车数量/价格/选择状态、下单或支付结果，需要同时核对 shopxo，确认业务矩阵后实施；本次没有变更任何契约。
- 现有 node_modules、uni_modules、静态资源和平台配置保持原样，不作为新验证产物或安全保证。

## 文档维护

[README](../README.md) 提供入口，[AGENTS](../AGENTS.md) 约束开发，[OpenSpec](../openspec/README.md) 保存行为与后续变更证据。源码或依赖变化后同步复核本基线。
