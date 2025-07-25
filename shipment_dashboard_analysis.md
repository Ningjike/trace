# 外贸发货看板Dart命令行程序开发任务分析报告

## 任务目标
开发一个名为 "shipment_dashboard_cli" 的Dart命令行程序，用于管理外贸发货记录。

## 主要功能需求
1. **用户登录功能：**
   - 支持贸易商和客户两种角色登录。
   - 贸易商登录后可以创建新运单或更新已有运单。
   - 客户登录后输入客户代码，可以查询所有相关运单信息。
2. 添加新的发货记录（仅限贸易商）。
3. 查看特定的发货记录。
4. 更新已存在的发货记录（仅限贸易商）。
5. 删除发货记录（仅限贸易商）。
6. 列出所有发货记录（贸易商可以查看所有记录，客户只能查看与自己客户代码相关的记录）。

## 数据结构
### Shipment 类
- `orderId`: 订单ID。
- `customerName`: 客户姓名。
- `customerCode`: 客户代码。
- `shipmentDate`: 发货日期。
- `expectedDeliveryDate`: 预计送达日期。
- `status`: 当前状态（例如：已发货、在途、已送达）。

## 用户数据结构
### User 类
- `username`: 用户名。
- `password`: 密码。
- `role`: 角色（贸易商或客户）。
- `customerCode` (仅客户角色有此字段)。

## 数据存储
将发货记录存储在一个JSON文件中，将用户信息存储在另一个JSON文件中。

## 命令行参数解析
使用 `args` 包来解析命令行参数，支持以下命令：
- `login`: 用户登录。
- `add`: 添加一个新的发货记录（仅限贸易商）。
- `view`: 查看一个特定的发货记录。
- `update`: 更新一个已存在的发货记录（仅限贸易商）。
- `delete`: 删除一个发货记录（仅限贸易商）。
- `list`: 列出所有发货记录（贸易商可以查看所有记录，客户只能查看与自己客户代码相关的记录）。

## 步骤计划
1. 创建Dart命令行项目：
    - 使用 `dart create shipment_dashboard_cli` 命令创建项目。
2. 定义 `Shipment` 类：
    - 包含订单ID、客户姓名、客户代码、发货日期、预计送达日期和当前状态等字段。
3. 定义 `User` 类：
    - 包含用户名、密码、角色和客户代码（仅限客户）等字段。
4. 定义 `ShipmentManager` 类：
    - 处理添加、更新、查看和删除发货记录等操作。
    - 将数据序列化到JSON文件，并能从JSON文件反序列化回 `Shipment` 对象列表。
5. 定义 `UserManager` 类：
    - 处理用户登录验证，并区分贸易商和客户角色。
6. 实现命令行参数解析：
    - 使用 `args` 包来解析 `login`、`add`、`view`、`update`、`delete` 和 `list` 命令。
7. 测试命令行应用程序：
    - 验证各个命令是否按预期工作。

## 后续计划
1. 确认以上计划后，切换到“代码”模式来实施该计划。

如果该计划符合您的需求，请确认。如果有任何修改建议，请告知。