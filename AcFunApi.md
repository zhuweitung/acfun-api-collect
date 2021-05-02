# AcFun API列表

- [目录](#acfun-api列表)
  - [PC端](#pc端)
    - [获取账户信息](#获取账户信息)
    - [获取关注分组](#获取关注分组)
    - [获取关注up列表](#获取关注up列表)
    - [获取关注up视频动态](#获取关注up视频动态)
    - [获取正在直播关注up列表](#获取正在直播关注up列表)
    - [获取视频弹幕列表](#获取视频弹幕列表)
    - [关注与取消关注](#关注与取消关注)
    - [获取香蕉商城商品列表](#获取香蕉商城商品列表)
  - [移动端](#移动端)
    - [登录](#登录)
    - [获取token](#获取token)
    - [每日香蕉榜](#每日香蕉榜)
    - [每日签到](#每日签到)
    - [发弹幕](#发弹幕)
    - [视频投蕉](#视频投蕉)
    - [视频点赞/取消点赞（pc、web通用）](#视频点赞取消点赞pcweb通用)
    - [视频分享](#视频分享)

## PC端

### 获取账户信息

请求地址：

> https://www.acfun.cn/rest/pc-direct/user/personalInfo

请求方式：`post`

请求参数：无

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "info": {
        "renameCard": 3,
        "isEmailCheck": true,
        "isMobileCheck": true,
        "mobile": "178****0287",
        "email": "z****g@foxmail.com",
        "activeRecently": true,
        "signIn": false,
        "headUrl": "https://tx-free-imgs.acfun.cn/style/image/201907/Mf4Uo9Hw96jg2gbHAOGteeXjf1MIB2N0.jpg?imageslim",
        "verifiedType": 0,
        "verifiedText": "",
        "nameRed": true,
        "avatarFrame": 578,
        "avatarFrameMobileImg": "https://imgs.aixifan.com/WxlISL5vzX-6vMBv2-R3ARFn-q2iMZr-FzayAv.gif",
        "avatarFramePcImg": "https://imgs.aixifan.com/GyMkwF3Re5-nuAJBb-6Bf67n-iEZnUn-3ueuAz.gif",
        "contentCount": "2",
        "nameColor": 1,
        "verifiedTypes": [],
        "experimentConfig": "{\"player\":{\"version\":\"beta-latest\",\"cdn\":\"\"},\"usePwa\":true}",
        "gender": 1,
        "shareUrl": "https://m.acfun.cn/upPage/625724",
        "registerTime": 1376341276000,
        "userId": 625724,
        "goldBanana": 1625,
        "followed": "17",
        "following": "378",
        "firstDepositState": 2,
        "banana": 1148,
        "isContractUp": false,
        "isRegular": true,
        "followedNum": 17,
        "tagStowCount": "34",
        "isTeenagerMode": false,
        "isSameCityTagAllowShown": true,
        "allowShowLikeList": true,
        "mediaWearInfo": {
            "uperId": 12610197,
            "uperName": "小缸和阿灿",
            "uperHeadUrl": "https://imgs.aixifan.com/content/2021_2_28/1.6145216197831511E9.png",
            "clubName": "榨汁机",
            "level": 3
        },
        "userName": "蒸汽咸鱼",
        "blog": "这种东西没人会鸟的。",
        "qq": "",
        "comeFrom": "浙江,湖州",
        "sexTrend": 1,
        "signature": "做人如果没有梦想，跟咸鱼有什么区别。",
        "level": 28
    },
    "host-name": "hb2-acfun-kce-node135.aliyun"
}
```

</details>



### 获取关注分组

请求地址：

> https://www.acfun.cn/rest/pc-direct/relation/getGroups

请求方式：`post`

请求参数：无

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "groupList": [
        {
            "groupName": "vup",
            "followingCount": 13,
            "followingCountShow": "13",
            "groupId": "174981"
        }
    ],
    "host-name": "hb2-acfun-kce-node110.aliyun"
}
```

</details>



### 获取关注up列表

请求地址：

> https://www.acfun.cn/rest/pc-direct/relation/getFollows

请求方式：`post`

请求参数：

| 参数名 | 值   | 说明                      |
| ------ | ---- | ------------------------- |
| action | 7    | 值为8时获取本账号粉丝列表 |

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "pcursor": "100",
    "friendList": [
        {
            "groupId": "29645",
            "groupName": "影视",
            "isFriend": false,
            "verifiedType": 2,
            "verifiedText": "知名游戏UP主\n",
            "userImg": "https://tx-free-imgs.acfun.cn/Fjz9sOCGfnZmqi-ql0LD2CpBzIQm?imageslim",
            "followingCount": 31,
            "nameColor": 1,
            "verifiedTypes": [
                2,
                5
            ],
            "isFollowing": true,
            "followingStatus": 3,
            "contributeCount": 200,
            "comeFrom": "重庆,渝中区",
            "sexTrend": 3,
            "isSignedUpCollege": true,
            "userName": "达奇上校",
            "userId": "346807",
            "fanCount": 33287,
            "gender": 1,
            "signature": "赌命而行",
            "followingCountShow": "31",
            "fanCountShow": "3.3万",
            "contributeCountShow": "200"
        }
    ],
    "host-name": "hb2-acfun-kce-node110.aliyun",
    "totalCount": 378
}
```

</details>



### 获取关注up视频动态

请求地址：

> https://www.acfun.cn/rest/pc-direct/feed/webPush

请求方式：`get`

请求参数：

| 参数名  | 值   | 说明            |
| ------- | ---- | --------------- |
| count   | 60   | 获取数据量      |
| pcursor | 0    | 0表示当前时间戳 |

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "feedList": [
        {
            "fansOnlyDesc": "走进工厂：看螺丝是如何制造出来的",
            "videoSizeType": 1,
            "caption": "走进工厂：看螺丝是如何制造出来的",
            "coverUrl": "https://tx-free-imgs.acfun.cn/o_1f3hlvgefn1e12mce9q1fn21ge90.jpeg?imageslim",
            "videoId": "23589397",
            "coverImgInfo": {
                "width": 0,
                "height": 0,
                "size": 0,
                "type": 0,
                "thumbnailImage": {
                    "cdnUrls": [
                        {
                            "url": "https://tx-free-imgs.acfun.cn/o_1f3hlvgefn1e12mce9q1fn21ge90.jpeg?imageslim",
                            "freeTrafficCdn": false
                        }
                    ]
                }
            },
            "playDuration": "03:58",
            "disableThrowBanana": false,
            "channel": {
                "parentId": 70,
                "parentName": "科技",
                "name": "科技制造",
                "id": 90
            },
            "shareCount": 3,
            "stowCount": 38,
            "bananaCount": 407,
            "commentCount": 26,
            "viewCount": 1814,
            "user": {
                "userHead": "https://tx-free-imgs.acfun.cn/FtWcHwDUKLxXjagk-HRvCuADzHCZ?imageslim",
                "isFollowing": true,
                "verifiedTypes": [
                    5
                ],
                "isUpCollege": true,
                "nameColor": 0,
                "verifiedType": 0,
                "userName": "硬核拆解",
                "userId": 19281632,
                "userHeadImgInfo": {
                    "width": 0,
                    "height": 0,
                    "size": 0,
                    "type": 0,
                    "thumbnailImage": {
                        "cdnUrls": [
                            {
                                "url": "https://tx-free-imgs.acfun.cn/FtWcHwDUKLxXjagk-HRvCuADzHCZ?imageslim",
                                "freeTrafficCdn": false
                            }
                        ]
                    }
                }
            },
            "shareUrl": "https://m.acfun.cn/v/?ac=27891648",
            "isFavorite": false,
            "picShareUrl": "https://m.acfun.cn/v/?ac=27891648&shareType=pic",
            "createTimeGroup": 1,
            "tag": [
                {
                    "tagResourceCount": 0,
                    "tagId": 85171,
                    "tagCountStr": "0内容",
                    "tagName": "螺丝"
                },
                {
                    "tagResourceCount": 0,
                    "tagId": 12550,
                    "tagCountStr": "0内容",
                    "tagName": "制造"
                },
                {
                    "tagResourceCount": 0,
                    "tagId": 70,
                    "tagCountStr": "0内容",
                    "tagName": "科普"
                },
                {
                    "tagResourceCount": 0,
                    "tagId": 38250,
                    "tagCountStr": "0内容",
                    "tagName": "知识"
                }
            ],
            "tagResourceType": 2,
            "resourceType": 2,
            "resourceId": 27891648,
            "authorId": 19281632,
            "likeCount": 88,
            "createTime": 1618723279102,
            "userInfo": {
                "action": 3,
                "href": "19281632",
                "sexTrend": -1,
                "isFollowing": true,
                "avatarFrame": 426,
                "verifiedTypes": [
                    5
                ],
                "nameColor": 0,
                "followingStatus": 2,
                "contributeCount": "480",
                "headUrl": "https://tx-free-imgs.acfun.cn/FtWcHwDUKLxXjagk-HRvCuADzHCZ?imageslim",
                "fanCountValue": 41011,
                "followingCount": "7",
                "gender": 1,
                "fanCount": "4.1万",
                "userHeadImgInfo": {
                    "width": 0,
                    "height": 0,
                    "size": 0,
                    "type": 0,
                    "thumbnailImage": {
                        "cdnUrls": [
                            {
                                "url": "https://tx-free-imgs.acfun.cn/FtWcHwDUKLxXjagk-HRvCuADzHCZ?imageslim",
                                "freeTrafficCdn": false
                            }
                        ]
                    }
                },
                "avatarFrameMobileImg": "https://imgs.aixifan.com/cms/2019_12_30/1577698794096.png",
                "avatarFramePcImg": "https://imgs.aixifan.com/cms/2019_12_30/1577698701130.png",
                "headCdnUrls": [
                    {
                        "url": "https://tx-free-imgs.acfun.cn/FtWcHwDUKLxXjagk-HRvCuADzHCZ?imageslim",
                        "freeTrafficCdn": true
                    },
                    {
                        "url": "https://imgs.aixifan.com/FtWcHwDUKLxXjagk-HRvCuADzHCZ?imageslim",
                        "freeTrafficCdn": false
                    }
                ],
                "isJoinUpCollege": true,
                "followingCountValue": 7,
                "contributeCountValue": 480,
                "name": "硬核拆解",
                "signature": "每日拆解各种电子设备,生活用品，老旧电器与机械等",
                "id": "19281632"
            },
            "time": "34分钟前",
            "isThrowBanana": false,
            "isLike": false
        }
    ],
    "followUpers": [
        {
            "hasUnReadResource": true,
            "headUrl": "https://imgs.aixifan.com/style/image/201907/varjkIG5PMSiP1Bw8HjqlPtLENjDOyZb.jpg",
            "userId": 156843,
            "name": "c137芦苇娘"
        }
    ],
    "pcursor": "1618655745480",
    "host-name": "hb2-acfun-kce-node123.aliyun",
    "requestId": "76b8fb83773042a4b3e58cbf7a9faf5e"
}
```

</details>



### 获取正在直播关注up列表

请求地址：

> https://www.acfun.cn/rest/pc-direct/live/followLiveUsers

请求方式：`post`

请求参数：无

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "liveUsers": [
        {
            "disableDanmakuShow": false,
            "groupId": "c5710058cf174dfa9761e936d211e560_0_1&-124&&lf",
            "action": 40,
            "href": "52326",
            "coverUrls": [
                "https://ali-live.static.yximgs.com/bs2/ztlc/cover_iC2mgecseIk_raw.jpg",
                "https://js-live.static.yximgs.com/bs2/ztlc/cover_iC2mgecseIk_raw.jpg"
            ],
            "onlineCount": 506,
            "liveId": "iC2mgecseIk",
            "user": {
                "action": 3,
                "href": "52326",
                "followingStatus": 2,
                "contributeCount": "6",
                "sexTrend": 1,
                "followingCount": "15",
                "avatarFrameMobileImg": "https://imgs.aixifan.com/cms/2019_12_21/1576933781819.png",
                "avatarFramePcImg": "https://imgs.aixifan.com/cms/2019_12_21/1576933739973.png",
                "verifiedTypes": [
                    1
                ],
                "nameColor": 1,
                "fanCountValue": 18785881,
                "verifiedType": 1,
                "verifiedText": "AcFun官方吉祥物",
                "isFollowing": true,
                "avatarFrame": 424,
                "headUrl": "https://tx-free-imgs.acfun.cn/content/2020_4_5/1.5860178587515075E9.png?imageslim",
                "liveId": "iC2mgecseIk",
                "gender": 0,
                "fanCount": "1878.6万",
                "headCdnUrls": [
                    {
                        "url": "https://tx-free-imgs.acfun.cn/content/2020_4_5/1.5860178587515075E9.png?imageslim",
                        "freeTrafficCdn": true
                    },
                    {
                        "url": "https://imgs.aixifan.com/content/2020_4_5/1.5860178587515075E9.png?imageslim",
                        "freeTrafficCdn": false
                    }
                ],
                "followingCountValue": 15,
                "contributeCountValue": 6,
                "userHeadImgInfo": {
                    "width": 0,
                    "height": 0,
                    "size": 0,
                    "type": 0,
                    "thumbnailImage": {
                        "cdnUrls": [
                            {
                                "url": "https://tx-free-imgs.acfun.cn/content/2020_4_5/1.5860178587515075E9.png?imageslim",
                                "freeTrafficCdn": false
                            }
                        ]
                    }
                },
                "name": "AC娘",
                "signature": "亲爱的用户你好~我是AC娘~欢迎来到AcFun",
                "id": "52326"
            },
            "likeCount": 4076,
            "authorId": 52326,
            "title": "AFM深圳站-【春日野火】Live放送",
            "createTime": 1618724798169,
            "streamName": "kszt_9KRHHeNTcvc",
            "formatLikeCount": "4076",
            "formatOnlineCount": "506",
            "panoramic": false,
            "bizCustomData": "{\"typeId\":301}",
            "cdnAuthBiz": 0,
            "portrait": false,
            "type": {
                "id": 301,
                "name": "唱见",
                "categoryId": 3,
                "categoryName": "娱乐"
            },
            "hasFansClub": false,
            "paidShowUserBuyStatus": false
        }
    ],
    "host-name": "hb2-acfun-kce-node136.aliyun"
}
```

</details>



### 获取视频弹幕列表

请求地址：

>  https://www.acfun.cn/rest/pc-direct/new-danmaku/list

请求方式：`post`

请求参数：

| 参数名         | 值    | 说明     |
| -------------- | ----- | -------- |
| resourceId     |       | 视频id   |
| resourceType   | 9     |          |
| enableAdvanced | true  | 高级弹幕 |
| pcursor        | 1     |          |
| count          | 200   |          |
| sortType       | 1     |          |
| asc            | false |          |

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "danmakus": [
        {
            "likeCount": 0,
            "roleId": 0,
            "danmakuId": 204617830,
            "danmakuType": 0,
            "color": 16777215,
            "createTime": 1618735041553,
            "rank": 5,
            "userId": 349907,
            "isLike": false,
            "body": "这个帽子，这个衣服，棒子游戏啊。。。",
            "mode": 5,
            "position": 587200,
            "size": 16
        }
    ],
    "pcursor": "2",
    "host-name": "hb2-acfun-kce-node117.aliyun",
    "totalCount": 952,
    "requestId": "0dae7e8863d340e2a1e6b1f39640e5f9"
}
```

</details>



### 关注与取消关注

请求地址：

>  https://www.acfun.cn/rest/pc-direct/relation/follow

请求方式：`post`

请求参数：

| 参数名   | 值   | 说明                |
| -------- | ---- | ------------------- |
| toUserId |      | 关注用户id          |
| action   |      | 1、关注 2、取消关注 |
| groupId  |      | 分组                |

<details>
<summary>查看响应格式示例：</summary>

```json
{
    host-name: "hb2-acfun-kce-node33.aliyun",
    result: 0
}
```

</details>



### 获取香蕉商城商品列表

请求地址：

> https://www.acfun.cn/rest/pc-direct/shop/productList

请求方式：`post`

请求参数：

| 参数名   | 值    | 说明     |
| -------- | ----- | -------- |
| pageNo   | 1     | 当前页   |
| pageSize | 20    | 每页数量 |
| sortType | 1     | 排序类型 |
| asc      | false |          |

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "host-name": "hb2-acfun-kce-node146.aliyun",
    "result": 0,
    "totalNum": 100,
    "list": [
        {
            "amount": 1500,
            "coolDownDay": 0,
            "description": "<span style=\"font-family: system-ui, -apple-system, system-ui, &quot;Segoe UI&quot;, &quot;PingFang SC&quot;, &quot;Hiragino Sans GB&quot;, &quot;Microsoft YaHei&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;, &quot;Segoe UI Symbol&quot;; font-size: 14px; font-variant-ligatures: normal; orphans: 2; white-space: pre-wrap; widows: 2; background-color: rgb(235, 236, 240);\">C137宇宙发廊为莫蒂设计的新发型</span>",
            "expireTime": 2527257600000,
            "imageAppUrl": "https://imgs.aixifan.com/3WU60arjBn-7bymEv-nUji2q-73yi6f-2yQV7z.gif",
            "imagePCUrl": "https://imgs.aixifan.com/2lzfSmZLbA-viemyu-6b2Uf2-IFZrqq-qE7rQn.gif",
            "imageUrl": "https://imgs.aixifan.com/3WU60arjBn-7bymEv-nUji2q-73yi6f-2yQV7z.gif",
            "levelLimit": 0,
            "maxAllowBuy": 1,
            "priceInfo": [
                {
                    "payType": 2,
                    "payTypeInfo": "金香蕉",
                    "count": 499
                }
            ],
            "productId": 630,
            "sales": 903,
            "status": 1,
            "title": "莫蒂的新发型",
            "type": 2
        }
    ]
}
```

</details>



## 移动端

### 登录

请求地址：

> https://id.app.acfun.cn/rest/app/login/signin

请求方式：`post`

请求参数：

| 参数名   | 说明            |
| -------- | --------------- |
| password | 登录密码        |
| username | 账号，手机/邮箱 |

请求头：

```json
{
    "Host": "id.app.acfun.cn",
    "user-agent": "AcFun/6.39.0 (iPhone; iOS 14.3; Scale/2.00)",
    "devicetype": "0",
    "accept-language": "zh-Hans-CN;q=1, en-CN;q=0.9, ja-CN;q=0.8, zh-Hant-HK;q=0.7, io-Latn-CN;q=0.6",
    "accept": "application/json",
    "content-type": "application/x-www-form-urlencoded",
}
```

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "mobile-check": 1,
    "group-level": 1,
    "acPassToken": "***",
    "mobile": "***",
    "avatar": "https://imgs.aixifan.com/style/image/***",
    "auth_key": 625724,
    "userid": 625724,
    "first_login": false,
    "token": "***",
    "check_real": 1,
    "result": 0,
    "acSecurity": "***",
    "check_password": 0,
    "passCheck": true,
    "username": "蒸汽咸鱼"
}
```

</details>

cookies必须包含：

```text
acPasstoken和auth_key
```



### 获取token

请求地址：

>  https://id.app.acfun.cn/rest/web/token/get

请求方式：`post`

请求参数：

| 参数名 | 值                  | 说明 |
| ------ | ------------------- | ---- |
| sid    | acfun.midground.api |      |

请求头：

```json
{
    "Content-Type": "application/x-www-form-urlencoded",
}
```

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "ssecurity": "***",
    "userId": 625724,
    "acfun.midground.api_st": "***",
    "acfun.midground.api.at": "***"
}
```

</details>



### 每日香蕉榜

请求地址：

>  https://api-ipv6.acfunchina.com/rest/app/rank/channel

请求方式：`post`

请求参数：

| 参数名     | 值   | 说明 |
| ---------- | ---- | ---- |
| channelId  | 0    |      |
| rankPeriod | DAY  |      |

请求头：

```json
{
    "Content-Type": "application/x-www-form-urlencoded",
}
```

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "host-name": "hb2-acfun-kce-node113.aliyun",
    "rankList": [
        {
            "groupId": "Ml8wXzE2MTg2NjUxNTU3ODJfNDI0Mw_1&-124&&rlg1",
            "userId": 526850,
            "dougaId": "27816819",
            "channelName": "主机单机",
            "contentId": 27816819,
            "fansCount": 1080417,
            "isFollowing": false,
            "videoCover": "https://tx-free-imgs.acfun.cn/o_1f3cprjdrukk9o41cqc1qsuja10.jpeg?imageslim",
            "channelId": 84,
            "userImg": "http://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCMytcv.webp?imageView2/5/w/480/h/720/format/jpg/ignore-error/1|imageslim",
            "contributeTime": 1618579800778,
            "userName": "老绅",
            "contentTitle": "【特惠喜+1】第157期 欢乐斗地府",
            "contentDesc": "妮可妮可妮~",
            "userSignature": "骸音头上的鼠妇才是本体。微博：AC老绅；斗鱼直播间45662",
            "contributionCount": 452,
            "danmuCount": 849,
            "contentType": 2,
            "duration": 759154,
            "commentCount": 846,
            "durationMillis": 759154,
            "bananaCount": 19110,
            "videoList": [
                {
                    "priority": 0,
                    "durationMillis": 759154,
                    "danmakuCount": 849,
                    "visibleType": 1,
                    "uploadTime": 1618558997588,
                    "title": "157",
                    "sourceStatus": 3,
                    "danmakuCountShow": "849",
                    "sizeType": 1,
                    "danmakuGuidePosition": 10000,
                    "fileName": "157",
                    "id": "23515117"
                }
            ],
            "danmakuCount": 849,
            "fansOnlyDesc": "妮可妮可妮~",
            "shareCount": 59,
            "originalDeclare": 1,
            "stowCount": 443,
            "giftPeachCount": 0,
            "commentCountRealValue": 846,
            "shareUrl": "https://m.acfun.cn/v/?ac=27816819",
            "user": {
                "action": 3,
                "href": "526850",
                "verifiedText": "AcFun签约UP主。节操生不带来死不带去要来何用。",
                "headUrl": "http://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCMytcv.webp",
                "nameColor": 0,
                "verifiedType": 2,
                "verifiedTypes": [
                    2,
                    5
                ],
                "avatarFrame": 315,
                "avatarFrameMobileImg": "http://imgs.aixifan.com/cms/2019_05_16/1557991543458.png",
                "avatarFramePcImg": "https://imgs.aixifan.com/cms/2019_05_16/1557991527323.png",
                "followingCount": "33",
                "contributeCount": "452",
                "followingStatus": 1,
                "comeFrom": "吉林,长春",
                "sexTrend": 1,
                "isFollowing": false,
                "gender": 1,
                "fanCount": "108.0万",
                "userHeadImgInfo": {
                    "width": 180,
                    "height": 180,
                    "size": 56939,
                    "type": 0,
                    "thumbnailImage": {
                        "cdnUrls": [
                            {
                                "url": "https://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCrytcv.webp",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            },
                            {
                                "url": "https://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCrytcv.webp",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            }
                        ],
                        "animated": 1
                    },
                    "smallSharedImage": {
                        "cdnUrls": [
                            {
                                "url": "https://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRD_ydcv.jpg",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            },
                            {
                                "url": "https://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRD_ydcv.jpg",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            }
                        ]
                    },
                    "expandedImage": {
                        "cdnUrls": [
                            {
                                "url": "https://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRDGytcv.webp",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            },
                            {
                                "url": "https://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRDGytcv.webp",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            }
                        ]
                    },
                    "originImage": {
                        "cdnUrls": [
                            {
                                "url": "https://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCMytcv.webp",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            },
                            {
                                "url": "https://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCMytcv.webp",
                                "freeTrafficProductAbbreviation": "",
                                "freeTrafficCdn": false
                            }
                        ]
                    }
                },
                "headCdnUrls": [
                    {
                        "url": "http://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCMytcv.webp",
                        "freeTrafficCdn": false
                    },
                    {
                        "url": "http://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChQwOGExOGMwODEwY2NkYmFiYWYwNRCMytcv.webp",
                        "freeTrafficCdn": false
                    }
                ],
                "isJoinUpCollege": true,
                "followingCountValue": 33,
                "fanCountValue": 1080417,
                "contributeCountValue": 452,
                "name": "老绅",
                "signature": "骸音头上的鼠妇才是本体。微博：AC老绅；斗鱼直播间45662",
                "id": "526850"
            },
            "viewCount": 64443,
            "coverUrl": "https://tx-free-imgs.acfun.cn/o_1f3cprjdrukk9o41cqc1qsuja10.jpeg?imageslim",
            "likeCount": 2937,
            "title": "【特惠喜+1】第157期 欢乐斗地府",
            "createTime": "23小时前",
            "hasHotComment": true,
            "commentCountTenThousandShow": "846",
            "isLike": false,
            "createTimeMillis": 1618579800778,
            "coverCdnUrls": [
                {
                    "url": "https://tx-free-imgs.acfun.cn/o_1f3cprjdrukk9o41cqc1qsuja10.jpeg?imageslim",
                    "freeTrafficCdn": true
                },
                {
                    "url": "https://imgs.aixifan.com/o_1f3cprjdrukk9o41cqc1qsuja10.jpeg?imageslim",
                    "freeTrafficCdn": false
                }
            ],
            "coverImgInfo": {
                "width": 435,
                "height": 272,
                "size": 110065,
                "type": 1,
                "thumbnailImage": {
                    "cdnUrls": [
                        {
                            "url": "https://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChYwOGYyZmZlNDJkMTBiZGQwZTNhZDA2EOnK1y8.webp",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        },
                        {
                            "url": "https://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChYwOGYyZmZlNDJkMTBiZGQwZTNhZDA2EOnK1y8.webp",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        }
                    ],
                    "animated": 1
                },
                "smallSharedImage": {
                    "cdnUrls": [
                        {
                            "url": "https://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChYwOGYyZmZlNDJkMTBiZGQwZTNhZDA2EP_J1y8.jpg",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        },
                        {
                            "url": "https://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChYwOGYyZmZlNDJkMTBiZGQwZTNhZDA2EP_J1y8.jpg",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        }
                    ]
                },
                "expandedImage": {
                    "cdnUrls": [
                        {
                            "url": "https://tx-free-imgs2.acfun.cn/kimg/bs2/zt-image-host/ChYwOGYyZmZlNDJkMTBiZGQwZTNhZDA2EMbK1y8.webp",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        },
                        {
                            "url": "https://ali-imgs.acfun.cn/kimg/bs2/zt-image-host/ChYwOGYyZmZlNDJkMTBiZGQwZTNhZDA2EMbK1y8.webp",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        }
                    ]
                },
                "originImage": {
                    "cdnUrls": [
                        {
                            "url": "https://tx-free-imgs2.acfun.cn/bs2/zt-image-host/08f2ffe42d10bdd0e3ad06",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        },
                        {
                            "url": "https://ali-imgs.acfun.cn/bs2/zt-image-host/08f2ffe42d10bdd0e3ad06",
                            "freeTrafficProductAbbreviation": "",
                            "freeTrafficCdn": false
                        }
                    ]
                }
            },
            "picShareUrl": "https://m.acfun.cn/v/?ac=27816819&shareType=pic",
            "viewCountShow": "6.4万",
            "commentCountShow": "846",
            "shareCountShow": "59",
            "stowCountShow": "443",
            "danmakuCountShow": "849",
            "bananaCountShow": "1.9万",
            "giftPeachCountShow": "0",
            "likeCountShow": "2937",
            "disableEdit": true,
            "tagList": [
                {
                    "name": "话痨绅",
                    "id": "63107"
                },
                {
                    "name": "steam",
                    "id": "1496"
                }
            ],
            "description": "妮可妮可妮~",
            "status": 2,
            "channel": {
                "parentId": 59,
                "parentName": "游戏",
                "name": "主机单机",
                "id": 84
            },
            "isFavorite": false,
            "superUbb": true,
            "isRewardSupportted": true,
            "isThrowBanana": false
        }
    ],
    "requestId": "Ml8wXzE2MTg2NjUxNTU3ODJfNDI0Mw"
}
```

</details>



### 每日签到

请求地址：

>  https://api-ipv6.acfunchina.com/rest/app/user/signIn

请求方式：`post`

请求参数：无

请求头：

```json
{
    "Content-Type": "application/x-www-form-urlencoded",
}
```

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "msg": "签到成功，领取6蕉",
    "bananaDelta": 6,
    "host-name": "hb2-acfun-kce-node148.aliyun",
    "continuousDays": 4
}
```

```json
{
    "result": 122,
    "msg": "今日已签到",
    "error_msg": "今日已签到",
    "host-name": "hb2-acfun-kce-node8.aliyun"
}
```

</details>



### 发弹幕

请求地址：

> https://api-ipv6.acfunchina.com/rest/app/new-danmaku/add

请求方式：`post`

请求参数：

| 参数名         | 值       | 说明                                                         |
| -------------- | -------- | ------------------------------------------------------------ |
| body           | 测试     | 弹幕内容                                                     |
| color          | 16777215 | 弹幕颜色                                                     |
| id             | 17784502 | ac号，详见香蕉榜响应格式中`rankList[0].contentId`            |
| mode           | 1        | 弹幕滚动方式呈现                                             |
| position       | 1000     | 弹幕发送距视频开始时间                                       |
| size           | 25       | 弹幕大小                                                     |
| subChannelId   | 1        | 子频道号，详见香蕉榜响应格式中`rankList[0].channel.parentId` |
| subChannelName | 动画     | 子频道名称，详见香蕉榜响应格式中`rankList[0].channel.parentName` |
| type           | douga    | 类型，固定为douga                                            |
| videoId        | 14177057 | 视频id，详见香蕉榜响应格式中`rankList[0].videoList[0].id`    |

请求头：

```json
{
    "Content-Type": "application/x-www-form-urlencoded",
}
```

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "danmakuId": 123456789,
    "host-name": "hb2-acfun-kce-node127.aliyun"
}
```

</details>



### 视频投蕉

请求地址：

> https://api-ipv6.acfunchina.com/rest/app/banana/throwBanana

请求方式：`post`

请求参数：

| 参数名       | 值       | 说明      |
| ------------ | -------- | --------- |
| resourceId   | 17784502 | ac号      |
| count        | 5        | 投蕉数1~5 |
| resourceType | 2        | 固定值    |

请求头：

```json
{
    "Content-Type": "application/x-www-form-urlencoded",
}
```

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "extData": {
        "bananaRealCount": 5,
        "criticalHitInfo": null
    },
    "host-name": "hb2-acfun-kce-node116.aliyun"
}
```

</details>



### 视频点赞/取消点赞（pc、web通用）

请求地址：

> 点赞：
>
> https://api.kuaishouzt.com/rest/zt/interact/add

> 取消点赞：
>
> https://api.kuaishouzt.com/rest/zt/interact/delete

请求方式：post

请求参数：

| 参数名                 | 值        | 说明                |
| ---------------------- | --------- | ------------------- |
| objectId               | 17784502  | ac号                |
| objectType             | 2         |                     |
| interactType           | 1         |                     |
| subBiz                 | mainApp   |                     |
| acfun.midground.api_st |           | 获取token中的返回值 |
| kpn                    | ACFUN_APP |                     |

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 1,
    "hostName": "public-zl-kcs-node4568.idczw.hb1.kwaidc.com"
}
```

</details>



### 视频分享

请求地址：

> https://api-ipv6.acfunchina.com/rest/app/task/reportTaskAction

请求方式：`get`

请求参数：

| 数名     | 值        | 说明 |
| -------- | --------- | ---- |
| taskType | 1         |      |
| market   | tencent   |      |
| product  | ACFUN_APP |      |
| appMode  | 0         |      |

<details>
<summary>查看响应格式示例：</summary>

```json
{
    "result": 0,
    "host-name": "hb2-acfun-kce-node106.aliyun"
}
```

</details>

