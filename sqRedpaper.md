# 宿迁红包开发文档

--------------------------------------------------------------------------------

## 用户表 (db_sqpaper_user)

编号id | 列名             | 数据类型        | 是否为空     | 约束条件              | 列名说明
---- | -------------- | ----------- | -------- | ----------------- | --------------------------------------
1    | id             | Smallint(5) | Not null | AUTO_INCREMENT pk | 编号
2    | nickname       | varchar(60) | Not null | 默认为''             | 微信获取昵称
3    | openid         | text        | Not null | 默认为''             | openid
4    | mobile         | char(20)    | Not null | 默认为''             | 手机号码
5    | head_img       | tinytext    | Not null | 默认为''             | 头像
6    | grant_way      | tinyint(3)  | Not null | 默认为''             | 发放方式(0=>微信红包,1=>支付宝账号,2=>银行转账)
7    | alipay_account | varchar(40) | Not null | 默认为''             | 支付宝账号
8    | alipay_name    | varchar(40) | Not null | 默认为''             | 支付宝昵称
9    | bank_account   | varchar(40) | Not null | 默认为''             | 银行账号
10   | bank           | varchar(40) | Not null | 默认为''             | 银行名称
11   | bank_name      | varchar(40) | Not null | 默认为''             | 银行户名
12   | bank_title     | varchar(40) | Not null | 默认为''             | 开户行
13   | grant_config   | tinytext    | Not null | 默认为''             | 发放信息配置----序列化(支付宝{账号xxx:,昵称:xxx},银行{})
14   | head_img       | tinytext    | Not null | 默认为''             | 头像
15   | dateline       | int(10)     | Not null | 默认为''             | 创建时间

--------------------------------------------------------------------------------

## 订单表 (db_sqpaper_order)

编号id | 列名              | 数据类型         | 是否为空     | 约束条件              | 列名说明
---- | --------------- | ------------ | -------- | ----------------- | -------------------------------------------
1    | id              | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
2    | member_id       | Mediumint(8) | Not null | 默认为''             | 所属企业编号
3    | user_id         | Varchar(40)  | Not null | 默认为''             | 用户编号
4    | order_id        | varchar(40)  | Not null | 默认为''             | 订单编号
5    | amount          | int(10)      | Not null | 默认为''             | 购票数量
6    | order_date      | Int(10)      | Not null | 默认为0              | 购票时间
7    | scenic          | varchar(40)  | Not null | 默认为''             | 景点名称
8    | hotel           | varchar(40)  | Not null | 默认为''             | 酒店名称
9    | invoice_code    | varchar(80)  | Not null | 默认为''             | 发票 凭证单号
10   | invoice_img     | tinytext     | Not null | 默认为''             | 发票 凭证图片
11   | check_date      | int(10)      | Not null | 默认为0              | 提交审核时间
12   | check_status    | tinyint(3)   | Not null | 默认为0              | 审核状态 默认为0 0=>还未提交 1=>提交未审核 2=>审核未通过 3=>审核通过
13   | de_grant_status | tinyint(3)   | Not null | 默认为0              | 默认发放状态 默认为0 0 =>未发放 1=>发放成功 2/other =>发放失败
14   | grant_status    | tinyint(3)   | Not null | 默认为0              | 微信发放状态 默认为0 0 =>未发放 1=>发放成功 ohter => 发放失败
15   | grant_date      | int(10)      | Not null | 默认为0              | 发放时间

--------------------------------------------------------------------------------

## 操作记录表 (db_sqpaper_operate_log)

编号id | 列名         | 数据类型         | 是否为空     | 约束条件              | 列名说明
---- | ---------- | ------------ | -------- | ----------------- | -----------------------
1    | id         | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
2    | member_id  | Mediumint(8) | Not null | 默认为''             | 所属企业编号
3    | operate_id | Mediumint(8) | Not null | 默认为''             | 工作人员编号
3    | user_id    | Mediumint(8) | Not null | 默认为''             | 用户id
4    | order_id   | varchar(40)  | Not null | 默认为''             | 操作订单号(order表中的order_id)
5    | id_card    | varchar(40)  | Not null | 默认为''             | 操作身份证号
6    | status     | tinyint(3)   | Not null | 默认为''             | 操作类型(1=>审核,2=>发放红包,3=>)
7    | log        | text         | Not null | 默认为''             | 操作内容
8    | dateline   | int(10)      | Not null | 默认为''             | 时间

--------------------------------------------------------------------------------

## 红包发放记录表 (db_sqpaper_grant_log)

编号id | 列名         | 数据类型         | 是否为空     | 约束条件              | 列名说明
---- | ---------- | ------------ | -------- | ----------------- | ---------------------------------
1    | id         | Smallint(5)  | Not null | AUTO_INCREMENT pk | 编号
2    | member_id  | Mediumint(8) | Not null | 默认为''             | 所属企业编号
3    | user_id    | Mediumint(8) | Not null | 默认为''             | 用户id
4    | id_card    | Mediumint(8) | Not null | 默认为''             | 用户身份证
5    | money      | decimal(9,2) | Not null | 默认为''             | 发放金额
6    | operate_id | Mediumint(8) | Not null | 默认为''             | 发放操作员id(operate_log表中的operate_id)
7    | dateline   | int(10)      | Not null | 默认为''             | 操作时间
