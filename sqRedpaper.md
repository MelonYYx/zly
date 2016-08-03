# 宿迁红包开发文档

======

## 用户表 (db_user)

编号id | 列名             | 数据类型        | 是否为空     | 约束条件              | 列名说明
---- | -------------- | ----------- | -------- | ----------------- | ------
1    | id             | Smallint(5) | Not null | AUTO_INCREMENT pk | 编号
2    | nickname       | varchar(60) | Not null | 默认为''             | 微信获取昵称
3    | openid         | text        | Not null | 默认为''             | openid
4    | mobile         | char(20)    | Not null | 默认为''             | 手机号码
5    | head_img       | tinytext    | Not null | 默认为''             | 头像
6    | dateline       | int(10)     | Not null | 默认为''             | 创建时间
7    | address        | varchar(40) | Not null | 默认为''             | 地址
8    | address_detail | varchar(40) | Not null | 默认为''             | 详细地址

## 订单表 (db_order)

编号id | 列名          | 数据类型         | 是否为空     | 约束条件              | 列名说明
---- | ----------- | ------------ | -------- | ----------------- | -------
1    | id          | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
2    | member_id   | Mediumint(8) | Not null | 默认为''             | 所属企业编号
3    | user_id     | Varchar(40)  | Not null | 默认为''             | 用户编号
4    | order_id    | varchar(40)  | Not null | 默认为''             | 订单编号
5    | amount      | int(10)      | Not null | 默认为''             | 购票数量
6    | order_date  | Int(10)      | Not null | 默认为0              | 购票时间
7    | scenic      | varchar(40)  | Not null | 默认为''             | 景点名称
8    | hotel       | varchar(40)  | Not null | 默认为''             | 酒店名称
9    | certificate | tinytext     | Not null | 默认为''             | 发票 凭证图片
