# 普通购物车展示

## Purpose
记录普通购物车组件的列表结构、空状态与失败反馈，保持移动端和服务端已有约定。依据：`components/cart/cart.vue::get_cart_data`；对应服务端 `app/api/controller/Cart.php::Index`。

## Requirements

### Requirement: 读取购物车汇总内的列表
购物车组件 SHALL 从成功响应的 data.data 读取商品行，并结束加载状态。

#### Scenario: 有商品行
- **WHEN** 普通 cart/index 返回 code=0 且列表非空
- **THEN** 组件保存列表、结合本地未选缓存处理选择状态、重新计算汇总并更新购物车角标

#### Scenario: 空购物车
- **WHEN** code=0 且 data.data 缺失或为空数组
- **THEN** 组件保存空列表并使用空列表提示状态

#### Scenario: 业务错误
- **WHEN** 服务端返回非零 code
- **THEN** 组件结束加载，将 msg 设为错误提示并调用既有登录检查

#### Scenario: 网络失败
- **WHEN** 请求触发 fail 回调
- **THEN** 组件结束加载并将列表提示设为网络错误
