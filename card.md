### 菜单获取


```
参数：
{
    'controller':'card',
    'action':'index',
    'id':ZlyJs.getUrlParam('id'),
    'option':'menu'
}
返回：
{
    "msg": "成功",
    "code": true,
    "data": {
        "interface": {
            "id": "2",
            "member": "4",
            "title": "众旅云",
            "logo": "http://wx.qlogo.cn/mmopen/PLc9fhw8iashRwVh0RnTAPKty3I92cDzKzwsmSbv8tYplCB3Wj4T5rfuOE2nGC8UxDnibrhN7FXcrYkRxQdoYltZ5zjwgOmZna/0",
            "service": "2",
            "appuser": "gh_dd71d4eef1bf",
            "qrcode_url": "http://mmbiz.qpic.cn/mmbiz/7aiaADrlRXiar2iaZ0VJQI5fficEfFs9SLmtw95laC6icGqjgv1GbfsRR2n6tbTer3ia0aDzjjbL31ClE31ibpBwibABtg/0"
        },
        "menu": [
            {
                "id": "2",
                "member_id": "4",
                "name": "用户信息",
                "url": "www.baidu.com",
                "order": "12",
                "dateline": "1464329680"
            },
            {
                "id": "3",
                "member_id": "4",
                "name": "订单管理",
                "url": "www.world.com",
                "order": "5",
                "dateline": "1464329720"
            }
        ]
    }
}
```

### 年卡列表
```
参数：
{
    'controller': 'card',
    'action': 'index',
    'id': ZlyJs.getUrlParam('id'),
    'option': 'cardList'
}
返回：
{
    "msg": "成功",
    "code": true,
    "data": {
        "interface": {'略'},
        "cardList": [
            {
                "id": "3",
                "member_id": "4",
                "image": "http://testtmpimage.b0.upaiyun.com/201605/03/146224483062210259.jpg",//年卡图片
                "configure": "360500*",
                "name": "新余旅游年卡",
                "free": "150.00",//年卡线下价格
                "delete": "0",
                "dateline": "1464224290",//时间
                "money": "90.99",//年卡线上价格
                "back_image": "http://testtmpimage.b0.upaiyun.com/201605/13/146312803163893373.jpg",//背部图片
                "type": "1", //排版模式1为竖版,2为横板
                "now_sale": 0.2 //年卡线上折扣
            },
            {
                "id": "5",
                "member_id": "4",
                "image": "http://testtmpimage.b0.upaiyun.com/201605/20/146373482392500255.jpg",
                "configure": "",
                "name": "测试",
                "free": "0.10",
                "delete": "0",
                "dateline": "1463734823",
                "money": "0.10",
                "back_image": "http://testtmpimage.b0.upaiyun.com/201605/20/146373482405790041.jpg",
                "type": "1",
                "now_sale": 0.1
            }
        ],
    }
}
```
