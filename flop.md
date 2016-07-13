# 翻牌游戏接口
---

### 获取当前活动相关信息
参数 | 含义 | 值
---|---|---
controller | 控制器 | flop
action | 行为 | activity
option | 执行 | getLotteryDetail
activityId | 活动id | 例：'1' 

data返回 | 含义
---|---
id | 编号
member_id | 所属企业编号
title | 活动名称
intro | 简介
image | 图片地址
verifi_code | 核销码
address | 领奖地址
contacts | 联系人
tel | 联系电话
probability | 获奖概率
awards_date | 发放奖品时间
start_date | 领奖开始时间
end_date | 领奖结束时间
dateline | 添加时间
