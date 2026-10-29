# 商品详情展示

## Purpose
记录移动端请求普通商品详情并区分成功、业务错误与网络失败的行为。依据：`pages/goods-detail/goods-detail.vue::init`、`App.vue::get_request_url`；对应服务端 `app/api/controller/Goods.php::Detail`。

## Requirements

### Requirement: 加载商品详情
页面 SHALL 使用现有 goods/detail API 和 code/msg/data 响应语义加载详情。

#### Scenario: 请求成功
- **WHEN** goods/detail 请求返回业务 code=0
- **THEN** 页面读取 data.goods 并初始化商品数据，同时更新关联展示数据

#### Scenario: 业务错误
- **WHEN** 请求收到非零业务 code
- **THEN** 页面将服务端 msg 写入加载提示状态，不执行成功分支

#### Scenario: 网络失败
- **WHEN** uni.request 触发 fail 回调
- **THEN** 页面停止下拉刷新，设置网络错误加载状态并展示网络错误提示
