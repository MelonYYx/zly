# 宿迁红包开发文档

--------------------------------------------------------------------------------

## 用户表 (db_sqpaper_user)

列名             | 数据类型         | 是否为空     | 约束条件              | 列名说明
:------------- | :----------- | :------- | :---------------- | :-----------------------------
id             | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
nickname       | varchar(60)  | Not null | 默认为''             | 微信获取昵称
openid         | text         | Not null | 默认为''             | openid
mobile         | char(20)     | Not null | 默认为''             | 手机号码
head_img       | tinytext     | Not null | 默认为''             | 头像
grant_way      | tinyint(3)   | Not null | 默认为''             | 发放方式(0=>微信红包,1=>支付宝账号,2=>银行转账)
alipay_account | varchar(40)  | Not null | 默认为''             | 支付宝账号
alipay_name    | varchar(40)  | Not null | 默认为''             | 支付宝昵称
bank_account   | varchar(40)  | Not null | 默认为''             | 银行账号
bank           | varchar(40)  | Not null | 默认为''             | 银行名称
bank_name      | varchar(40)  | Not null | 默认为''             | 银行户名
bank_title     | varchar(40)  | Not null | 默认为''             | 开户行
total          | decimal(9,2) | Not null | 默认为''             | 累计获得红包
dateline       | int(10)      | Not null | 默认为''             | 创建时间

--------------------------------------------------------------------------------

## 入园记录表 (db_sqpaper_enter)

列名        | 数据类型         | 是否为空     | 约束条件              | 列名说明
:-------- | :----------- | :------- | :---------------- | :------------------
id        | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
member_id | Mediumint(8) | Not null | 默认为''             | 所属企业编号
id_card   | varchar(40)  | Not null | 默认为''             | 身份证
scenic    | Smallint(3)  | Not null | 默认为''             | 景区(0=>项王故里 ,1=>三台山)
machine   | varchar(40)  | Not null | 默认为''             | 扫描机器码
amount    | int(10)      | Not null | 默认为''             | 购票数量
is_use    | int(10)      | Not null | 默认为''             | 是否使用(0=>未使用 1=>已使用)
dateline  | Int(10)      | Not null | 默认为0              | 入园时间

--------------------------------------------------------------------------------

## 订单表 (db_sqpaper_order)

列名               | 数据类型         | 是否为空     | 约束条件              | 列名说明
:--------------- | :----------- | :------- | :---------------- | :-------------------------------------------------------------
id               | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
member_id        | Mediumint(8) | Not null | 默认为''             | 所属企业编号
user_id          | Varchar(40)  | Not null | 默认为''             | 用户编号
order_id         | varchar(40)  | Not null | 默认为''             | 订单编号
amount           | int(10)      | Not null | 默认为''             | 购票数量
order_date       | Int(10)      | Not null | 默认为0              | 购票时间
id_card          | varchar(40)  | Not null | 默认为''             | 操作身份证号
scenic           | varchar(40)  | Not null | 默认为''             | 景点名称
hotel_title      | varchar(40)  | Not null | 默认为''             | 酒店名称
hotel_enter_date | Int(10)      | Not null | 默认为''             | 酒店入住时间
hotel_left_date  | varchar(40)  | Not null | 默认为''             | 酒店离开时间
hotel_amount     | varchar(40)  | Not null | 默认为''             | 酒店房间数
hotel_number     | varchar(40)  | Not null | 默认为''             | 酒店房间号
hotel_person     | varchar(40)  | Not null | 默认为''             | 入住人数
invoice_code     | varchar(80)  | Not null | 默认为''             | 发票 凭证单号
invoice_img      | tinytext     | Not null | 默认为''             | 发票 凭证图片
check_date       | int(10)      | Not null | 默认为0              | 提交审核时间
check_status     | tinyint(3)   | Not null | 默认为0              | 审核状态 默认为0 0=>还未提交 1=>提交未审核 2=>初审核未通过 3=>初审核通过 4=>财政未通过 5=>财政通过
de_grant_status  | tinyint(3)   | Not null | 默认为0              | 默认发放状态 默认为0 0 =>未发放 1=>发放成功 2/other =>发放失败
grant_status     | tinyint(3)   | Not null | 默认为0              | 微信发放状态 默认为0 0 =>未发放 1=>发放成功 ohter => 发放失败
grant_date       | int(10)      | Not null | 默认为0              | 发放时间

--------------------------------------------------------------------------------

## 操作记录表 (db_sqpaper_operate_log)

列名         | 数据类型         | 是否为空     | 约束条件              | 列名说明
:--------- | :----------- | :------- | :---------------- | :--------------------------------------------------------
id         | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
member_id  | Mediumint(8) | Not null | 默认为''             | 所属企业编号
operate_id | Mediumint(8) | Not null | 默认为''             | 工作人员编号
user_id    | Mediumint(8) | Not null | 默认为''             | 用户id
order_id   | varchar(40)  | Not null | 默认为''             | 操作订单号(order表中的order_id)
id_card    | varchar(40)  | Not null | 默认为''             | 操作身份证号
status     | tinyint(3)   | Not null | 默认为''             | 操作类型(2=>初审核未通过 3=>初审核通过 4=>财政未通过 5=>财政通过 6=>发放成功 7=>发放失败)
log        | text         | Not null | 默认为''             | 操作内容
dateline   | int(10)      | Not null | 默认为''             | 时间

--------------------------------------------------------------------------------

## 红包发放记录表 (db_sqpaper_grant_log)

列名         | 数据类型         | 是否为空     | 约束条件              | 列名说明
:--------- | :----------- | :------- | :---------------- | :--------------------------------
id         | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
member_id  | Mediumint(8) | Not null | 默认为''             | 所属企业编号
user_id    | Mediumint(8) | Not null | 默认为''             | 用户id
id_card    | Mediumint(8) | Not null | 默认为''             | 用户身份证
money      | decimal(9,2) | Not null | 默认为''             | 发放金额
operate_id | Mediumint(8) | Not null | 默认为''             | 发放操作员id(operate_log表中的operate_id)
dateline   | int(10)      | Not null | 默认为''             | 操作时间
